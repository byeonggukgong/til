# DNS

DNS(Domain Name System)은 호스트의 도메인 네임을 호스트의 네트워크 주소로 바꾸거나 그 반대의 변환을 수행합니다.

## 구조

DNS는 트리 형태의 계층적 구조를 가집니다.

* .(루트)
* 1단계 도메인 또는 TLD(Top Level Domain, 최상위 도메인)
  * com, net, biz, io 등
* 2단계 도메인
  * co, go, or 등 또는 희망 문자열
* ···

www.naver.com로 다시 설명하겠습니다.

* .은 루트입니다. (생략됩니다.)
* com은 1단계 도메인 또는 TLD입니다.
* naver는 2단계 도메인입니다.
* www가 서브 도메인 또는 호스트 네임입니다.
* www.naver.com은 FQDN(Fully Qualified Domain Name)입니다.

## 과정

1. 브라우저에서 PC에 등록된 로컬 DNS에 www.daum.net의 IP 주소를 질의합니다.
2. 로컬 DNS에 IP 주소가 있다면 응답합니다. 만약 IP 주소가 없으면 루트 DNS의 주소를 응답합니다.
3. 루트 DNS에 IP 주소가 있다면 응답합니다. 만약 IP 주소가 없으면 www.daum.net의 1단계 도메인을 참고해 net DNS 주소를 응답합니다.
4. ···
