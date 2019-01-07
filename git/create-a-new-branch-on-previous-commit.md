# 이전 커밋에 새 브랜치 생성하기

`git branch` 명령어는 **새 브랜치**를 생성하는데 사용합니다.

```
# git branch [브랜치 명] [브랜치를 생성할 위치(HEAD 또는 커밋 해쉬)]

$ git log --graph --oneline --all

* 611ea6e (HEAD -> master, origin/master, origin/HEAD) Update configurations
* 7ef7c74 Translate English into Korean

$ git branch develope HEAD~1

$ git log --graph --oneline --all

* 611ea6e (HEAD -> master, origin/master, origin/HEAD) Update configurations
* 7ef7c74 (develop)Translate English into Korean
```

# 참고

[Branch from a previous commit using Git](https://stackoverflow.com/questions/2816715/branch-from-a-previous-commit-using-git)
