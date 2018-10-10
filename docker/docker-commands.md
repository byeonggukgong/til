# Docker 명령어

> Docker 18.06.1-ce 기준

## 목록

- [Client](#client)
  - [Image](#image)
  - [Container](#container)
- [Machine](#machine)

## Client

- `version`은 클라이언트와 데몬의 버전을 보여준다.
- `pull`은 `image pull`과 같다.
- `rmi`는 `image rm`과 같다.
- `start`는 `container start`와 같다.
- `run`은 이미지를 가져와 컨테이너를 만들고 실행한다.
- `exec`는 `container exec`와 같다.
- `rm`은 `container rm`과 같다.

### Image

- `pull`은 레지스트리에서 이미지를 가져온다.
- `build`는 Dockerfile로 이미지를 만든다.
- `history`는 이미지의 변경 내역을 보여준다.
- `inspect`는 이미지의 자세한 정보를 보여준다.
- `rm`은 하나 이상의 이미지를 없앤다. (컨테이너가 참조 중인 이미지는 강제로 없애야 한다.)
  - `-f, --force`를 붙이면 이미지를 강제로 없앤다.
- `prune`은 모든 이미지를 없앤다.

### Container

- `ls`는 실행 중인 컨테이너 목록을 보여준다.
  - `-a, -all`를 붙이면 종료된 컨테이너도 포함하여 목록을 보여준다.
  - `-l, --lastest`를 붙이면 마지막으로 생성된 컨테이너를 보여준다.
- `create`는 컨테이너를 만든다.
- `start`는 하나 이상의 멈춘 컨테이너를 실행한다.
- `exec`는 실행 중인 컨테이너에 명령어를 실행한다.
- `inspect`는 컨테이너의 자세한 정보를 보여준다.
- `rm`은 하나 이상의 컨테이너를 없앤다. (실행 중인 컨테이너는 강제로 없애야 한다.)
  - `-f, --force`를 붙이면 컨테이너를 강제로 없앤다.
- `prune`은 모든 컨테이너를 없앤다.

## Machine

- `ls`는 머신 목록을 보여준다.
- `create`는 머신을 만든다. (드라이버를 반드시 정해야 한다.)
  - `-d, --driver`를 붙이면 [드라이버](https://docs.docker.com/machine/drivers/)를 정한다.
- `start`는 머신을 실행한다.
- `restart`는 머신을 다시 실행한다.
- `stop`은 머신을 멈춘다.
- `kill`은 머신을 강제로 멈춘다.
- `status`는 머신의 상태를 보여준다.
- `inspect`는 머신의 정보를 보여준다.
- `rm`은 하나 이상의 머신을 없앤다.
  - `-f, --force`를 붙이면 머신을 강제로 없앤다.
