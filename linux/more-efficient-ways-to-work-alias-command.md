# More efficient ways to work, "alias" command

`alias` 는 반복적으로 사용해야 하는 명령어에 **별칭**을 붙입니다.

아래의 간단한 예제를 통해 알아봅시다.

### alias 목록

```txt
$ alias

alias ..='cd ..'
alias grep='grep --color=auto'

        * skip the contents *

alias ls='ls --color=auto -F'
```

### alias 등록

`alias [-p] [name[=value] ... ]` 형식으로 등록합니다.


```txt
$ alias file_count='find . -type f | wc -l'

$ alias

alias ..='cd ..'
alias file_count='find . -type f | wc -l'
alias grep='grep --color=auto'

        * skip the contents *

alias ls='ls --color=auto -F'
```

> 재부팅 시 초기화됩니다. 영구적인 사용을 위해서는 홈 디렉토리의 *.bashrc* 파일에 추가해야 합니다.

### alias 제거

`unalias [-a] name [name ...]` 형식으로 해당 별칭 또는 전체 별칭을 제거합니다.

```txt
$ unalias file_count
$ alias

alias ..='cd ..'
alias grep='grep --color=auto'

        * skip the contents *

alias ls='ls --color=auto -F'

$ unalias -a
$ alias
```

## Reference

[LINFO, The alias Command][the-alias-using-command]  
[흉내쟁이, 리눅스 Alias - 별칭 사용하기][linux-alias-using-alias]

[the-alias-using-command]: http://www.linfo.org/alias.html
[linux-alias-using-alias]: http://webdir.tistory.com/107