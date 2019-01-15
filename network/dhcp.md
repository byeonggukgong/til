# DHCP

DHCP(Dynamic Host Configuration Protocol)는 IP 주소 및 관련된 기타 구성 세부 정보를 DHCP 사용 클라이언트에게 동적으로 할당하기 위한 프로토콜입니다.

## 장점

까페나 공공장소와 같이 일시적인 IP 주소 할당이 자주 발생하는 곳이나 회사처럼 할당량 이상의 할당을 요청하는 곳에서 IP 충돌을 방지할 수 있어 관리가 편합니다.

## 단점

DHCP 서버가 IP 주소를 할당 및 관리하기 때문에 서버에 장애가 발생하면 할당이 제대로 이루어지지 않습니다. 또, 할당 과정 중 발생하는 잦은 브로드캐스트(Broadcase)는 네트워크에 부하를 줄 수 있습니다.

## 동작원리

### 임대

1. DHCP Discover
   - 클라이언트가 서버에게 IP 주소 할당을 요청하는 Discover 패킷에 `서버 MAC 주소`를 담아 브로드캐스트합니다.
2. DHCP Offer
   - 서버는 Discover 패킷을 받게 되면, 특정 IP 주소를 예약해두고 Offer 패킷에 `클라이언트 MAC 주소`, `클라이언트가 사용할 IP 주소(서버에서 예약해준 IP 주소)`, `서버 IP 주소`와 `IP 주소 임대 기간(유효 시간)`을 담아 브로드캐스트 또는 유니캐스트(Unicast)합니다.
3. DHCP Request
   - 클라이언트가 Offer 패킷을 받게 되면, Request 패킷에 `클라이언트 MAC 주소`, `클라이언트가 사용하기로 결정한 IP 주소(서버에서 예약해준 IP 주소)`와 서버가 하나 이상 있다면 `서버 IP 주소`도 담아 브로드캐스트합니다.
4. DHCP Ack
   - 서버가 Request 패킷을 받게 되면, Ack 패킷에 `클라이언트가 사용할 IP 주소(서버에서 확정한 IP 주소)`와 `기타 구성 세부 정보`를 담아 브로드캐스트 또는 유니캐스트합니다.

### 갱신

1. DHCP Request
   - 클라이언트는 IP 주소 임대 기간 갱신 요청을 Request 패킷에 담아 유니캐스트합니다. (갱신은 임대 기간의 50%, 리바인드는 임대 기간의 87.5%)
2. DHCP Ack
   - 서버는 IP 주소 임개 기간 갱신 정보를 Ack 패킷에 담아 유니캐스트합니다.

### 반환

클라이언트와 서버 모두 IP 주소 임대 기간을 가지고 있어 기간이 끝나면 반환합니다.

## 참조

- [블로그, DHCP란? #1](http://jwprogramming.tistory.com/35)
- [블로그, DHCP란? #2](http://blog.naver.com/PostView.nhn?blogId=cmw1728&logNo=221075863208)
- [나무위키, DHCP](https://namu.wiki/w/DHCP)
- [위키피디아, Dynamic Host Configuration Protocol](https://en.wikipedia.org/wiki/Dynamic_Host_Configuration_Protocol)
- [웹페이지, DHCP 임대 갱신 재연결 리바인딩 해제](http://www.ktword.co.kr/abbr_view.php?m_temp1=5571)
