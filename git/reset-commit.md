# Ways to reset commit

`reset` 명령어는 의도한 바와 다른 **commit** 을 되돌리는데 사용합니다.

> 예제의 `HEAD~1` 는 이전 **commit** 을 가리킵니다. (`HEAD` 는 현재 **commit**)  
> **복구 지점 commit 해시 값** 으로도 사용 가능합니다.

### --soft 

복구 지점의 **commit** 과 그 이후의 **모든 변경(staged)** 들이 남습니다.

```command
$ git reset --soft HEAD~1
```

### --mixed

**기본 옵션**으로 복구 지점의 **commit** 과 그 이후의 **모든 변경(unstaged)** 들이 남습니다.

```command
$ git reset HEAD~1
```

### --hard

복구 지점의 **commit** 만 남고, 그 이후의 모든 변경들이 **초기화**됩니다.

```command
$ git reset --hard HEAD~1
```

> 다른 옵션과 달리 복구할 수 없으므로 신중히 사용하여야 합니다.

## Reference

[Git, Git 도구 - Reset 명확히 알고 가기](https://git-scm.com/book/ko/v2/Git-%EB%8F%84%EA%B5%AC-Reset-%EB%AA%85%ED%99%95%ED%9E%88-%EC%95%8C%EA%B3%A0-%EA%B0%80%EA%B8%B0)  
[유봉주, \[초보용\] Git 되돌리기(Reset, Revert)](http://devpools.kr/2017/02/05/%EC%B4%88%EB%B3%B4%EC%9A%A9-git-%EB%90%98%EB%8F%8C%EB%A6%AC%EA%B8%B0-reset-revert/)


