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
  - CREATE, ALTER, DROP
- DML (Data Manipulation Language)
  - 테이블에 새롭게 데이터를 추가, 삭제, 갱신, 조작할 때 사용하는 언어
  - INSERT, DELETE, UPDATE
- DCL (Data Control Language)
  - 데이터의 사용 권한을 관리하는 데 사용
  - GRANT, REVOKE 등
