# Xử lý ngoại lệ

## Các ngoại lệ phổ biến

- `Exception`: ngoại lệ cơ bản, tất cả các ngoại lệ khác thừa kế từ nó
- `AttributeError`: xảy ra khi tham chiếu hoặc gán giá trị tới một thuộc tính thất bại
- `ImportError`: lỗi xảy ra trong quá trình import khi không tìm thấy định nghĩa module hoặc không tìm thấy các thành viên của module khi sử dụng `from...import`
- `ModuleNotFoundError`: lớp con của `ImportError`, xảy ra khi không tìm thấy module
- `IndexError`: truy cập các phần tử có chỉ số ngoài khoảng cho phép
- `KeyError`: không tìm thấy key trong một từ điển
- `KeyboardInterrupt`: xảy ra khi người dùng bấm `Control-C` hoặc `Delete`
- `NameError`: không tìm thấy tên cục bộ hoặc tên toàn cục
- `OSError`:  lỗi liên quan hệ thống
- `RuntimeError`: lỗi thực thi chung, không thuộc bất kỳ kiểu lỗi nào khác
- `SyntaxError`: lỗi cú pháp
- `TypeError`: Kiểu dữ liệu không phù hợp
- `ValueError`: Giá trị không phù hợp
- `ZeroDivisionError`: Lỗi chia cho không

## Xử lý ngoại lệ

Cú pháp cơ bản:

```python
try:
    # Mã mà có thể gây ra ngoại lệ
except:
    # Mã chạy khi có ngoại lệ xuất hiện
```

```python
try:
    with open('example.txt') as file_handler:
        for line in file_handler:
            print(line)
except:
    print('An arror occurred')            
```

Có thể có nhiều khối `except`, mỗi khi xử lý các kiểu ngoại lệ khác nhau:

```python
try:
    with open('example.txt') as file_handler:
        for line in file_handler:
            print(line)
    import something
except OSError:
    print('An error occurred')
except ImportError:
    print('Unknown import!')
```

Một khối `except` có thể xử lý một số kiểu ngoại lệ nhất định:

```python
try:
    with open('example.txt') as file_handler:
        for line in file_handler:
            print(line)
    import something
except (OSError, ImportError):
    print('An error occurred')
```

## Tạo ngoại lệ

Sử dụng hàm `raise` để chủ động tạo ra một ngoại lệ:

```python
try:
    raise ImportError
except ImportError:
    print('Caught an ImportError')
```

Một ngoại lệ được tạo thường đi kèm với một thông báo lỗi:

```python
>>> raise Exception('Something bad happened!')
Traceback (most recent call last):
Python Shell, prompt 1, line 1
builtins.Exception: Something bad happened!
```

Nếu không cung cấp thông báo, ngoại lệ sẽ trông như thế này:

```python
>>> raise Exception
Traceback (most recent call last):
Python Shell, prompt 2, line 1
builtins.Exception:
```

## Đối tượng ngoại lệ

Có thể lưu ngoại lệ như một đối tượng và truy cập các thuộc tính của nó:

```python
>>> try:
...     raise ImportError('Bad Import!')
... except ImportError as error:
...     print(type(error))
...     print(error.args)
...     print(error)
...
<class 'ImportError'>
('Bad Import!',)
Bad Import!
```

## Khối `finally`

Khối `finally` luôn chạy dù có ngoại lệ xảy ra hay không.

```python
>>> try:
...     1 / 0
... except ZeroDivisionError:
...     print('You can not divide by zero!')
... finally:
...     print('Cleaning up')
...
You can not divide by zero!
Clearning up
```

Có thể bỏ qua khối `except` mà `finally` vẫn chạy, nhưng ngoại lệ sẽ không được xử lý:

```python
>>> try:
...     1/0
... finally:
...     print('Cleaning up')
...
Cleaning up
Traceback (most recent call last):
Python Shell, prompt 6, line 2
builtins.ZeroDivisionError: division by zero
```

## Khối `else`

Khối `else` chỉ chạy khi không có ngoại lệ:

```python
>>> try:
...     print('This is the try block')
... except IOError:
...     print('An IOError has occurred')
... else:
...     print('This is the else block')
...
This is the try block
This is the else block
```

```python
>>> try:
...     raise IOError
...     print('This is the try block')
... except IOError:
...     print('An IOError has occurred')
... else:
...     print('This is the else block')
...
An IOError has occurred
```
