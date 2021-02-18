# Kiểu số

## Tạo

Tạo số nguyên

```python
>>> my_integer = 3
>>> my_integer = int(3)
>>> int('10', 2)
2
>>> int('101', 2)
5
```

Tạo số thực

```python
>>> my_float = 2.0
>>> my_float = float(2.0)
>>> my_float = float("2.0")
```

Tạo số phức

```python
>>> comp = 1 + 2j
>>> type(comp)
<class 'complex'>
>>> comp.real
1.0
>>> comp.imag
2.0
>>> complex(10, 12)
(10+12j)
```

## Các toán tử số học

| Toán tử | Kết quả |
|---------|---------|
| a + b | Tổng của a và b|
| a - b | Hiệu của a và b|
| a * b | Tích của a và b|
| a / b | Thương của a và b|
| a // b | Thương đã làm tròn xuống của a và b |
| a % b | Số dư của a / b |
| -a | Số đối của a |
| +a | a |
| abs(a) | Trị tuyệt đối của a |
| int(a) | a được chuyển thành số nguyên |
| float(x) | x được chuyển thành số thực |
| complex(re, im) | Số phức với phần thực re và phần ảo im |
| c.conjugate() | Số phức liên hợp của c |
| divmod(a, b) | Cặp: (a // b, a % b) |
| pow(a, b) | a mũ b |
| a ** b | a mũ b |

Danh sách và giải thích chi tiết ở đây: [https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)

## Augmented Assignment

Danh sách: `+=`, `-=`, `*=`, `/=`, `%=`, `**=`, `<<=`, `>>=`, `&=`, `^=`, `|=`

Cách sử dụng:

```python
>>> x = 1
>>> x += 2
>>> x
3
```
