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





## Reference
- <a href = "https://book.naver.com/bookdb/book_detail.nhn?bid=12500834"> 컴퓨터 네트워킹 하향식 접근 </a> 
- <a href = "http://www.yes24.com/Product/Goods/15894097"> 그림으로 배우는 HTTP & NETWORK BASIC </a>

