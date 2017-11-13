# Know first and use it, "is" operator

`is` 는 비교하는 두 개체의 **메모리 주소 값**을 비교합니다.  
가끔 **값**만을 비교하는 `==` 와 다른 결과를 도출하여 당황스럽게 합니다.

미묘하지만 중요한 차이점을 코드를 통해 알아봅시다.

```python
name = "byeongguk"
mimic = "byeonggu"
mimic += "k"

print("name: {}, memory address: {}".format(name, hex(id(name))))
print("mimic: {}, memory address: {}".format(mimic, hex(id(mimic))))
print("compare using "is": {}, compare using "==": {}".format(name is mimic, name == mimic))
```
```txt
name: byeongguk, memory address: 0x7f78da90d530
mimic: byeongguk, memory address: 0x7f78da90d5b0
compare using "is": False, compare using "==": True
```

`is` 와 `==` 을 용도에 맞게 구별하여 **Pythonic** 하게 개발합시다.

## Reference

[Rakesh Reddy, Python "is" operator?][quora-python-is-operator]  
[Junehyeon Bae, The Hitchhiker's Guide to the Python Memory][junehyeon-bae-hitchhikers-guide-to-the-python-memory]

[quora-python-is-operator]: https://www.quora.com/Python-is-operator
[junehyeon-bae-hitchhikers-guide-to-the-python-memory]: https://speakerdeck.com/devunt/the-hitchhikers-guide-to-the-python-memory