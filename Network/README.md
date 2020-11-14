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

# 애플리케이션 계층 (Application Layer)
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
  - 웹이 진화함에 따라, 상태를 저장해야할 필요가 생겼고 이를 위해 고안된 것이 쿠키(세션)이다.<br><br>
  
  
### HTTP의 메소드
메소드 | 설명
---- | ----
GET | 리소스 획득 (**GET요청은 요청본문이 없다!! -> @RequestBody 사용 불가**)  
POST | 엔티티 전송
PUT | 엔티티 수정, 파일 전송 (<a href = "https://multifrontgarden.tistory.com/245"> POST vs PUT </a>)
DELETE | 엔티티 삭제
OPTIONS | 제공하고 있는 메소드 문의
<br>

### HTTP의 상태 코드
상태코드 | 클래스 | 설명
---- | ---- | ----
1xx | Informational | 리퀘스트를 받아들여 처리중
2xx | Success | 리퀘스트를 정상적으로 처리함
3xx | Redirection | 리퀘스트완료를 위해 추가 동작이 필요
4xx | Client Error | 서버는 리퀘스트 이해 불가능 ex) <a href = "https://github.com/opdshe/spring-boot-challenge/issues/1"> 403</a>
5xx | Server Error | 서버는 리퀘스트 처리 실패
<br>

### 세션과 쿠키
  HTTP는 상태정보를 저장하지 않는다. 하지만, 웹이 진화함에 따라 **상태 정보를 저장해야 할 필요가 생겼고 이를 위해 고안된 것이 바로 쿠키(세션)이다.**  
클라이언트가 서버에게 요청을 하면, 서버는 사용자를 검증한 후 식별값을 응답 헤더의 **set-cookie**에 담아 전송한다. 이후, 클라이언트는 요청을 보낼 때마다 요청 헤더에 **쿠키 식별값을 함께 전송한다.**  
  그렇다면 세션은 무엇인가? 세션 또한 상태정보를 저장하기위한 수단이며, 기본적으로 **세션은 쿠키를 이용한다.** 클라이언트가 서버에 요청하면 서버는 **sessionId를 응답 헤더의 set-cookie에 담아 전송한다.** 즉, 클라이언트는 쿠키를 통해 **로컬에 sessionId값을 저장한다.**     
  세션과 쿠키의 **가장 큰 차이는 저장 장소이다.** 쿠키는 사용자의 **로컬**에 저장되므로 단순히 파일을 읽는 작업이라 **처리 속도가 빠르다**는 장점이 있다. 하지만 로컬에 저장되는 만큼 **보안에 취약하다.**  
세션은 로컬이 아닌 **서버에 저장된다.** 따라서, **보안상의 이점**이 있지만, 세션을 이용할 경우 매번 서버에 요청해야하므로 **처리 속도가 느리다.** 또한 무분별한 세션 사용은 서버에 부하를 줄 수 있다.  
<a href = "https://medium.com/@chrisjune_13837/web-%EC%BF%A0%ED%82%A4-%EC%84%B8%EC%85%98%EC%9D%B4%EB%9E%80-aa6bcb327582"> 참고 </a> 
<br><br>


# 전송 계층 (Transport Layer)  
## ARQ (Automatic Repeat Request)  
**ARQ(검출후 재전송)**: 통신회선에서 착오가 발생하면 수신측은 착오의 발생을 송신측에 알리고, 송신측은 착오가 발생한 block을 재전송하는 방식
- **stop-and-wait**  
  송신측에서 하나의 패킷 전송 후, 수신측의 응이 송신측에 도착해야 다음 패킷 전송  
  **전송 효율이 낮다**  
  
- **pipeline protocol**  
  송신측에서 수신측의 응답을 기다리지 않고 **여러개의 패킷을 전송할 수 있다**
  패킷을 구분하기 위한 순서번호 (Sequence Number)가 필요  
  - **Go-Back-N**  
    - **Cumulative ACK**: 하나도 빠짐없이 받은 가장 마지막 패킷 순서번호를 응답.  
    - 1,2,3,5 전송 -> ACK 1, ACK2, ACK 3, ACK 3 (**수신측에서 5번 패킷 버림**)   
    - Sender는 아직 ACK을 받지 못한 **가장 오래된 패킷에 대해 타이머를 갖는다 (타이머는 하나)**  
    - 최대 Window size만큼 한 번에 전송 가능  
    - **receiver는 window가 필요없음**  
    - **sequence number size > sender window size 를 만족해야 함**  
    
    
  - **Selective-repeat**   
    - **Individual ACK**: 각 패킷에 대한 확인 응답을 전송.  
    - Sender는 아직 ACK을 받지 못한 **모든 패킷에 대해 개별 타이머를 갖는다**    
    - **sequence number < sender window + receiver window**  
<br>

## UDP와 TCP  
### UDP (User Datagram Protocol)  
특징  
- **Connectionless**  
- **신뢰성을 보장하지 않음**  
- **혼잡 제어 하지 않음**  
- 패킷의 순서, 손실 **확인하지 않고 도착하는대로 응용계층으로 전달**  
- **실시간 스트리밍**, **DNS**, SNMP 등에 사용  

헤더 
- source port #
- dest port #
- length
- **checksum** (**에러를 수정하진 않지만, 망가진 데이터는 응용 계층으로 전달하지 않기 위해 checksum 필요**)  
<br>

### TCP (Transmission Control Protocol)  
특징
- **Connection oriented**
  - 연결: 3 way handshaking  
  - 연결종료: 4 way handshaking  
- **신뢰성 보장**
- **혼잡 제어**
- 패킷의 **순서를 보장**하며, **손실없이** 모두 응용 계층으로 전달 
- **Cumulative ACK** (**다음에 받을 패킷의 Sequence number를 전송**)  
- **GO-Back-N과 Selective repeat의 장점들을 적절히 섞어서 사용**  
- Full duplex data 전송  

헤더
- source port #  
- dest port #  
- **sequence number**  
- **ack number**  
- **receive window (flow-control에 필요)**  
- **checksum** 
- flags 등  

#### ✨ TCP의 재전송 트리거  
- **Time Out**  
- **Duplicated ACK**   

  ❉ **TCP Fast Retransmition:** 타임 아웃되기 전에 세개의 Duplicated ACK을 통해 패킷 손실을 인지하고, 재전송 하는 것  
  (네 개의 똑같은 ACK = 세 개의 Duplicated ACK)   
<br>

### TCP의 흐름 제어(flow control)  
전송 계층에는 **receive buffer**라는 것이 존재한다. 응용계층에서 이 **receive buffer**에 있는 데이터를 읽어가야 데이터가 사라진다.  
이 receive buffer의 크기는 무한하지 않다. 응용계층에서 데이터를 읽는 양보다 receive buffer에 도착하는 데이터의 양이 많으면,  
데이터는 점점 쌓이게 되고 수용할 수 있는 양을 초과하면 데이터는 **버려진다.** 이때, 패킷이 버려지는 것을 막기 위해  
Receiver 측의 **Receive buffer가 수용할 수 있는 만큼만 데이터를 보내도록 제어하는 것**을 **흐름 제어**라고 한다. (**End to End**)  

#### 흐름 제어 방법  
- **Stop-and-wait**  
  패킷 전송 후 해당 패킷에 대한 응답이 도착해야 다음 패킷 전송  
  
- **Sliding Window**  
  TCP헤더에 존재하는 **receive window**에 **receive buffer**의 빈공간의 크기를 기입하여 전송.  
  송신측은 전달받은 **receive window 크기에 맞게** 전송량 조절. 

<br>

### TCP의 혼잡 제어  
네트워크 계층의 라우터에도 데이터를 담을 수 있는 **buffer**가 있다. 이 buffer가 무한하면 좋겠지만 현실은 그렇지 않다.  
buffer가 수용할 수 있는 양 이상의 데이터가 buffer에 도착하면, 데이터는 **버려지기 시작한다.** 이는 **전송 효율 저하**를 야기한다.  
데이터가 버려지는 양을 최소화 하기 위해, **전송 계층에서 네트워크 계층으로** 보내는 데이터 양을 조절하는 것을 **혼잡 제어**라고 한다.  
(**Transport <-> Network**)  

#### 기본 개념  
데이터 손실을 줄이기 위해, Sender가 보내는 데이터의 양을 조절.  
- **swnd**
  - **sender**가 한 번에 보낼 수 있는 **window size**
  - **swnd = min[rwnd, cwnd]**  
  - 일반적으로 **rwnd >> cwnd**  -> **cwnd가 swnd를 결정**  
<br>  

- **cwnd**  
  - **ACK를 확인하지 않고도 보낼 수 있는 데이터의 양**  
  - cwnd는 네트워크 상태에 따라 **변화하는 값**
  

#### 혼잡 제어 방법 
 
- **AIMD(Additive Increse Multiplicative Decrese)**  
  - 매 **RTT마다** cwnd를 **1씩 증가**  
  - loss 발생 시 cwnd **반으로 감소**  
  - **최적의 속도를 내기까지 오래걸린다는 단점이 있음**  

- **Slow start & Congestion Avoidance**  
  - **slow start**  
    - **ACK**을 받을 때 마다 cwnd **1증가** -> 매 **RTT**마다 cwnd가 **2배로 증가**
    - cwnd가 **ssthresh**(slow start threshold)에 도달할 때까지 진행<br>  
  <br>
  
  - **congestion avoidance**  
    - **ACK**을 받을 때 마다 **MSS*MSS/cwnd** 만큼 증가 -> 매 **RTT**마다 **1MSS 증가**
    - cwnd가 **ssthresh**에 도달한 이후부터 진행<br>  
  <br>
  
  ✨ **패킷 손실이 발생하면 ??**
  - Time out 상황  
    - 패킷의 대량 손실을 의미 -> **심각한 네트워크 상황**  
    - **cwnd를 1MSS로 설정 후 slow start 시작**
  
  - 3 Duplicated ACK 상황
    - 특정 ACK은 못받았지만, 그 **뒤의 최소 3개의 패킷은 받았음을 의미** -> **심각하지 않은 네트워크 상황**  
    - **cwnd를 반으로 설정 후 congestion avoidance 시작**  
    
 <br>
 
# 네트워크 계층 (Network Layer)
### ✨ 라우팅 시스템의 변화
- 이전의 라우팅 시스템
  - 라우터 **각각이 개별적 forwarding table**을 가짐
  - 패킷을 수신하면 **자신이 가진 forwading table에 근거하여** 경로 설정<br>
  
- **SDN**(Software Definded Networking)
  - **Remote Controller**가 forwarding table을 결정하여 각 라우터에게 전달
  - **중앙집권적**
  - 장점
    - 정책 변겨 시 하나의 Remote Controller만 수정하면 됨


<br>

## Reference
- <a href = "https://book.naver.com/bookdb/book_detail.nhn?bid=12500834"> 컴퓨터 네트워킹 하향식 접근 </a> 
- <a href = "http://www.yes24.com/Product/Goods/15894097"> 그림으로 배우는 HTTP & NETWORK BASIC </a>

