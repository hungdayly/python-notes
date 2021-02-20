# Các toán tử lôgic và `None`

Trong Python, `False` được xem là `0` và `True` được xem là `1`.

```python
>>> True == 1
True
>>> False == 0
True
>>> False == True
False
```

## Hàm `bool()`

Hàm `bool()` cho phép chuyển một giá trị sang kiểu lôgic.

Chuỗi trống `''` được chuyển thành `False`, các chuỗi không trống được chuyển thành `True`:

```python
>>> bool('1')
True
>>> bool('2')
True
>>> bool('0')
True
>>> bool('')
False
```

Các số khác không đều được chuyển thành `True`, số "không" được chuyển thành `False`.

```python
>>> bool(1.0)
True
>>> bool(3.14)
True
>>> bool(0)
False
>>> bool(0.0)
False
```

Đối với các kiểu dữ liệu như danh sách, tuple, từ điển, tập hợp..., nó được chuyển thành `False` khi không có phần tử nào, thành `True` nếu có ít nhất một phần tử.

```python
>>> bool([])
False
>>> bool(['something'])
True
>>> bool({})
False
>>> bool({1: 'one'})
True
>>> bool(12)
True
```

## Giá trị `None`

`None` một mình tạo nên một kiểu dữ liệu riêng là `NoneType`. So sánh `None` với mọi giá trị khác nó đều trả về `False`:

```python
>>> None == 1
False
>>> None == []
False
>>> None == ''
False
>>> None == None
True
```

Có thể gán `None` cho một biến. Mọi biến được gán cho giá trị `None` đều tham chiếu tới một đối tượng `None` duy nhất trong bộ nhớ. `None` không được in ra trong Python Shell.

```python
>>> x = None
>>> y = None
>>> x
>>> id(x)
4478513256
>>> id(y)
 4478513256
>>> x is None
True
>>> y is None
True
```
