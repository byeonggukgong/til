# Know first and use it, range() and xrange()

### range()

`range()` 의 형식은 `range([start], stop[, step])` 이며,  **list** 타입을 반환합니다.

```python
range(3)
range(1, 7)
range(1, 7, 2)
```
```txt
[0, 1, 2]
[1, 2, 3, 4, 5, 6, 7]
[1, 3, 5, 7]
```

일괄적으로 모든 값을 메모리에 할당하며, 범위가 커질수록 할당량 또한 늘어납니다.

### xrange()

`xrange()` 의 형식은 `xrange([start], stop[, step])` 이며, **xrange** 타입을 반환합니다.  

```txt
* skip, same as above example *
```

메모리 할당량은 일정하고, 해당 값에 접근할 때 할당하여 사용합니다.

> 순차적 접근 또는 인덱스를 활용할 때 `xrange()` 사용이 효율적입니다.  
> 구조적 차이에 의해 용도가 달라집니다.

### Tip

혹시, `Python 3` 코드를 `Python 2` 에서 실행해야 한다면 이렇게 해봅시다.

```python
import sys

if sys.version.info < (3,):
	range = xrange
```

## Reference

[Python 2.x document: range][python2-range]
[Python 2.x document: xrange][python2-xrange]
[Python 3.x document: range][python2-xrange]

[python2-range]: https://docs.python.org/2/library/functions.html#range
[python2-xrange]: https://docs.python.org/2/library/functions.html#xrange
[python3-range]: https://docs.python.org/3/library/functions.html#func-range