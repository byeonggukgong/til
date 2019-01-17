# Docker 명령어

> Docker 18.06.1-ce 기준

## 목록

- [Client](#client)
  - [Container](#container)
  - [Image](#image)
  - [Swarm](#swarm)
- [Machine](#machine)

## Client

- `build`는 `image build`와 같습니다.
- `cp`는 `container cp`와 같습니다.
- `exec`는 `container exec`와 같습니다.
- `pull`은 `image pull`과 같습니다.
- `rm`은 `container rm`과 같습니다.
- `rmi`는 `image rm`과 같습니다.
- `run`은 이미지를 가져와 컨테이너를 만들고 실행합니다.
- `start`는 `container start`와 같습니다.
- `stop`은 `container stop`과 같습니다.
- `version`은 클라이언트와 데몬의 버전을 보여줍니다.

### Container

- `cp`는 컨테이너와 로컬 파일 시스템 사이의 파일/폴더를 복사합니다.
- `create`는 컨테이너를 만듭니다.
- `exec`는 실행 중인 컨테이너에 명령어를 실행한다.
- `inspect`는 컨테이너의 자세한 정보를 보여준다.
- `ls`는 실행 중인 컨테이너 목록을 보여줍니다.
  - `-a, -all`를 붙이면 종료된 컨테이너도 포함하여 목록을 보여줍니다.
  - `-l, --lastest`를 붙이면 마지막으로 생성된 컨테이너를 보여줍니다.
- `prune`은 모든 컨테이너를 없앱니다.
- `rm`은 하나 이상의 컨테이너를 없앱니다. (실행 중인 컨테이너는 강제로 없애야 합니다.)
  - `-f, --force`를 붙이면 컨테이너를 강제로 없앱니다.
- `start`는 하나 이상의 멈춘 컨테이너를 실행합니다.
- `stop`은 하나 이상의 실행 중인 컨테이너를 멈춥니다.

### Image

- `build`는 Dockerfile로 이미지를 만듭니다.
- `history`는 이미지의 변경 내역을 보여줍니다.
- `inspect`는 이미지의 자세한 정보를 보여줍니다.
- `prune`은 모든 이미지를 없앱니다.
- `pull`은 레지스트리에서 이미지를 가져옵니다.
- `rm`은 하나 이상의 이미지를 없앱니다. (컨테이너가 참조 중인 이미지는 강제로 없애야 합니다.)
  - `-f, --force`를 붙이면 이미지를 강제로 없앱니다.

### Swarm

- `init`은 스웜을 만든다.
  - `--advertise-addr`를 붙이면 스웜에 들어갈 주소를 정합니다.
- `join`는 스웜에 들어간다. (토큰에 따라서 매니저 또는 워커로 역할이 주어집니다.)
- `join-token`는 스웜에 들어가기 위해 필요한 토큰을 관리합니다. (매너저 또는 워커를 반드시 정해야 합니다.)
  - `-q, --quiet`를 붙이면 토큰만 보여줍니다.
  - `--rotate`를 붙이면 새 토큰을 만듭니다.
- `leave`는 스웜에서 나옵니다.
  - `-f, --force`를 붙이면 스웜에서 강제로 나옵니다.

## Machine

- `create`는 머신을 만듭니다. (드라이버를 반드시 정해야 합니다.)
  - `-d, --driver`를 붙이면 [드라이버](https://docs.docker.com/machine/drivers/)를 정합니다.
- `inspect`는 머신의 정보를 보여줍니다.
- `kill`은 머신을 강제로 멈춥니다.
- `ls`는 머신 목록을 보여줍니다.
- `restart`는 머신을 다시 실행합니다.
- `rm`은 하나 이상의 머신을 없앱니다.
  - `-f, --force`를 붙이면 머신을 강제로 없앱니다.
- `start`는 머신을 실행합니다.
- `status`는 머신의 상태를 보여줍니다.
- `stop`은 머신을 멈춥니다.
