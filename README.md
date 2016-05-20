# composite_pattern
------
```python
def add(self, first, *items):
    self.children.append(first)
    if items:
        self.children.extend(items)
 ```
    这里的first不能去除，因为假如去除的话，items所捕获的元素数量可能为0，虽然无害，但却会把用户在代码中所犯的逻辑错误掩盖掉。
------
```python
def add(self, first, *items):
	self.children.extend(itertools.chain((first,), items))
```
    itertools.chain()函数接受若干个iterable，并返回一个iterable。

