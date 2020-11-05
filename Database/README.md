# 👨🏻‍💻 Database (작성중)

### 데이터베이스란 ? 
데이터: 컴퓨터 안에 기록되어 있는 숫자  
데이터베이스: 데이터의 집합, 특정 데이터를 확인하고 싶을 때 간단하게 찾아낼 수 있도록 정리된 형태.
<br>  

### 🌟 DBMS
**DBMS(Database Management System): 데이터베이스를 효율적으로 관리하는 소프트웨어**  
DBMS의 장점
- 생산성
  - CRUD와 같은 기본 기능을 제공함으로써 이를 직접 구현하지 않않아도 됨 -> **생상성 향상**
- 기능성
  - 복수 유저의 요청에 대응하거나, 높은 속도의 검색 기능 등을 제공
- 신뢰성
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
- DDL (Data Definition Language)
  - 테이블이나 관계의 구조를 생성하는 데 사용하는 언어
  - 대상: 도메인, 스키마, 테이블, 뷰, 인덱스
  - CREATE, ALTER, DROP, TRUNCATE
- DML (Data Manipulation Language)
  - 테이블에 새롭게 데이터를 추가, 삭제, 갱신, 조작할 때 사용하는 언어
  - INSERT, DELETE, UPDATE
- DCL (Data Control Language)
  - 데이터의 사용 권한을 관리하는 데 사용
  - GRANT, REVOKE 등  
<br>

## 🌟데이터베이스의 구성요소  
**스키마: 하나의 데이터베이스 객체 (CREATE DATABASE 로 생성한 객체)**  
스키마의 구성요소  
- 테이블
- 뷰
- 인덱스

## 🌟 테이블
용어 | 설명 
---- | ----
행,튜플, 레코드 | 튜플은 릴레이션에서 같은 값을 가질 수 없다.
열, 어트리뷰트 | 테이블 내의 열을 의미
카디널리티 | 튜플의 개수
차수(Degree) | 어트리뷰트의 개수

## 🌟 뷰  
**뷰(View): 다수의 테이블 또는 뷰로 이루어진 논리적 테이블**  
뷰의 목적 : 조인과 결과는 똑같지만, 뷰를 미리 생성해두면 질의(Query)를 단순화할 수있다.  

특징
- 뷰의 정의는 변경이 불가능하다
- 변경하고 싶으면 삭제, 재생성 해야함
- 뷰를 통해 접근한 '데이터'는 변경이 가능
- PK에 해당하는 컬럼이 뷰에 정의되어 있지 않으면 INSERT 불가능

<br>  

## Reference
- <a href = "https://book.naver.com/bookdb/book_detail.nhn?bid=9738902"> SQL 첫걸음 </a> 

