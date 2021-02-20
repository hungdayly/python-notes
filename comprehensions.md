# Comprehensions

## Danh sách

### Tạo danh sách

```python
>>> sequence = [1, 2, 3]
>>> new_list = [x * 2 for x in sequence]
>>> new_list
[2, 4, 6]
```

tương đương với:

```python
>>> sequence = [1, 2, 3]
>>> new_list = []
>>> for x in sequence:
...     new_list.append(x * 2)
...
>>> new_list
[2, 4, 6]
```

### Lọc danh sách

```python
>>> odd_numbers = [x for x in range(10) if x % 2]
>>> odd_numbers
[1, 3, 5, 7, 9]
```

tương đương với:

```python
>>> odd_numbers = []
>>> for x in range(10):
...     if x % 2:
...         odd_numbers.append(x)
```

```python
>>> my_dict = {1: 'dog', 2: 'cat', 3: 'python'}
>>> [(num, animal) for num in my_dict for animal in my_dict.values() if my_dict[num] == animal]
[(1, 'dog'), (2, 'cat'), (3, 'python')]
```

tương đương với:

```python
>>> my_dict = {1: 'dog', 2: 'cat', 3: 'python'}
>>> my_list = []
>>> for num in my_dict:
...     for animal in my_dict.values():
...         if my_dict[num] == animal:
...             my_list.append((num, animal))
...
>>> my_list
[(1, 'dog'), (2, 'cat'), (3, 'python')]
```

### Comprehension lồng nhau

```python
>>> matrix = [[9, 8, 7], [6, 5, 4], [3, 2, 1]]
>>> [[element * 2 for element in row] for row in matrix]
[[18, 16, 14], [12, 10, 8], [6, 4, 2]]
```

## Từ điển

```python
>>> {key: value for key, value in enumerate('abcde')}
{0: 'a', 1: 'b', 2: 'c', 3: 'd', 4: 'e'}
```

## Tập hợp

```python
>>> my_list = list('aaabbcde')
>>> my_list
['a', 'a', 'a', 'b', 'b', 'c', 'd', 'e']
>>> my_set = {item for item in my_list}
>>> my_set
{'d', 'e', 'c', 'b', 'a'}
```
