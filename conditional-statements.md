# Các lệnh điều kiện

## Các toán tử so sánh

- `>`: lớn hơn
- `>=`: lớn hơn hoặc bằng
- `<`: nhỏ hơn
- `<=`: nhỏ hơn hoặc bằng
- `==`: bằng nhau
- `!=`: khác nhau

```python
>>> a = 2
>>> b = 3
>>> a == b
False
>>> a > b
False
>>> a < b
True
>>> a >= b
False
>>> a <= b
True
>>> a != b
True
```

## Các câu lệnh điều kiện

### Câu lệnh điều kiện
```python
>>> authenticated = True
>>> if authenticated:
...    print('You are logged in')
...
You are logged in
```

### Câu lệnh rẽ nhánh

```python
>>> authenticated = False
>>> if authenticated:
...    print('You are logged in')
... else:
...    print('Please login')
...
Please login
```

### Câu lệnh rẽ nhánh nhiều điều kiện

```python
>>> age = 10
>>> if age < 18:
...    print('You can follow the elections on the news')
... elif age < 35:
...    print('You can vote in all elections')
... elif age >= 35:
...    print('You can stand for any election')
...
You can follow the elections on the news
```

### Các điều kiện lồng nhau

```python
>>> age = 18
>>> car = 'Ford'
>>> if age >= 18:
...    if car in ['Honda', 'Toyota']:
...        print('You buy Japanese cars')
...    elif car in ['Ford', 'Chevrolet']:
...        print('You buy American cars')
... else:
...    print('You are too young to buy cars!')
...
You buy American cars
```

## Các toán tử lôgic

- `and`
- `or`
- `not`

```python
>>> age = 18
>>> car = 'Ford'
>>> if age > 18 and car in ['Honda', 'Toyota']:
...     print('You buy Japanese cars')
... elif age >= 18 and car in ['Ford', 'Chevrolet']:
...     print('You buy American cars')
... else:
...     print('You are too young to buy cars!')
...
You buy American cars
```

`or` có độ ưu tiên thấp hơn `and` và `and` có độ ưu tiên thấp hơn `not`:

```python
>>> color = 'white'
>>> age = 10
>>> if age <= 14 and (color == 'white' or color == 'green'):
...     print(f'This milk is {age} days old and looks {color}')
... else:
...     print(f'You should not drink this {age} day old milk...')
...
This milk is 10 days old and looks white
```

## Các toán tử đặc biệt

- `is`: toán tử đồng nhất (kiểm tra id của hai đối tượng có bằng nhau không)
- `is not`: ngược với `is`
- `in`: kiểm tra một giá trị có nằm trong một tập (danh sách, tuple, từ điển, tập hợp...) không
- `not in`: ngược với `in`

Tất cả các toán tử này đều trả về `True` hoặc `False`.

```python
>>> x = [1, 2, 3]
>>> y = [1, 2, 3]
>>> x == y
True
>>> x is y
False
>>> id(x)
140328193994832
>>> id(y)
140328193887760
```

```python
>>> my_list = [1, 2, 3, 4]
>>> 5 not in my_list
True
```
