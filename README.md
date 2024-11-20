# Computer_science
## 1, 자료구조
### 1-1 자료구조랑?
### 1-2 시간복잡도
### 1-3 공간복잡도
데이터를 구조적으로 표현하는 방식을 배우는 과정
자료구조의 기본 연산
탐색,
삽입,
삭제

배열의 삽입 연산
연결 리스트


---
## 2, 운영체제
### 2-1 운영체제란?
운영체제는 컴퓨터의 자원을 관리하고, 프로그램에 대한 지원을 하는 시스템 SW

Application
CPU
Device
OS
Memory

시스템 콜

User Mode
Kernel Mode

Dual Mode

Kernel : 시스템 소프트웨어

인터럽트

프로그램 : 프로그래밍 언어를 통해서 만들어진 결과물

프로세스

언어의 분류
컴파일 과정
인터프리터 언어

아키텍쳐

컴파일러 
=> 컴파일 언어 -> 목적 프로그램
링커
=> 목적 프로그램들 => 실행 프로그램
.dll file

### 2-2 프로그램이 되는 과정
java
자바 가상 환경

javaScript
가상 환경


프로그램 -> 프로세스
로더 : 보조기억장치로부터 주기억장치에 프로그램을 적재하는 시스템 SW

모든 프로세스는 부모-자식 간의 트리 형태를 가짐
새로운 프로세스 생성은 fork() -> exec() 시스템 콜을 호출하는 방식

### 2-3 프로세스와 스레드
프로세스란?
프로그램이 메모리에 올라와 실행 가능한 상태가 되는 것

프로세스의 메모리 구조
- Text(Code) 영역 : 실행중인 프로그램이 포함되는 영역
- Data 영역 : 전역 변수, 정적변수 등이 저장됨, 컴파일때 크기가 정해짐
- Heap 영역 : 동적으로 할당되는 메모리 영역
- Stack 영역 : 함수 호출 값들이 저장되는 영역

콜 스탯
각 함수 내의 변수 정보도 함께 저장된다.

PCB(Process Control Block) 프로세스의 정보를 담은 일련의 저장공간  
Pointer : Process State  
Process Number(ID)  
Program Counter  
Registers  
Memory limits  
List of open files  

스레드
컴퓨터에서 작업을 수행하는 단위

프로세스와 스레드의 관계
프로세스 : 자원을 할당 받는 단위
스레드 : 작업을 수행하는 단위

스레드의 주소공간

CPU는 한번에 하나의 작업만
동시성 : 한 번에 여러 프로그램이 돌아가는 것 처럼 보이게 하는 것
병렬성 : 한 번에 여러 프로그램을 돌리는 것

스래드는 2가지가 있다
코어/스레드의 스레드든 CPU의 코어와 다는 논리적인 코어의 수
프로세스/스레드의 스레드는 작업을 수행하는 단위

### 2-4 프로세스 동기화
하나의 작업을 어떻게 나누어서 수행할까?
멀티 프로세싱 :  
멀티 스레딩 : 

성능-> 멀티 스레딩이 멀티 프로세싱보다 가볍다
안정성 -> 멀티 스레딩보다 멀티 프로세싱이 훨신 안정적이다.

Race Condition
타이밍에 따라 결과가 다르게 나올 수 있는 지점

Locking Algorithm
특정 자원이나, 진입점에 대해 잠금을 걸어버리는 메커니즘
=> Locking은 실행을 하고 나면 반드시 Locking 을 해제해야 한다.

Mutex : Mutual Exclustion의 약자로, 락의 소유권을 갖는 방식
Samaphore : 카운트 방식의 Locking Algorithm, 중앙에서 Lock의 소유권을 관리한다.

CAS
비교하고, 교환하는 코드를 한 번에 처리하는 방식
Atomic

### 2-5 프로세스 스케줄링

어떤 방식으로 동시성을 보장할 수 있는가?
스케줄링 알고리즘 : 
여러 프로세스를 어떤 방식으로 CPU에 할당할지 결정하는 알고리즘  
-> 대기시간 단축, 선택되지 않는 스레드가 없어야 한다.

FCFS(First Come, First Served)
먼저 들어온 프로세스부터 처리  
-> 대기시간이 길어질 수밖에 없다  
-> 우선순위가 적용되지 않는다.  

SJF(Shortest Job First)
가장 남은 시간이 잛은 Job을 우선적으로 처리  
-> 가장 이상적이지만 실현 불가  
-> 기존 기록을 확인 => 예상시간을 측정  

Preemtive VS Non-Preemtive
새로운 Job이 들어왔을 때, 수행중인 기존 Job을 빼앗을 수 있는가?

Priority Scheduling
프로세스에 우선순위를 지정하여, 그 순서대로 스케줄링
-> Aging 문제 : 우선순위가 낮은 프로세스는 수행되지 않을 수 있다.
-> 그래서 우선순위가 낮아서 실행되지 않는 프로세스는 일정 시간이 지나면 우선수위를 높힌다.

Round Robin(RR)
모든 프로세스 마다 동일한 시간 간격(Time Quantum)을 부여하는 방식

Multi-level Queue
프로세스를 우선순위에 따라 나누고, 각 층마다 서로 다른 알고리즘 사용

Multi-level Feedback Queue  
Multi-level Queue + Aging

### 2-6 캐시 메모리
램과 하드디스크

메모리의 계층성
메모리를 필요에 따라 여러 종류로 분리한 것
=> 자주 접근

캐시 메모리
CPU에 포함된 작은 메모리로, 접근 속도가 매우 빠름
한 번 접근한 값은 캐시 메모리에 저장되므로, 반복 접근 시 매우 빠름
-> Cache Miss(최초 접근)
-> Cache Hit(2회차 이상)
캐시의 크기는 작기 떄문에, 모든 데이터가 들어가지 못함

캐시 지역성
캐시의 효울을 위해선, 시간적/공간적으로 인접한 데이터 접근을 해야 함

### 2-7 메모리 관리

프로그램 쪼개서 밀어넣기

세그먼트 : 프로세스 주소공간에 맞춰서 프로세스를 분리하는 방식  
페이징 : 똑같은 크기의 "페이지"로 공간을 분리하는 방법  
-> 단편화의 단점 -> 내부 단편화, 외부 단편화  


Demanding Paging
프로그램 중에서 필요한 부분만 사용한다.

가상 메모리
프로그램의 실행중인 부분만 메모리에 적재하는 방식
Frame : 실제 램 공간 분할

페이지 테이블
pid : p : d
p => 몇번 페이지
d => 어느 위치

## 3. 네트워크
### 3-1 HTTP
HTTP란? 
Hyper Text Transfer Protocol
웹에서 파일을 주고 받기 위한 

Protocol
통신 방식에 대한 일종의 규약(어떤 방식으로 통신을 할 것인가?)
HTTP : Hyper Text Transfer Protocol
FTP : File Transfer Protocol
IP : Internet Protocol

### 3-2 OSI 7계층

OSI 7계층 : 네트워크 통신을 7개의 레이어로 나눈 것
HTTP Header

OSI 7계층 - 캡슐화

OSI 7계층 - 물리 계층
데이터의 물리적 연결(전기 신호)의 전송을 관리

OSI 7계층 - 데이터 링크 계층
네트워크 기기 간 데이터 전송, 오류 검출 및 제어 처리
MAC(주소) : 각 기기에 할당된 주소

OSI 7계층 - 네트워크 계층 
데이터의 전송 경로를 결정해주는 역할을 하는 계층
IP 주소

IP 주소 vs MAX 주소
IP 주소 : 상대적이며, 똑같은 기기에서도 다른 IP가 가능하다.
MAC 주소 : 각 기기에 귀속된 주소로, 변경이 불가능하다.

OSI 7계층 - 전송 계층
데이터를 신뢰성 있게 전송할 수 있도록 돕는 계층 + 프로세스 단위로 통신이 가능하다.
TCP vs UDP
IP Address VS Port Number
Port Number : 프로세스 포트 번호

OSI 7계층 - 응용 계층
전송 받은 데이터를 활용해서, 특정한 작업을 수행하는 계층

### 3-3 TCP vs UDP
전송 계층 - TCP
연결 지향적 전송 계층 프로토콜로, 안정적인 통신을 위한 기능을 제공
TCP - 3 Way Handshake
TCP - 4 Way Handshake
TCP - Sequence Number

TCP - HTTP
주로 HTML 문서를 주고받는 데에 쓰인다. 주로 TCP를 사용한다.

HTTP Persistent Connection
HTTP Stateless

TCP의 단점
기능이 몹시, 몹시 많다! -> 느리다

전송 계층 - UDP
비연결 지향적 전송 계층 프로토콜로, 특별한 추가 기능을 제공하지 않음
TCP에 비해 엄청나게 가볍다!


### 3-4 인터넷을 타고 떠나는 여행

단골 질문 
주소창에 www.naver.com을 쳤을 때, 네트워크에서 발생하는 일을 최대한 자세히 설명하세요

1) 인터넷에 연결하기 : IP 주소를 할당받는다.  
유동 IP, 고정 IP => 어떻게 IP 주소를 받을까?
=> DHCP(Dynamic Host Configuration Protocol) IP 할당 받기위한 절차 
-> DHCP Discover => BroadCast => IP 주소를 받기 위해 주변에 모든 곳에 요청을 보낸다.
=> 우리가 쓰는 인터넷의 95%는 유동 IP이다.(IPv6)  
=> 고정 IP를 발급 받아서, 계속 사용한다.
2) 목적지 IP 주소를 찾는다.
도메인에서 IP로
도메인 : IP에 대한 별칭으로, 사람이 기억하기 쉽도록 만든 것
DNS : Domain Name Server - 도메인에 대한 정보를 갖고 있는 서버들
도메인 체계 : 
DNS Query 
1, 로컬 저장 데이터를 확인한다.(DNS Cache,Host File)
2, 최상위 도메인부터 시작하여, 상위에서 하위로 내려가며 주소를 구한다.
3) 네트워크에 최적의 경로를 찾아서 연결한다.
라우터 : 패킷을 추출하여, 그 위치에 대한 최적의 경로를 지정하여 전달하는 장치
최적의 경로를 찾는 법
Routing Table
Subnet : IP 주소에서 네트워크 영역을 부분적으로 나눈 네트워크
이동할 때마다 캡슐화
HTTP는 TCP니까
HTTP Handshake - 3 Way Handshake
HTTPS - HTTP-Secure
