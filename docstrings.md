# Docstrings

Một docstring được tạo bởi ba dấu nháy.

```python
"""
This is a docstring
with multiple lines
"""
```

Docstring bị bỏ qua bởi Python. Chúng không thể chạy. Tuy nhiên khi bạn sử dụng docstring như câu lệnh đầu tiên của một module, hàm, ... chúng sẽ trở thành một thuộc tính đặc biệt có tên là `__doc__`. 

Đây là ví dụ về một docstring được tạo trong một hàm:

```python
def my_function():
    """This is the function's docstring"""
```

>__Chú ý__: Ba dấu nháy kép được khuyến khích sử dụng, nhưng ba dấu nháy đơn, một dấu nháy kép và một dấu nháy đơn cũng hoạt động.