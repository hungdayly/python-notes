# Làm việc với chuỗi

## Tạo chuỗi

```python
name = 'Mike'
first_name = 'Mike'
last_name = "Driscoll"
triple = """multi-line
string"""
```

Có thể tạo chuỗi bằng hàm chuyển đổi `str()`:

```python
>>> number = 5
>>> str(number)
'5'
```

Trong Python, dấu backslash `\` được dùng để tạo các escape sequence. Đây là một số ví dụ:

- `\b` - backspace
- `\n` - line feed
- `\r` - carriage return
- `\t` - tab
- `\"` - dấu nháy kép
- `\'` - dấu nháy đơn
- `\\` - dấu backslash

## Các phương thức của chuỗi

Để lấy danh sách đầy đủ các phương thức của chuỗi, sử dụng `dir(str)`.

```python
>>> dir(str)
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'removeprefix', 'removesuffix', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
```

Các phương thức bắt đầu và kết thúc bằng hai dấu `_` được gọi là "dunder method" hay "magic method".

## Định dạng chuỗi

Có 3 cách để thực hiện định dạng chuỗi:

- Sử dụng `%`
- Sử dụng phương thức `.format()`
- Sử dụng f-strings

### Sử dụng `%`

```python
>>> age = 18
>>> print('You must be at least %s to continue' % age)
You must be at least 18 to continue
```

```python
>>> name = 'Mike'
>>> age = 18
>>> print('Hello %s. You must be at least %i to continue!' % (name, age))
Hello Mike. You must be at least 18 to continue!
```

```python
>>> name = 'Mike'
>>> age = 18
>>> print('Hello %(first_name)s. You must be at least %(age)i to continue!' % {'first_name': name, 'age': age})
Hello Mike. You must be at least 18 to continue!
```

### Sử dụng phương thức `.format()`

```python
>>> age = 18
>>> name = 'Mike'
>>> print('Hello {}. You must be at least {} to continue!'.format(name, age))
Hello Mike. You must be at least 18 to continue!
```

```python
>>> age = 18
>>> name = 'Mike'
>>> print('Hello {1}. You must be at least {0} to continue!'.format(age, name))
Hello Mike. You must be at least 18 to continue!
```

```python
>>> age = 18
>>> name = 'Mike'
>>> print('Hello {first_name}. You must be at least {age} to continue!'.format(first_name=name, age=age))
Hello Mike. You must be at least 18 to continue!
```

```python
>>> '{:<20}'.format('left aligned')
'left aligned'
>>> '{:>20}'.format('right aligned')
'       right aligned'
>>> '{:^20}'.format('centered')
'      centered      '
>>> '{example:^20}'.format(example='centered')
'      centered      '
```

### Sử dụng f-strings

```python
>>> name = 'Mike'
>>> age = 20
>>> f'Hello {name}. You are {age} years old'
'Hello Mike. You are 20 years old'
>>> f'{age+2}'
'22'
>>> f'{name.lower()}'
'mike'
```

```python
>>> sample_dict = {'name': 'Tom', 'age': 40}
>>> f'Hello {sample_dict["name"]}. You are {sample_dict["age"]} years old'
'Hello Tom. You are 40 years old'
```

```python
>>> username = 'jdoe'
>>> f'Your {username=}'
"Your username='jdoe'"
```

## Nối chuỗi

```python
>>> first_string = 'My name is '
>>> second_string = 'Mike'
>>> first_string + second_string
'My name is Mike'
```

```python
>>> first_string = 'My name is'
>>> second_string = 'Mike'
>>> ' '.join([first_string, second_string])
'My name is Mike'
>>> '--'.join([first_string, second_string])
'My name is--Mike'
```

## Slicing

```python
>>> 'this is a string'[0:4]
'this'
>>> 'this is a string'[:4]
'this'
>>> 'this is a string'[-4:]
'ring'
```
