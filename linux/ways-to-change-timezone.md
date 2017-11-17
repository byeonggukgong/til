# Ways to change timezone

**timezone** 을 확인하기 위해 `date` 명령어로 시스템 시간을 알아봅니다.

```txt
Mon Nov 13 09:49:28 UTC 2017
```

**UTC**(Coordinated Universal Time, 세계 협정시) 를 **KST**(Korea Standard Time, 한국 표준시) 로 변경합니다.

### tzselect

홈 디렉토리의 *.profile* 파일에 `TZ='Asia/Seoul'; export TZ` 를 저장합니다.

```txt
$ tzselect

* skip the process *

You can make this change permanent for yourself by appending the line
        TZ='Asia/Seoul'; export TZ
to the file '.profile' in your home directory; then log out and log in again.

Here is that TZ value again, this time on standard output so that you
can use the /usr/bin/tzselect command in shell scripts:
Asia/Seoul
```

### /etc/localtime

`ln -sf` 명령어를 사용하여 */etc/localtime* 에 */usr/share/zoneinfo/Asia/Seoul* 의 링크를 설정합니다.

```txt
$ sudo ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
```

### dpkg-reconfigure tzdata

Ubuntu/Debian 계열에서 적용되는 명령어입니다.

```txt
$ sudo dpkg-reconfigure tzdata

* skip the process *

Current default time zone: 'Asia/Seoul'
Local time is now:      Mon Nov 13 18:49:28 KST 2017.
Universal Time is now:  Mon Nov 13 09:49:28 UTC 2017.
```

## Reference

[Unix & Linux Stack Exchange, Timezone Setting in Linux][timezone-setting-in-linux]  
[Ramesh Natarajan, How To: 2 Methods To Change TimeZone in Linux][how-to-2-methods-to-change-timezone-in-linux]

[timezone-setting-in-linux]: https://unix.stackexchange.com/questions/110522/timezone-setting-in-linux
[how-to-2-methods-to-change-timezone-in-linux]: http://www.thegeekstuff.com/2010/09/change-timezone-in-linux/