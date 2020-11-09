# 👨🏻‍💻 Network

## Network란?
서로 연결되어 있는 모든 것을 의미한다.  
<br>  

## 컴퓨터 네트워크의 구성 요소
- 종단 시스템 (Host)
- 통신 링크 (Communication link)
  - 구리선, 위성, 등 
- 패킷 스위치 (Packet switch)
  - 패킷들을 내보내는 장치
  - ex) 라우터, 스위치
- ISP
  - 인터넷을 제공하는 집단
  - ex) skt, kt, lg u+
- 프로토콜 (Protocol)
  -  데이터 통신을 원활하게 하기 위해 필요한 통신 규약
  - ex) TCP, IP, HTTP... 
- 인터넷 표준 (Internet Standard)  
<br>  

## 데이터 전달 방식  
- **회선 교환 (Circuit switching)**
  - **end to end 연결 설정**
  - 회선당 하나의 호스트 연결
  - 이용률 측면에서는 좋지 않다. (연결 후 데이터 전송하지 않을 때 자원낭비 발생)
  - **실시간 데이터 전송에 용이**
  <br>  
- **패킷 교환(Packet switching)**
  - 데이터는 **패킷 단위로 분할하여 전송**
  - 패킷들은 네트워크 상태에 따라, **각기 다른 경로를 통해 전송될 수 있음**
  - 전송 링크를 공유  
  - 이용률 측면에서 효율적  
  - 현대의 인터넷은 **보편적으로 패킷 교환을 사용**
## 💫 프로토콜
서로 다른 하드웨어와 운영체제 등을 가지고 통신을 하기 위해서는 통신 규약 혹은 규칙들이 필요하고, 이를 프로토콜이라 부른다.  
## 인터넷 프로토콜 스택 (Internet Protocol Stack)
- 애플리케이션  
  - HTTP, DNS, SMTP, FTP
- 전송계층 (Transport)
  - **process - process 간 데이터 전송**
  - **TCP, UDP**
- 네트워크 (Network)
  - **라우팅과 포워딩** 담당
  - **IP, Routing protocols**
- 링크계층 (Link)
  - 인접한 네트워크 요소와의 데이터 전송 **(논리적)**
  - 이더넷, 802.11, PPP
- 물리계층 (Physical)

## OSI 7계층
- 애플리케이션
- 프레젠테이션
- 세션
- 전송
- 네트워크
- 링크
- 물리    
<br>  

**_실사용에서는 애플리케이션과 전송계층이 프레젠테이션, 세션 레이어의 역할을 포함한다_**

## 계층을 분할하는 이유
- 변경사항이 생길 시, 해당 계층만 수정하면 되므로 수정에 용이
- 설계시, 각 계층은 자기 자신이 담당하는 부분만 고려하면 됨
<br>

## 🌟 HTTP와 관계 깊은 핵심 프로토콜들
- **IP (Internet Protocol)**
  - **네트워크 계층**에 해당
  - 패킷을 상대방에게 전달하는 역할
  - ARP를 이용하여 경로 탐색  
  **ARP(Address Resolution Protocol): 수신지의 IP주소를 바탕으로 MAC주소를 획득하는 프로토콜**
  - ARP를 통해 획득한 **MAC주소를 기반으로 통신**
<br>  

- **TCP**
  - **트랜스포트 계층**에 해당
  - 신뢰성 있는 바이트 스트림 서비스  
  **바이트 스트림 서비스: 큰 데이터를 보내기 쉽게 TCP 세그먼트로 분해하여 관리**  
  - 정확히 보냈는지 확인
  - 연결 : 3 way handshaking
  - 연결 종료: 4 way handshaking
<br>

- **DNS**
  - 애플리케이션 계층
  - 도메인명을 통해 IP주소 제공
  - IP 주소를 통해 도메인명 제공
  
<br>

## HTTP
- HTTP는 **클라이언트/서버 간의 통신이다.**
- Request와 Response를 교환하여 성립한다.
  - 클라이언트가 응답을 보내야지만 서버가 응답. (서버가 먼저 요청을 보내지 않음)
- HTTP 메세지
  - HTTP 요청 (Request)
    - 메소드, URI, 프로토콜 버전, 헤더, 본문으로 구성
    - **GET**, HEAD, DELETE, OPTIONS는 **본문이 없다 !! 매우 중요**
  - HTTP 응답 (Response)
    - 프로토콜 버전, 상태코드, 상태 텍스트, 헤더, 본문으로 구성<br>
    
- **HTTP는 상태를 유지하지 않는 프로토콜(Stateless)**
  - HTTP는 지나간 요청, 응답 정보를 기억하지 않는다.
  - 웹이 진화함에 따라, 상태를 저장해야할 필요가 생겼고 이를 위해 고안된 것이 쿠키(세션)이다.<br>
  
### HTTP의 메소드
메소드 | 설명
---- | ----
GET | 리소스 획득 (**GET요청은 요청본문이 없다!! -> @RequestBody 사용 불가**)  
POST | 엔티티 전송
PUT | 엔티티 수정, 파일 전송 (<a href = "https://multifrontgarden.tistory.com/245"> POST vs PUT </a>)
DELETE | 엔티티 삭제
OPTIONS | 제공하고 있는 메소드 문의



## Reference
- <a href = "https://book.naver.com/bookdb/book_detail.nhn?bid=12500834"> 컴퓨터 네트워킹 하향식 접근 </a> 
- <a href = "http://www.yes24.com/Product/Goods/15894097"> 그림으로 배우는 HTTP & NETWORK BASIC </a>

