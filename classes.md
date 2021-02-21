# Các class

## Tạo class

```python
class Ball:
    pass
```

```python
class Ball:

    def __init__(self, color, size, weight):
        """Initializer"""
        self.color = color
        self.size = size
        self.weight = weight
```

Tạo đối tượng từ class:

```python
>>> beach_ball = Ball('red', 15, 1)
>>> print(beach_ball)
<__main__.Ball object at 0x101f5a040>
>>> print(f'My ball is {beach_ball.color} and weighs {beach_ball.weight} lb')
My ball is red and weighs 1 lb
```

## Tạo phương thức

```python
# ball.py

class Ball:

    def __init__(self, color: str, size: float, weight: float, ball_type: str) -> None:
        self.color = color
        self.size = size
        self.weight = weight
        self.ball_type = ball_type

    def bounce(self):
        if self.ball_type.lower() == 'bowling':
            print("Bowling balls can't bounce!")
        else:
            print(f"The {self.ball_type} ball is bouncing!")

if __name__ == "__main__":
    ball_one = Ball('black', 6, 12, 'bowling')
    ball_two = Ball('red', 12, 1, 'beach')

    ball_one.bounce()
    ball_two.bounc()
```

```bash
python ball.py
Bowling balls can't bounce!
The beach ball is bouncing!
```

## Phương thức/thuộc tính public và private

Python không hỗ trợ thuộc tính private, tất cả là public.

Có quy ước là, thuộc tính/phương thức có tên bắt đầu bằng một hoặc hai dấu `_` được xem là private và không nên sử dụng bên ngoài class.

Các thuộc tính hoặc phương thức bắt đầu và kết thúc bằng hai dấu `_` được gọi là "magic method" hoặc "dunder method".

## Tạo lớp con

```python
# ball.py
class Ball:
    
    def __init__(self, color: str, size: float, weight: float, ball_type: str) -> None:
        self.color = color
        self.size = size
        self.weight = weight
        self.ball_type = ball_type

    def bounce(self):
        if self.ball_type.lower() == 'bowling':
            print("Bowling balls can't bounce!")
        else:
            print(f"The {self.ball_type} ball is bouncing!")
```

```python
# bowling_ball.py
from ball import Ball

class BowlingBall(Ball):

    def roll(self):
        print(f'You are rolling the {self.ball_type} ball')

if __name__ == '__main__':
    ball = BowlingBall('green', 10, 15, 'bowling')
    ball.roll()
```

Khi chạy `bowling_ball.py`:

```bash
You are rolling the bowling ball
```

## Biểu diễn một đối tượng

```python
class Ball:

    def __init__(self, color: str, size: float, weight: float, ball_type: str) -> None:
        self.color = color
        self.size = size
        self.weight = weight
        self.ball_type = ball_type

    def bounce(self):
        if self.ball_type.lower() == 'bowling':
            print("Bowling balls can't bounce!")
        else:
            print(f"The {self.ball_type} ball is bouncing!")

    def __repr__(self):
        return f"<Ball: {self.color} {self.ball_type} ball>"

if __name__ == '__main__':
    ball_one = Ball('black', 6, 12, 'bowling')
    ball_two = Ball('red', 12, 1, 'beach')

    print(ball_one)
    print(ball_two)
```

Khi chạy chương trình trên:

```bash
<Ball: black bowling ball>
<Ball: red beach ball>
```

Bạn có thể dùng `__str__` thay cho `__repr__`.
