# Know first and use it, enumerate()

`enumerate()` 는 **iterable(list, tuple, string)** 를 인자 값으로 가지며, 동일한 순서의 인덱스와 아이템을 내장 함수 `list([iterable])` 를 이용하여 `[(0, youngje), (1, minho) ... ]` 와 같은 형식을 지닌 **enumerate object** 를 반환합니다. 

보통 아래 예제처럼 for loop 와 함께 사용됩니다.

```python
friends = ["youngje", "minho", "jonggu", "bongsu", "chanho"]

# enumerate(iterable[, start])
for idx, friend in enumerate(friends, start=1):
    print("{}. my friend {}".format(idx, friend))
```
```txt
1. my friend youngje
2. my friend minho
3. my friend jonggu
4. my friend bongsu
5. my friend chanho
```

매우 심플한 코드로 **Pythonic** 하게 해결합니다.

## Reference

[PEP 279, enumerate()][enumerate-pep]  
[Programiz, enumerate()][enumerate-programiz]

[enumerate-pep]: https://www.python.org/dev/peps/pep-0279/
[enumerate-programiz]: https://www.programiz.com/python-programming/methods/built-in/enumerate