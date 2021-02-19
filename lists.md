# Danh sách

## Tạo danh sách

```python
>>> my_list = [1, 2, 3]
>>> my_list
[1, 2, 3]
```

```python
>>> list_of_strings = list('abc')
>>> list_of_strings
['a', 'b', 'c']
```

```python
>>> empty_list = []
>>> empty_list
[]
>>> another_empty_list = list()
>>> another_empty_list
[]
```

## Các phương thức

Lấy danh sách các phương thức qua `dir(list)`:

```python
>>> dir(list)
['__add__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
```

Bỏ qua các "magic method", ta có các phương thức sau:

- `append()`
- `clear()`
- `copy()`
- `count()`
- `extend()`
- `index()`
- `insert()`
- `pop()`
- `remove()`
- `reverse()`
- `sort()`

Bạn có thể sử dụng `count()` để đếm số lần xuất hiện của một đối tượng trong danh sách.

```python
>>> my_list = list('abcc')
>>> my_list.count('a')
1
>>> my_list.count('c')
2
```

Phương thức `index()` tìm vị trí xuất hiện đầu tiên của một đối tượng trong danh sách.

```python
>>> my_list = list('abcc')
>>> my_list.index('c')
2
>>> my_list.index('a')
0
```

Phương thức `reverse()` đảo ngược thứ tự các phần tử của danh sách, nó làm thay đổi danh sách:

```python
>>> my_list = list('abcc')
>>> my_list.reverse()
>>> my_list
['c', 'c', 'b', 'a']
```

Bản thân `reverse()` trả về `None`:

```python
>>> x = my_list.reverse()
>>> print(x)
None
```

## Thêm vào danh sách

Phương thức `append()` thêm phần tử vào cuối danh sách có sẵn:

```python
>>> my_list = list('abcc')
>>> my_list
['a', 'b', 'c', 'c']
>>> my_list.append(1)
>>> my_list
['a', 'b', 'c', 'c', 1]
```

Bạn có thể sử dụng hàm tích hợp `len()` để biết số phần tử của một danh sách:

```python
>>> len(my_list)
5
```

Phương thức `insert()` cho phép chèn phần tử vào vị trí bất kỳ trong danh sách có sẵn:

```python
>>> my_list.insert(0, 'first')
>>> my_list
['first', 'a', 'b', 'c', 'c', 1]
```

Để thêm nhiều phần tử cùng lúc vào danh sách, sử dụng phương thức `extend()`:

```python
>>> my_list = [1, 2, 3]
>>> other_list = [4, 5, 6]
>>> my_list.extend(other_list)
>>> my_list
[1, 2, 3, 4, 5, 6]
```

Bạn có thể kết hợp hai danh sách bằng toán tử `+`:

```python
>>> my_list = [1, 2, 3]
>>> other_list = [4, 5, 6]
>>> combined = my_list + other_list
>>> combined
[1, 2, 3, 4, 5, 6]
```

Nên có một cách khác thay vì sử dụng `extend()` như sau:

```python
>>> my_list = [1, 2, 3]
>>> other_list = [4, 5, 6]
>>> my_list += other_list
>>> my_list
[1, 2, 3, 4, 5, 6]
```

## Truy cập và thay đổi phần tử của danh sách

```python
>>> my_list = [7, 8, 9]
>>> my_list[0]
7
>>> my_list[2]
9
>>> my_list[-1]
9
```

## Xóa phần tử khỏi danh sách

Sử dụng `clear()` sẽ xóa bỏ tất cả các phần tử khỏi danh sách:

```python
>>> my_list = [7, 8, 9]
>>> my_list.clear()
>>> my_list
[]
```

Phương thức `pop()` cho phép xóa phần tử ở vị trí cụ thể, nó trả về phần tử đã bị xóa:

```python
>>> my_list = [7, 8, 9]
>>> my_list.pop()
9
>>> my_list
[7, 8]
>>> my_list.pop(0)
7
>>> my_list
[8]
```

Phương thức `remove()` cho phép xóa một phần tử cụ thể:

```python
>>> my_list = [7, 8, 9]
>>> my_list.remove(8)
>>> my_list
[7, 9]
```

Có thể dùng từ khóa `del` để xóa một phần tử khỏi danh sách:

```python
>>> my_list = [7, 8, 9]
>>> del my_list[1]
>>> my_list
[7, 9]
```

## Sắp xếp danh sách

```python
>>> my_list = [4, 10, 2, 1, 23, 9]
>>> my_list.sort()
>>> my_list
[1, 2, 4, 9, 10, 23]
```

Phương thức `.sort()` thay đổi danh sách và không trả về gì. Muốn tạo một phiên bản đã sắp xếp của một danh sách, có thể sử dụng hàm tích hợp sẵn là `sorted()`:

```python
>>> my_list = [4, 10, 2, 1, 23, 9]
>>> sorted_list = sorted(my_list)
>>> sorted_list
[1, 2, 4, 9, 10, 23]
```

Cả `.sort()` và `sorted()` đều chấp nhận đối số thứ hai là `reverse`. Mặc định `reverse=False`, nếu `reverse=True` thì thứ tự sắp xếp là giảm dần.

```python
>>> my_list = [4, 10, 2, 1, 23, 9]
>>> sorted_list = sorted(my_list, reverse=True)
>>> sorted_list
[23, 10, 9, 4, 2, 1]
```

## Slicing

```python
>>> my_list = [4, 10, 2, 1, 23, 9]
>>> my_list[1:3]
[10, 2]
>>> my_list[-2:]
[23, 9]
>>> my_list[:3]
[4, 10, 2]
```

## Sao chép danh sách

Cách đơn giản nhất là sử dụng phương thức `.copy()`.

```python
>>> my_list = [1, 2, 3]
>>> new_list = my_list.copy()
>>> new_list
[1, 2, 3]
```

Cũng có thể sử dụng cú pháp sau để thay thế:

```python
>>> my_list = [1, 2, 3]
>>> new_list = my_list[:]
>>> new_list
[1, 2, 3]
```

Hoặc sử dụng hàm tích hợp `list()`:

```python
>>> my_list = [1, 2, 3]
>>> new_list = list(my_list)
>>> new_list
[1, 2, 3]
```

Tất cả các phương pháp này đều là "shallow copy".
