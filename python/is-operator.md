# is 연산자

`is` 는 비교하는 두 개체의 **메모리 주소 값**을 비교합니다.
가끔 **값**만을 비교하는 `==` 와 다른 결과를 도출하여 당황스럽게 합니다.

미묘하지만 중요한 차이점을 코드를 통해 알아봅시다.

```python
name = 'byeongguk'
mimic = 'byeonggu'
mimic += 'k'

another_name = 'byeonggukgong'
another_mimic = 'byeonggukgong'

print(f'name: {name}, memory address: {hex(id(name))}')
print(f'mimic: {mimic}, memory address: {hex(id(mimic))}')
print(f'compare using "is": {name is mimic}, compare using "==": {name == mimic}')

print(f'another_name: {another_name}, memory address: {hex(id(another_name))}')
print(f'another_name: {another_mimic}, memory address: {hex(id(another_mimic))}')
print(f'compare using "is": {another_name is another_mimic}, compare using "==": {another_name == another_mimic}')
```

```txt
name: byeongguk, memory address: 0x7f78da90d530
mimic: byeongguk, memory address: 0x7f78da90d5b0
compare using "is": False, compare using "==": True

another_name: byeonggukgong, memory address: 0x10b2828f0
another_mimic: byeonggukgong, memory address: 0x10b2828f0
compare using "is": True, compare using "==": True
```

```python
number = 1
mimic = 1

another_number = 257
another_mimic = 257

print(f'number: {number}, memory address: {hex(id(number))}')
print(f'mimic: {mimic}, memory address: {hex(id(mimic))}')
print(f'compare using "is": {number is mimic}, compare using "==": {number == mimic}')

print(f'anothor number: {another_number}, memory address: {hex(id(another_number))}')
print(f'another mimic: {another_mimic}, memory address: {hex(id(another_mimic))}')
print(f'compare using "is": {another_number is another_mimic}, compare using "==": {another_number == another_mimic}')
```

```txt
number: 1, memory address: 0x1024cbc90
mimic: 1, memory address: 0x1024cbc90
compare using "is": True, compare using "==": True

another number: 257, memory address: 0x102884f10
another number: 257, memory address: 0x102884f30
compare using "is": False, compare using "==": True
```

`-5 ~ 256`까지 파이썬이 자체적으로 정수 객체를 배열에 저장해두고 참조하기 떄문에 위와 같은 결과 값 차이를 볼 수 있습니다.

## 참조

[큐오라, Python "is" operator?](https://www.quora.com/Python-is-operator)

[블로그, The Hitchhiker's Guide to the Python Memory](https://speakerdeck.com/devunt/the-hitchhikers-guide-to-the-python-memory)

[파이썬 공식 홈페이지, PyObject* PyLong_FromLong(long v)](https://docs.python.org/3/c-api/long.html#c.PyLong_FromLong)
