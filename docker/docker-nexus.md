# Nesux 설치하기

## Docker Compose

1. Docker Compose를 설치합니다.
2. `docker-compose.yml` 파일을 만듭니다.

```yaml
nexus:
  image: sonatype/nexus3
  restart: always
  container_name: nexus
  ports:
    - 8081:8081
    - 12000:12000
  volumes:
    - nexus-data:/nexus-data
```

3. `docker-compose.yml` 파일이 있는 디렉토리에서 `docker-compose up -d` 명령어로 Nexus를 실행합니다.
