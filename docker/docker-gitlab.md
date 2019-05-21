# GitLab 설치하기

## Docker Compose

1. Docker Compose를 설치합니다.
2. `docker-compose.yml` 파일을 만듭니다.

```yaml
gitlab:
  image: gitlab/gitlab-ce
  restart: always
  hostname: gitlab.example.com
  container_name: gitlab
  environment:
    GITLAB_OMNIBUS_CONFIG: |
      external_url "http://gitlab.example.com"
  ports:
    - 22:22
    - 80:80
    - 443:443
  volumes:
    - gitlab-config:/etc/gitlab
    - gitlab-logs:/var/log/gitlab
    - gitlab-data:/var/opt/gitlab
```

3. `docker-compose.yml` 파일이 있는 디렉토리에서 `docker-compose up -d` 명령어로 GitLab을 실행합니다.
