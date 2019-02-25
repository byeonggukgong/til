# 파일 내용 복사하기와 붙여넣기

## 복사하기

```bash
$ echo "Hello, world" | pbcopy
```

```bash
$ cat 파일 이름 | pbcopy
$ pbcopy < 파일 이름.확장자
```

## 붙여넣기

```bash
$ echo `pbpaste`
```

```bash
$ pbpaste > 파일 이름.확장자
```

## 참조

- [블로그, pbpaste & pbcopy in Mac OS X (or: Terminal + Clipboard = Fun!)](https://langui.sh/2010/11/14/pbpaste-pbcopy-in-mac-os-x-or-terminal-clipboard-fun/)
