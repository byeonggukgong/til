# 원격 저장소 주소 변경하기

`git remote set-url` 명령어는 **원격 저장소 URL**을 변경하는데 사용합니다.

```command
# git remote set-url https://github.com/USERNAME/REPOSITORY.git

$ git remote -v
origin  https://github.com/byeonggukgong/old.git (fetch)
origin  https://github.com/byeonggukgong/old.git (push)

$ git remote set-url origin https://github.com/byeonggukgong/new.git

$ git remote -v
origin  https://github.com/byeonggukgong/new.git (fetch)
origin  https://github.com/byeonggukgong/new.git (push)
```

## 참고

[GitHub Help, Changing a remote's URL](https://help.github.com/articles/changing-a-remote-s-url/)
