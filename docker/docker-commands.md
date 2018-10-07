# Docker 명령어

> Docker 18.06.1-ce 기준

## 목록

- [Client](#client)
  - [Image](#image)
  - [Container](#container)

## Client

- `version`은 클라이언트와 데몬의 버전을 보여준다.
- `pull`은 `image pull`과 동일하다.
- `exec`는 `container exec`와 동일하다.
- `run`은 이미지를 가져와 컨테이너를 생성하고 실행한다.

### Image

- `pull`은 저장소(Registry)에서 이미지를 가져온다.
- `build`는 Dockerfile로 이미지를 만든다.
- `history`는 이미지의 변경 내역을 보여준다.
- `inspect`는 이미지의 자세한 정보를 보여준다.
- `prune`은 모든 이미지를 없앤다.

### Container

- `ls`는 실행중인 컨테이너 목록을 보여준다.
  - `-a, -all`를 붙이면 종료된 컨테이너도 포함하여 목록을 보여준다.
  - `-l, --lastest`를 붙이면 마지막으로 생성된 컨테이너를 보여준다.
- `create`는 컨테이너를 만든다.
- `exec`는 실행중인 컨테이너에 명령어를 실행한다.
- `inspect`는 컨테이너의 자세한 정보를 보여준다.
- `prune`은 모든 컨테이너를 없앤다.
