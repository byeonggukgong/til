# CDN

CDN(Contents Delivery Network)은 느린 응답 속도와 다운로드 타임을 극복하기 위한 기술입니다. 원격 서버로 부터 미리 컨텐츠를 저장하고 근처 클라이언트에게 응답합니다.

* 원격 서버로 집중되는 트래픽을 분산시켜 부하를 낮추고 장애 발생률을 낮춥니다.
* 원격 서버보다 물리적으로 가까운 클라이언트에게 신속 정확하게 컨텐츠를 전달합니다.

## 정적 캐싱

원격 서버의 컨텐츠를 관리자가 미리 캐시 서버에 저장해둡니다. 항상 컨텐츠가 저장되어있습니다. (이미지, 동영상, 게임 설치 파일 등)

## 동적 캐싱

클라이언트가 컨텐츠를 요청하면 해당 컨텐츠가 있는지 확인합니다. 만약 없다면 원격 서버에서 다운로드해 저장합니다. 이후 동일한 요청을 받으면 저장된 컨텐츠로 응답합니다. (웹 페이지 등)

컨텐츠의 유효기간을 정해 캐시 서버에서 삭제하거나 원격 서버로 다운로드해 최신 상태를 유지할 수 있습니다.
