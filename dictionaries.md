# Kiểu từ điển

## Tạo từ điển

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict
{'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> numbers = dict(one=1, two=2, three=3)
>>> numbers
{'one': 1, 'two': 2, 'three': 3}
>>> info_list = [('first_name', 'James'), ('last_name', 'Doe'), ('email', 'jdoe@gmail.com')]
>>> info_dict = dict(info_list)
>>> info_dict
{'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoes@gmail.com'}
```

## Truy cập

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict['first_name']
'James'
```

Kiểm tra từ điển có một khóa nào đó không:

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> 'address' in sample_dict
False
>>> 'address' not in sample_dict
True
>>> 'first_name' in sample_dict
True
```

## Các phương thức

Phương thức `.get()`:

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> print(sample_dict.get('address'))
None
>>> print(sample_dict.get('address', 'Not Found'))
Not Found
```

Phương thức `.clear()`:

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict
{'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict.clear()
>>> sample_dict
{}
```

Phương thức `.copy()`: tạo phiên bản shallow copy của một từ điển

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> copied_dict = sample_dict.copy()
>>> copied_dict
{'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
```

Phương thức `.items()`:

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict.items()
dict_items([('first_name', 'James'), ('last_name', 'Doe'), ('email', 'jdoe@gmail.com')])
```

Phương thức `.keys()`:

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> keys = sample_dict.keys()
>>> keys
dict_keys(['first_name', 'last_name', 'email'])
>>> 'email' in keys
True
>>> len(keys)
3
```

Phương thức `.values()`:

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> values = sample_dict.values()
>>> values
dict_values(['James', 'Doe', 'jdoe@gmail.com'])
>>> 'Doe' in values
True
>>> len(values)
3
```

Phương thức `.pop()`: xóa một khóa khỏi từ điển

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict.pop('something')
Traceback (most recent call last):
Python Shell, prompt 146, line 1
builtins.KeyError: 'something'
>>> sample_dict.pop('something', 'Not found!')
'Not found!'
>>> sample_dict.pop('first_name')
'James'
>>> sample_dict
{'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
```

Phương thức `.popitem()`: xóa và trả về cặp `(key, value)` khỏi từ điển

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict.popitem()
('email', 'jdoe@gmail.com')
>>> sample_dict
{'first_name': 'James', 'last_name': 'Doe'}
```

Phương thức `.update()`:

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict.update([('something', 'else')])
>>> sample_dict
{'first_name': 'James',
'last_name': 'Doe',
'email': 'jdoe@gmail.com',
'something': 'else'}
```

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict.update([('first_name', 'Mike')])
>>> sample_dict
{'first_name': 'Mike', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
```

## Chỉnh sửa từ điển

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict['address'] = '123 Dunn St'
>>> sample_dict
{'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com', 'address': '123 Dunn St'}
```

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict['email'] = 'jame@doe.com'
>>> sample_dict
{'first_name': 'James', 'last_name': 'Doe', 'email': 'jame@doe.com'}
```

## Xoá phần tử khỏi từ điển

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> del sample_dict['email']
>>> sample_dict
{'first_name': 'James', 'last_name': 'Doe'}
```

```python
>>> sample_dict = {'first_name': 'James', 'last_name': 'Doe', 'email': 'jdoe@gmail.com'}
>>> sample_dict.pop('email')
'jdoe@gmail.com'
>>> sample_dict
{'first_name': 'James', 'last_name': 'Doe'}
```
