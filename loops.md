# Các vòng lặp

## Vòng lặp `for`

Cú pháp chung:

```python
for x in iterable:
    # do something
```

Các ví dụ:

```python
>>> my_list = [1, 2, 3]
>>> for item in my_list:
...     print(item)
...
1
2
3
```

```python
>>> my_list = [1, 2, 3]
>>> for item in my_list:
...     if item % 2 == 0:
...         print(f'{item} is even')
...
2 is even
```

## Các trường hợp thường dùng

### Lặp qua chuỗi

```python
>>> my_str = 'abcdefg'
>>> for letter in my_str:
...     print(letter)
...
a
b
c
d
e
f
g
```

### Lặp qua từ điển

Mặc định các khóa được lặp:

```python
>>> users = {'mdriscoll': 'password', 'guido': 'python', 'steve': 'guac', 'ethanf': 'enum'}
>>> for user in users:
...     print(user)
...
mdriscoll
guido
steve
ethanf
```

Lặp qua cả khóa và giá trị thì cần sử dụng phương thức `.items()`:

```python
>>> users = {'mdriscoll': 'password', 'guido': 'python', 'steve': 'guac', 'ethanf': 'enum'}
>>> for user, password in users.items():
...     print(f"{user}'s password is {password}")
...
mdriscoll's password is password
guido's password is python
steve's password is guac
ethanf's password is enum
```

### Lặp qua danh sách các tuple

```python
>>> list_of_tuples = [(1, 'banana'), (2, 'apple'), (3, 'pear')]
>>> for item in list_of_tuples:
...     print(item)
...
(1, 'banana')
(2, 'apple')
(3, 'pear')
>>> for number, fruit in list_of_tuples:
...     print(f'{number} - {fruit}')
...
1 - banana
2 - apple
3 - pear
```

### Sử dụng `enumerate`

`enumerate` nhận một iterable và trả về một tuple có dạng `(count, item)`.

```python
>>> my_str = 'abcdefg'
>>> for pos, letter in enumerate(my_str):
...     print(f'{pos} - {letter}')
...
0 - a
1 - b
2 - c
3 - d
4 - e
5 - f
6 - g
```

## Vòng lặp `while`

```python
>>> count = 0
>>> while count < 10:
...     print(count)
...     count += 1
```

## Thoát khỏi vòng lặp

```python
>>> count = 0
>>> while count < 10:
...     if count == 4:
...         print(f'{count=}')
...         break
...     print(count)
...     count += 1
...
0
1
2
3
count=4
```

```python
>>> list_of_tuples = [(1, 'banana'), (2, 'apple'), (3, 'pear')]
>>> for number, fruit in list_of_tuples:
...     if fruit == 'apple':
...         print('Apple found!')
...         break
...     print(f'{number} - {fruit}')
...
1 - banana
Apple found!
```

## Sử dụng `continue`

`continue` sẽ dừng ngay lần lặp hiện tại và nhảy sang lần lặp tiếp theo.

```python
>>> for number in range(2, 12):
...     if number % 2 == 0:
...         continue
...     print(number)
...
3
5
7
9
11
```

## Sử dụng mệnh đề `else` của vòng lặp

Mệnh đề `else` chỉ chạy nếu vòng lặp kết thúc một cách bình thường (không gặp `break`).

```python
>>> my_list = [1, 2, 3]
>>> for number in my_list:
...     if number == 4:
...         print('Found number 4!')
...         break
... else:
...     print('Number 4 not found')
...
1
2
3
Number 4 not found
```

## Vòng lặp lồng nhau

```python
>>> nested = [['mike': 12], ['jan', 15], ['alice', 8]]
>>> for lst in nested:
...     print(f'List = {lst}')
...     for item in lst:
...         print(f'Item -> {item}')
...
List = ['mike', 12]
Item -> mike
Item -> 12
List = ['jan', 15]
Item -> jan
Item -> 15
List = ['alice', 8]
Item -> alice
Item -> 8
```
