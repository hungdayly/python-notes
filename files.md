# Làm việc với file

## Hàm `open()`

Định nghĩa hàm:

```python
open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
```

Các `mode` khả dĩ:

| Kí tự | Ý nghĩa |
|-------|---------|
| `r` | chỉ đọc |
| `w` | ghi đè |
| `a` | ghi vào cuối |
| `b` | chế độ nhị phân |
| `t` | chế độ văn bản (mặc định) |
| `+` | đọc và ghi |

Các cách mở file:

```python
file_handler = open('example.txt')

file_handler.close()
```

```python
try:
    file_handler = open('example.txt')
except:
    # bỏ qua lỗi
    pass
finally:
    file_handler.close()
```
Cách tốt nhất là sử dụng `with`:

```python
with open('example.txt') as file_handler:
    data = file_handler.read()
```

Khi ra khỏi `with`, file tự động được đóng lại.

## Đọc file

```python
with open('example.txt') as file_handler:
    for line in file_handler:
        print(line)
```

```python
with open('example.txt') as file_handler:
    lines = file_handler.readlines()
    for line in lines:
        print(line)
```

Cách đầu tốt hơn vì không đọc toàn bộ các dòng cùng lúc, nó đọc từng dòng một, và không gây tràn bộ nhớ.

Nếu file tương đối nhỏ có thể đọc toàn bộ file và lưu vào bộ nhớ:

```python
with open('example.txt') as file_handler:
    file_contents = file_handler.read()
```

Cũng có thể đọc theo từng mảnh nhỏ với kích thước (tính theo byte) xác định:

```python
while True:
    with open('example.txt') as file_handler:
        data = file_handler.read(1024)
        if not data:
            break
        print(data)
```

## Đọc file nhị phân

Để đọc file dưới dạng nhị phân, thêm `mode` là `b`:

```python
with open('example.pdf', 'rb') as file_handler:
    file_contents = file_handler.read()
```

## Ghi file

- `w`: ghi file mới hoặc ghi đè file hiện tại
- `wb`: ghi/ghi đè dưới dạng nhị phân

```python
>>> with open('example.txt', 'w') as file_handler:
...     file_handler.write('This is a test')
```

Phương thức `write` ghi một chuỗi vào file, nên muốn xuống dòng bạn phải thêm `\n`.

Nếu muốn ghi nhiều dòng bạn phải sử dụng `writelines()`. Nó nhận một sequence các chuỗi. Bạn có thể sử dụng một danh sách các chuỗi và truyền vào `writelines()`.

## Di chuyển trong file

Sử dụng phương thức `.seek()` để di chuyển trong file, nó chấp nhận hai đối số:

- `offset`: số byte tính từ `whence`
- `whence`: điểm tham chiếu, có thể có các giá trị:
  - `0`: đầu file (mặc định)
  - `1`: vị trí hiện tại
  - `2`: cuối file

```python
>>> with open('example.txt') as file_handler:
...     file_handler.seek(4)
...     chunk = file_handler.read()
...     print(chunk)
...
is a test
```

## Thêm vào file

Sử dụng `mode` là `a` để thêm nội dung vào file mà không ghi đè nó.

```python
>>> with open('example.txt', 'a') as file_handler:
...     file_handler.write('Here is some more text')
```

## Xử lý ngoại lệ

```python
try:
    with open('example.txt') as file_handler:
        for line in file_handler:
            print(line)
except OSError:
    print('An error has occurred')
```
