# Ways to find command

### type

**파일** 위치, `bash builtin` 및 `alias` 명령어 여부 등의 정보를 알려줍니다.

```txt
$ type ifconfig
ifconfig is /sbin/ifconfig
```

### which

**실행 파일**의 위치를 찾으며, `alias` 명령어가 있다면 먼저 알려줍니다.  

> `-a` 옵션은 검색 가능한 모든 경로에서 해당 명령어를 찾습니다.

```txt
$ which ls
/bin/ls

$ which -a ls
/bin/ls
/mnt/shared/sbin/ls
```

> `bash builtin` 명령어는 보이지 않습니다.

### whereis

**binary**, **source**, **manual page**의 위치를 알려줍니다.

```txt
$ whereis  ifconfig
ifconfig: /sbin/ifconfig /usr/share/man/man8/ifconfig.8.gz
```

> `bash builtin` 과 `alias` 명령어는 보이지 않습니다.

## Reference

[제타위키, 리눅스 명령어 위치 확인](https://zetawiki.com/wiki/%EB%A6%AC%EB%88%85%EC%8A%A4_%EB%AA%85%EB%A0%B9%EC%96%B4_%EC%9C%84%EC%B9%98_%ED%99%95%EC%9D%B8)  
[흉내쟁이, 리눅스 which, whereis, locate - 명령어의 경로 확인](http://webdir.tistory.com/158)