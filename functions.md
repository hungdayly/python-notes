# Hàm

## Tạo hàm

```python
def my_function():
    pass
```

## Gọi hàm

```python
>>> def my_function():
...     print('Hello from my_function')
...
>>> my_function()
Hello from my_function
```

## Truyền đối số

### Truyển đối số đơn giản

```python
>>> def welcome(name):
...     print(f'Welcome {name}')
...
>>> welcome('Mike')
Welcome Mike
```

Giá trị trả về mặc định của hàm `None`:

```python
>>> def welcome(name):
...     print(f'Welcome {name}')
...
>>> return_value = welcome('Mike')
Welcome Mike
>>> print(return_value)
None
```

### Nhắc kiểu

```python
>>> def welcome(name: str) -> int:
...     print(f'Welcome {name}')
...     return 5
...
>>> return_value = welcome('Mike')
Welcome Mike
>>> print(return_value)
5
```

### Truyền đối số theo vị trí và theo tên

Mặc định các tham số của hàm có thể được truyền đối số theo vị trí hoặc theo tên.

```python
>>> def welcome(name: str, age: int=15) -> None:
...     print(f'Welcome {name}. You are {age} years old.')
...
>>> welcome(name='Mike')
Welcome Mike. You are 15 years old.
>>> welcome(age=12, name='Mike')
Welcome Mike. You are 12 years old.
>>> welcome(12, 'Mike')
Welcome 12. You are Mike years old.
```

### Đối số bắt buộc và đối số mặc định

```python
>>> def multiply(x: int, y: int=5) -> int:
...     return x * y
...
>>> multiply(5)
25
```

### `*args` và `**kwargs`

```python
>>> def any_args(*args):
...     print(args)
...
>>> any_args(1, 2, 3)
(1, 2, 3)
>>> any_args(1, 2, 'Mike', 4)
(1, 2, 'Mike', 4)
```

```python
>>> def one_required_arg(required, *args):
...     print(f'{required=}')
...     print(args)
...
>>> one_required_arg('Mike', 1, 2)
required='Mike'
(1, 2)
```

```python
>>> def any_keyword_args(**kwargs):
...     print(args)
...
>>> any_keyword_args(one=1, two=2, three=3)
{'one': 1, 'two': 2, 'three': 3}
```

```python
>>> def arg_inspector(*args, **kwargs):
...     print(f'args are of type {type(args)}')
...     print(f'kwargs are of type {type(kwargs)}')
...
>>> arg_inspector(1, 2, 3, x='test', y=5)
args are of type <class 'tuple'>
kwargs are of type <calss 'dict'>
```

```python
>>> def output(*args, **kwargs):
...     print(f'{args=}')
...     print(f'{kwargs=}')
...
>>> my_tuple = (1, 2, 3)
>>> my_dict = {'one': 1, 'two': 2}
>>> output(*my_tuple)
args=(1, 2, 3)
kwargs={}
>>> output(**my_dict)
args=()
kwargs={'one': 1, 'two': 2}
>>> output(*my_tuple, **my_dict)
args=(1, 2, 3)
kwargs={'one': 1, 'two': 2}
```

### Tham số chỉ truyền theo vị trí hoặc chỉ truyền theo tên

```python
>>> def positional(name, age, /, a, b, *, key):
...     print(name, age, a, b, key)
...
>>> positional('Mike', 17, 2, b=3, key=test)
Mike 17 2 3 test
```

- Các tham số trước `/` là các tham số chỉ truyền theo vị trí, trong trưởng hợp này là `name` và `age`.
- Các tham số trước `*` là các tham số thông thường (có thể truyền theo vị trí hoặc theo tên), trong trường hợp này là `a` và `b`.
- Các tham số sau `*` là các tham số chỉ được truyền theo tên, trong trường hợp này là `key`.

## Phạm vi của biến

```python
>>> name = 'Mike'
>>> def welcome(name):
...     print(f'Welcome {name}')
...
>>> welcome('Nick')
Welcome Nick
>>> name
'Mike'
```

```python
>>> def add():
...     a = 2
...     b = 4
...     return a + b
...
>>> def subtract():
...     a = 3
...     return a - b
...
>>> add()
6
>>> subtract()
NameError: name 'b' is not defined
```

```python
>>> def add():
...     global b
...     a = 2
...     b = 4
...     return a + b
...
>>> def subtract():
...     a = 3
...     return a - b
...
>>> add()
6
>>> subtract()
-1
```
