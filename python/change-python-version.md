# Ways to change version of python

**version of python** 을 `python3 --version` 명령어로 확인합니다.

```txt
Python 3.4.3
```

### alias

명령어에 별칭을 붙여 사용합니다.  
하나의 **version of python** 을 사용하기 위해 변경하는 가장 간단한 방법입니다.

```txt
$ alias python3='/usr/bin/python3.5'
```

> 자세한 설명은 [More efficient ways to work, "alias" command][more-efficient-ways-to-work-alias-command] 를 참고합니다.

### update-alternatives

Ubuntu/Debian 계열에서 적용되는 명령어입니다.  
여러 **version of python** 을 유동적으로 사용하기에 매우 적합하여 개인적으로 추천하는 방법입니다.

```txt
$ update-alternatives --list python3
update-alternatives: error: no alternatives for python3

$ update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.4 1
update-alternatives: using /usr/bin/python3.4 to provide /usr/bin/python3 (python3) in auto mode
$ update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.5 2
update-alternatives: using /usr/bin/python3.5 to provide /usr/bin/python3 (python3) in auto mode

$ update-alternatives --config python3
There are 2 choices for the alternative python3 (providing /usr/bin/python3).

  Selection    Path                Priority   Status
------------------------------------------------------------
* 0            /usr/bin/python3.5   2         auto mode
  1            /usr/bin/python3.4   1         manual mode
  2            /usr/bin/python3.5   2         manual mode

Press enter to keep the current choice[*], or type selection number:
```

> 자세한 설명은 [More efficient ways to work, "update-alternatives" command][more-efficient-ways-to-work-update-alternatives-command] 를 참고합니다.

## Reference

[LinuxConfig, How to change from default to alternative Python version on Debian Linux][how-to-change-from-default-to-alternative-python-version-on-debian-linux]

[more-efficient-ways-to-work-alias-command]: https://github.com/byeonggukgong/til/blob/master/linux/more-efficient-ways-to-work-alias-command.md
[more-efficient-ways-to-work-update-alternatives-command]: https://github.com/byeonggukgong/til/blob/master/linux/more-efficient-ways-to-work-update-alternatives-command.md
[how-to-change-from-default-to-alternative-python-version-on-debian-linux]: https://linuxconfig.org/how-to-change-from-default-to-alternative-python-version-on-debian-linux