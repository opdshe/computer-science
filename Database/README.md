# 👨🏻‍💻 Database (작성중)

### 데이터베이스란 ? 
데이터: 컴퓨터 안에 기록되어 있는 숫자  
데이터베이스: 데이터의 집합, 특정 데이터를 확인하고 싶을 때 간단하게 찾아낼 수 있도록 정리된 형태.
<br>  

### 🌟 DBMS
**DBMS(Database Management System): 데이터베이스를 효율적으로 관리하는 소프트웨어**  
DBMS의 장점
- **생산성**
  - CRUD와 같은 기본 기능을 제공함으로써 이를 직접 구현하지 않않아도 됨 -> **생산성 향상**
- **기능성**
  - 복수 유저의 요청에 대응하거나, 높은 속도의 검색 기능 등을 제공
- **신뢰성**
  - DBMS를 통해 확장성(Scalability)와 부하분산(Load balancing)을 구현할 수 있다.
  - 백업 기능 제공 
  
DBMS 종류
- RDB (관계형 데이터베이스)
  - MySQL
  - OracleDB
  - MariaDB
- NoSQL(비관계형 데이터베이스)
  - MongoDB
<br>

### 🌟 SQL이란?
**SQL: DBMS중에서, RDBMS를 조작하기 위한 언어.** 
- **DDL** (Data Definition Language)
  - 테이블이나 관계의 구조를 생성하는 데 사용하는 언어
  - 대상: 도메인, 스키마, 테이블, 뷰, 인덱스
  - CREATE, ALTER, DROP, TRUNCATE
- **DML** (Data Manipulation Language)
  - 테이블에 새롭게 데이터를 추가, 삭제, 갱신, 조작할 때 사용하는 언어
  - INSERT, DELETE, UPDATE
- **DCL** (Data Control Language)
  - 데이터의 사용 권한을 관리하는 데 사용
  - GRANT, REVOKE 등  
<br>

## 🌟 관계형 데이터베이스의 구성요소  
**스키마: 하나의 데이터베이스 객체 (CREATE DATABASE 로 생성한 객체)**  
스키마의 구성요소  
- 테이블
- 뷰
- 인덱스

### 테이블
용어 | 설명 
---- | ----
행,튜플, 레코드 | 튜플은 릴레이션에서 같은 값을 가질 수 없다.
열, 어트리뷰트 | 테이블 내의 열을 의미
카디널리티 | 튜플의 개수
차수(Degree) | 어트리뷰트의 개수

### 뷰  
**뷰(View): 다수의 테이블 또는 뷰로 이루어진 논리적 테이블**  
뷰의 목적 : 조인과 결과는 똑같지만, 뷰를 미리 생성해두면 질의(Query)를 단순화할 수있다.  

특징
- 뷰의 정의는 변경이 불가능하다
- 변경하고 싶으면 삭제, 재생성 해야함
- 뷰를 통해 접근한 '데이터'는 변경이 가능
- PK에 해당하는 컬럼이 뷰에 정의되어 있지 않으면 INSERT 불가능<br>

<br>

### 인덱스  
**인덱스(Index): 데이터를 빠르게 찾을 수 있는 수단으로써, 테이블에 대한 조회 속도를 높여 주는 자료 구조.**

특징  
- 인덱스는 테이블의 특정 레코드 위치를 알려 주는 용도로 사용  
- **인덱스는 자동으로 생성되지 않는다.** (**_단, PK 칼럼은 자동으로 생성_**)  
- **찾고자 하는 칼럼에 인덱스가 없으면, 전체 레코드를 검색해야 함 -> 속도가 느림** <br><br>


**✨ 인덱스는 무조건 사용하는 것이 좋은가?** <br>
인덱스는 항상 정렬된 상태를 유지하므로, **_원하는 값을 탐색하는 것은 빠르지만    
새로운 값을 추가하거나 삭제, 수정하는 경우에는 쿼리문 실행 속도가 느려진다.     
따라서, 저장 성능보다 검색 속도가 중요한 상황에서 사용하는 것이 좋다._**  <br><br>

**✨ 인덱스 칼럼은 어떤 기준으로 선정하는 것이 좋은가?** <br>
중복이 적은 칼럼을 선정하는 것이 좋다. 그래야 많이 걸러냄으로써 성능적 효율을 가져올 수 있다


## 🌟 트랜잭션
**트랜잭션(Transaction): 데이터베이스의 상태를 변화시키기 해서 수행하는 작업의 단위. 트랜잭션은 하나의 연산이 아닐 수 있다.**<br>  


### 트랜잭션의 특징 (ACID)
- **원자성(Atomicity)**  
  트랜잭션은 더 이상 작은 단위로 쪼개질 수 없다. 작업이 모두 데이터베이스에 반영되던가, 모두 반영되지 않아야함  
  수행하고 있는 트랜잭션에 의해 변경된 내역을 유지하면서, **이전에 commit된 상태를 임시 영역에 따로 저장함으로써 보장**  <br>
  
- **일관성(Consistency)**  
  기존의 데이터가 Correct State라면 트랜잭션 처리 후에도 Correct State이어야 함  
  트랜잭션 수행 전, 후에 데이터 모델의 **모든 제약 조건(기본키, 외래키, 도메인, 도메인 제약조건 등)을 만족하는 것을 통해 보장**
  
  *Correct State : 도메인의 유효범위, 무결성 제약조건 등의 제약조건을 위배하지 않는 정상적인 상태*<br>
  
- **독립성(Isolation)**  
  하나의 트랜잭션이 실행되는 동안 다른 트랜잭션이 끼어들 수 없다  
  **lock을 통해 보장할 수 있음**
  - Shared lock : 데이터를 읽을 때 사용하며, 다른 트랜잭션 또한 해당 자원을 읽을 수 있다. (다른 트랜잭션은 수정 불가능)
  - Exclusive lock : 데이터를 수정할 때 사용. 다른 트랜잭션에서 접근할 수 없다. (다른 트랜잭션은 읽기, 쓰기 둘 다 불가능)<br>
  
- **지속성(Durability)**  
  트랜잭션이 완료되면 결과는 영원히 지속되어야함  
<br>

### 트랜잭션의 상태
![트랜잭션상태](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=http%3A%2F%2Fcfile23.uf.tistory.com%2Fimage%2F999C55345B6D2ED308A7CA)
상태 | 설명
---- | ----
활동(Active) | 트랜잭션이 실행중인 상태
부분 완료(Partially Committed) | 트랜잭션의 마지막 연산까지 실행했지만, **Commit 연산이 실행되기 직전의 상태**
완료(Committed) | 트랜잭션이 성공적으로 종료되어 **Commit 연산을 실행한 후의 상태**
실패(Failed) | 트랜잭션 실행에 오류가 발생하여 **중단된 상태**
철회(Aborted) | 트랜잭션이 비정상적으로 종료되어 **Rollback 연산을 수행한 상태**
<br>
<br>

## 트랜잭션의 읽기 이상현상
![image](https://user-images.githubusercontent.com/50160282/129444687-dd36bce7-bfdd-4b9a-983e-394dd4c80f49.png)

## 트랜잭션의 고립 수준
<img width="1410" alt="스크린샷 2021-08-14 오후 8 54 21" src="https://user-images.githubusercontent.com/50160282/129445471-5be12dba-20ea-4c40-bf79-6bc336019b69.png">

<br>

### ✨ 서버 다중화 상황에서 하나의 데이터 베이스 내 같은 데이터에 동시 접근을 막으려면 ??
트랜잭션 고립 수준은 **읽기 이상현상**에 대한 격리 수준이다. 쓰기작업에 대한 동시접근을 막으려면 고립 수준만으로는 해결할 수 없다. Read Uncommitted, Read committed, Repeatable-read는 일반 select 시 락을 걸지 않는다. (shared lock, exclusive lock 모두 안건다) 따라서, 하나의 데이터에 대한 동기화 처리 불가능하다. Serializable의 경우 select 시 for share 로 shared lock을 건다. 하나의 트랜잭션이 데이터에 Shared lock을 걸면 다른 트랜잭션은 해당 데이터에 Exclusive lock 걸 수 없다. 하지만 shared lock은 걸 수 있다. 
```
select query;
update query;
```
위와 같은 트랜잭션을 두 트랜잭션이 동시에 두 트랜잭션이 실행했다고 가정하자. 두 트랜잭션 모두 동시에 select query를 실행하며 shared lock을 건다. 하지만 앞서 말했듯 shared lock이 걸린 데이터에 exclusive lock 을 걸 수가 없다. 즉 데드락 상황이 발생한다. 만약 하나의 Api server라면 synchronized 키워드로 해결할 수 있지만, 서버 다중화 상황이라면 synchronized로는 해결할 수 없다. 
```
select ... for update
```
위와 같이 select 시 배타락(exclusive lock)을 거는 것이 해결책이다. JPA는 아래와 같이 비관적 락 사용해야 함
```
public interface ReviewRepository extends JpaRepository<Review, Long> {
	@Lock(value = LockModeType.PESSIMISTIC_WRITE)
	Optional<Review> findById(Long id);
}
```

<br>

## 🌟 데이터의 무결성   
### 무결성의 종류  
- **개체 무결성**   
  - 모든 테이블이 기본 키로 선택된 어트리뷰트를 가져야 한다  
  - **기본키는 중복될 수 없다**  
  - **기본키는 NULL값이 될 수 없다**<br>  
  
- **참조 무결성**  
  - 참조 관계에 있는 두 테이블의 데이터가 **항상 일관된 값을 갖도록 유지하는 것**  
  - **어떠한 외래 키 B가 A를 참조한다면, A를 삭제할 수 없다. (B를 삭제 후, A를 삭제해야 함)**<br>  
  
- **도메인 무결성(속성 무결성)**  
  - 필드의 타입, NULL값의 허용 등에 대한 사항을 정의하고, **올바른 데이터가 입력 되었는지를 확인하는 것**<br>  
  
- **키 무결성**  
  - 한 릴레이션에 **같은 키 값을 가진 튜플이 존재할 수 없음**
<br>  

### ✨ 외래키와 제약조건  
데이터베이스에서는 **참조 무결성**을 위해 참조 대상이 존재하지 않는 외래 키를 허용하지 않는다.  
또한, 참조 무결성을 지키기 위해 외래키 제약조건들이 존재한다. 

- **RESTRICTED(Default)**: 레코드를 변경 또는 삭제하고자 할 때 **해당 레코드를 참조하고 있는 개체가 있다면, 변경 또는 삭제 연산을 취소한다.** <br>

- **CASCADE**: 레코드를 변경 또는 삭제하면, **해당 레코드를 참조하고 있는 개체도 변경 또는 삭제된다.**<br>  

- **SET NULL**: 레코드를 변경 또는 삭제하면, 해당 레코드를 참조하고 있는 개체의 값을 **NULL로 설정한다.**<br>   

<a href = "https://untitledtblog.tistory.com/123">참고 </a> 

<br>
<br>


 
## 🌟 KEY
**KEY: 데이터베이스에서 특정 행을 구별할 수 있는 기준이 되는 속성(Attribute)**<br>  
**유일성**: 하나의 키값으로 하나의 튜플을 특정할 수 있어야 함  
**최소성**: 키를 구성하는 속성의 개수를 **최소**로하여 유일성을 만족시켜야함  
          (최소성을 만족한다면, 키를 구성하는 속성 중 하나를 제거하면 유일성을 만족시키지 못해야함)
<br>

- **슈퍼키(Super key)**
  - **유일성을 만족하는 모든 키들의 집합**
  - **최소성은 만족하지 않아도 됨**
  - 가장 넓은 범위

- **후보키(Candidate Key)**
  - 슈퍼키 중 **최소성도 만족하는 키들의 집합**
  - 기본키가 될 수 있는 키들의 집합
  - **유일성, 최소성 모두 만족**
  
- **기본키(Primary key, PK)** 
  - **후보키 중 튜플 구별을 위해 선택한 키**
  - **유일성, 최소성 모두 만족**

- **대체키(Alternate Key)**  
  - **후보키 중 기본키로 선택되지 못한 키들의 집합**
  - **유일성, 최소성 모두 만족**
<br>

❉ **복합키**: 두개 이상의 속성으로 구성된 후보키  
<a href = "https://jhnyang.tistory.com/71"> 참고 </a> 

  
## 🌟 테이블 결합  
테이블 결합에는 **내부 결합**과 **외부 결합**이 있다. 이 두가지는 테이블 결합 시, **어느 한쪽에만 존재하는 데이터 행을 처리하는 방식이 다르다.**   
**내부 결합**은 어느 한 쪽에만 존재하는 데이터행은 **취급하지 않는다.**   
**외부 결합**은 어느 한 쪽에만 존재하는 데이터에 대해서 **NULL값으로 출력할 수 있다.**  
<br>

**상품**  
상품코드 | 상품명 | 가격 
---- | ---- | ----
001 | OO | 100
002 | XX | 200
003 | YY | 300

**재고**
상품코드 | 재고수 
---- | ----
001 | 200
002 | 300

- **내부 결합**  
  상품명 | 재고수
  ---- | ----
  OO | 200
  XX | 300
  
  - SELECT 상품.상품명, 재고.재고수 FROM 상품 INNER JOIN 재고 ON 상품.상품코드 = 재고.상품코드 
  - 재고 테이블에 003번에 대한 데이터가 없으므로, 003은 **취급하지 않음.**  
  
- **외부 결합**
  상품명 | 재고수
  ---- | ----
  OO | 200
  XX | 300
  YY | NULL
  - SELECT 상품.상품명, 재고.재고수 FROM 상품 LEFT JOIN 재고 ON 상품.상품코드 = 재고.상품코드 
  - 재고 테이블에 없는 003번은, **NULL값으로 처리**
  
### ✨ LEFT JOIN 과 RIGHT JOIN 차이
**LEFT JOIN**: JOIN 기준으로 **왼쪽 테이블은 모두 표시하고**, 오른쪽 테이블에 데이터가 없으면 **NULL로 처리.**  
**RIGHT JOIN**: JOIN 기준으로 **오른쪽 테이블은 모두 표시하고**, 왼쪽 테이블에 데이터가 없으면 **NULL로 처리.**  

<br>

### 정규화
- 제 1 정규화
  - 하나의 칼럼에는 하나의 값만 존재하도록 테이블 구조 변경
	- 이후, 반복되는 그룹들(칼럼집합) 테이블 분리 진행
	- 1 정규화가 진행되면 테이블 분할과 기본키 지정이 이루어짐
	
- 제 2 정규화
	- 기본키의 일부만으로 다른 칼럼을 특정할 수 있는 경우 테이블 분리를 진행

- 제 3정규화
	- 기본키 이외의 칼럼에서 한 칼럼이 다른 칼럼을 특정할 수 있는 경우 테이블 분리 진행

- BCNF
  - 결정자이면서 후보키가 아닌 것을 제거해야 한다

### 정규화의 목적
'하나의 데이터는 한 곳에만 존재하도록' 해서, 확장에도 용이하고, 수정시에도 한 번의 쿼리로 수정할 수 있도록 하기위해

<br>

### 반정규화
반정규화는 정규화된 엔티티, 속성, 관계를 시스템의 성능 향상 및 개발과 운영의 단순화를 위해 다시 하나로 합치는 데이터 모델링 기법 중 하나이다. 일반적으로 조회에 대한 처리 성능이 중요하다고 판단될 때 부분적으로 반정규화를 고려하게 된다.

### 언제 반정규화를 진행할 것인가?
데이터를 수정할 일이 많지 않으며, 조회 성능이 가장 우선시 되는 데이터에 적용하는 것이 좋다

<br>

### 파티셔닝
**파티셔닝 : 하나의 큰 테이블을 관리하기 쉬운 단위로 분리하는 것**
장점
- 가용성
	- 전체 데이터의 훼손 가능성이 줄어들고 데이터 가용성이 향상됩니다.
- 성능
	- 특정 DML(Database Manipulation Language)과 쿼리의 성능을 향상시킵니다. 

단점
- 테이블간 조인이 많아져 비용이 증가
<br>

**Q. 쿼리 성능 향상 시킨다해놓고 테이블간 조인이 많아져서 비용이 증가한다고 ??**  
특정 칼럼만 필요한 경우가 많다면 수직 파티셔닝을 고려해 볼 수 있다. 예를들어 사용자의 데이터 중 이름만 필요할 때가 많다면 이름 칼럼만 분리하는 것을 고려해 볼 수 있다. 
단, 사용자의 모든 데이터를 조회할 때는 Join을 해야하므로 비용이 증가한다

## Reference
- <a href = "https://book.naver.com/bookdb/book_detail.nhn?bid=9738902"> SQL 첫걸음 </a> 

