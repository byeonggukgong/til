# More efficient ways to work, "update-alternatives" command

`update-alternatives` 명령어는 여러 버전의 패키지를 관리하기 위해 사용합니다.

## Debian/Ubuntu 기준

### update-alternatives 목록

`update-alternatives --list <name>` 형식으로 `<name>` 에 해당하는 패키지를 확인합니다.

```txt
$ update-alternatives --list python3
update-alternatives: error: no alternatives for python3
```

> 아직 등록된 버전의 패키지가 없습니다.

### update-alternatives 등록

`update-alternatives --install <link> <name> <path> <priority>` 형식으로 `<name>` 에 해당하는 패키지에 `<path>` 버전을 등록합니다.

> 인자 값들은 순서대로 `<명령어 링크 경로> <패키지 이름> <버전 경로> <auto mode 의 버전 우선 순위>` 입니다.

```txt
$ update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.4 1
update-alternatives: using /usr/bin/python3.4 to provide /usr/bin/python3 (python3) in auto mode

$ update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.5 2
update-alternatives: using /usr/bin/python3.5 to provide /usr/bin/python3 (python3) in auto mode
```

> `<priority>` 는 높을수록 **auto mode** 의 버전 우선 순위를 가집니다.

### update-alternatives 변경

`update-alternatives --set <name> <path>` 형식으로 `<name>` 에 해당하는 패키지의 `<path>` 버전으로 변경합니다.  
`update-alternatives --config <name>` 형식으로 `<name>` 에 해당하는 패키지의 버전을 변경합니다.

> `--set` 과 `--config` 는 동일한 기능을 하지만 비대화형과 대화형이라는 차이를 가집니다.

```txt
$ python3 --version
Python 3.5.4

$ update-alternatives --set python3 /usr/bin/python3.4

$ python3 --version
Python 3.4.3

$ update-alternatives --config python3
There are 2 choices for the alternative python3 (providing /usr/bin/python3).

  Selection    Path                Priority   Status
------------------------------------------------------------
  0            /usr/bin/python3.5   2         auto mode
* 1            /usr/bin/python3.4   1         manual mode
  2            /usr/bin/python3.5   2         manual mode

Press enter to keep the current choice[*], or type selection number: 0

$ python3 --version
Python 3.5.4
```

### update-alternatives 제거

`update-alternatives --remove <name> <path>` 형식으로 `<name>` 에 해당하는 패키지에서 `<path>` 의 버전을 제거합니다.

```txt
$ update-alternatives --remove python3 /usr/bin/python3.4
$ update-alternatives --remove python3 /usr/bin/python3.5

$ update-alternatives --list python3
update-alternatives: error: no alternatives for python3
```

> 패키지에 속한 모든 버전을 제거하여 패키지도 마찬가지로 제거됩니다.

## Reference

[Ubuntu Manpage, update-alternatives - maintain symbolic links determining default commands][1]

[1]: http://manpages.ubuntu.com/manpages/trusty/man8/update-alternatives.8.html