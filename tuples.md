# Tuple

## Tạo các tuple

```python
>>> tuple_1 = 4,5
>>> type(tuple_1)
<class 'tuple'>
>>> tuple_2 = (2, 3, 4)
>>> type(tuple_2)
<class 'tuple'>
>>> tuple_3 = 5,
>>> type(tuple_3)
<class 'tuple'>
>>> tuple_4 = (5,)
>>> type(tuple_4)
<class 'tuple'>
>>> not_a_tuple = (5)
>>> type(not_a_tuple)
<class 'int'>
```

```python
>>> a_tuple = tuple(['1', '2', '3'])
>>> type(a_tuple)
<class 'tuple'>
```

Tạo tuple trống:

```python
>>> empty = tuple()
>>> len(empty)
0
>>> type(empty)
<class 'tuple'>
>>> also_empty = ()
>>> len(also_empty)
0
```



## Làm việc với các tuple

Ngoại trừ các magic method, chỉ có hai phương thức đối với một tuple:

- `count()`
- `index()`

```python
>>> a_tuple = (1, 2, 3, 3)
>>> a_tuple.count(3)
2
>>> a_tuple.index(2)
1
```

Chỉ có thể truy cập nhưng không thể thay đổi một phần tử của tuple:

```python
>>> a_tuple = (1, 2, 3, 3)
>>> a_tuple[2]
3
>>> a_tuple[0] = 8
TypeError: 'tuple' object does not support item assignment
```

## Nối các tuple

```python
>>> a_tuple = (1, 2, 3, 4)
>>> id(a_tuple)
140617302751760
>>> a_tuple += (6, 7)
>>> id(a_tuple)
140617282270944
```

