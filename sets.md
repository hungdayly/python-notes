# Tập hợp

Có hai kiểu tập hợp:

- `set` - có thể thay đổi
- `frozenset` - không thể thay đổi

Ở đây chúng ta tập chung vào kiểu `set`.

## Tạo tập hợp

```python
>>> my_set = {"a", "b", "c", "c"}
>>> my_set
{'c', 'a', 'b'}
>>> type(my_set)
<class 'set'>
```

Tạo bằng `set`:

```python
>>> my_list = [1, 2, 3, 4]
>>> my_set = set(my_list)
>>> my_set
{1, 2, 3, 4}
>>> type(my_set)
<class 'set'>
```

## Truy cập phần tử của tập hợp

Ta có thể kiểm tra một phần tử có thuộc tập hợp không:

```python
>>> my_set = {"a", "b", "c", "c"}
>>> "a" in my_set
True
```

Tập hợp không hỗ trợ truy cập từng phần tử riêng biệt. Thay vì vậy, bạn phải sử dụng vòng lặp.

```python
>>> my_set = {"a", "b", "c", "c"}
>>> for item in my_set
...    print(item)
...
c
a
b
```

## Thay đổi phần tử

Bạn không thể thay đổi phần tử của một tập hợp.

## Thêm phần tử vào tập hợp

Có hai cách:

- `.add()`
- `.update()`

```python
>>> my_set = {"a", "b", "c", "c"}
>>> my_set.add('d')
>>> my_set
{'d', 'c', 'a', 'b'}
```

```python
>>> my_set = {"a", "b", "c", "c"}
>>> my_set.update(['d', 'e', 'f'])
>>> my_set
{'a', 'c', 'd', 'e', 'b', 'f'}
```

`.update()` có thể chấp nhận một danh sách, một tuple hoặc một tập hợp khác.

## Xóa phần tử khỏi tập hợp

Có thể sử dụng:

- `.remove()`
- `.discard()`
- `.pop()`
- `.clear()`

```python
>>> my_set = {"a", "b", "c", "c"}
>>> my_set.remove('a')
>>> my_set
{'c', 'b'}
```

`.remove()` báo lỗi khi xóa một phần tử không tồn tại.

```python
>>> my_set = {"a", "b", "c", "c"}
>>> my_set.discard('b')
>>> my_set
{'c', 'a'}
```

`.discard()` không báo lỗi khi xóa một phần tử không tồn tại.

```python
>>> my_set = {"a", "b", "c", "c"}
>>> my_set.pop()
'c'
>>> my_set
{'a', 'b'}
```

`.pop()` báo lỗi khi áp dụng cho một tập hợp rỗng.

Để làm trống một tập hợp, sử dụng `.clear()`:

```python
>>> my_set = {"a", "b", "c", "c"}
>>> my_set.clear()
>>> my_set
set()
```

## Xóa tập hợp

```python
>>> my_set = {"a", "b", "c", "c"}
>>> del my_set
>>> my_set
Traceback (most recent call last):
Python Shell, prompt 227, line 1
builtins.NameError: name 'my_set' is not defined
```

## Các phép toán đối với tập hợp

- `.union()`: lấy hợp của hai tập hợp và trả về một tập hợp mới.
- `.intersection()`: lấy giao của hai tập hợp và trả về một tập hợp mới.
- `.difference()`: lấy hiệu của hai tập hợp và trả về một tập hợp mới.

```python
>>> first_set = {'one', 'two', 'three'}
>>> second_set = {'orange', 'banana', 'peach'}
>>> united_set =  first_set.union(second_set)
>>> united_set
{'two', 'banana', 'three', 'peach', 'orange', 'one'}
>>> first_set
{'two', 'three', 'one'}
```

```python
>>> first_set = {'one', 'two', 'three'}
>>> second_set = {'orange', 'banana', 'peach', 'one'}
>>> intersection = first_set.intersection(second_set)
>>> intersection
{'one'}
```

```python
>>> first_set = {'one', 'two', 'three'}
>>> second_set = {'three', 'four', 'one'}
>>> first_set.difference(second_set)
{'two'}
>>> second_set.difference(first_set)
{'four'}
```
