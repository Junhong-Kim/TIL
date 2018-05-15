## args
> `*args` 처럼 매개변수명 앞에 `*`을 붙이면 입력 값을 모아 `tuple`로 만듭니다.
```py
def func(*args):
    total = 0
    for arg in args:
        total = total + arg
    return total


print(func(1, 2, 3))
# 6
print(func(1, 2, 3, 4, 5))
# 15
```
첫 번째 `func(1, 2, 3)`은 args를 `(1, 2, 3)`로 만듭니다.  
두 번째 `func(1, 2, 3, 4, 5)`은 args를 `(1, 2, 3, 4, 5)`로 만듭니다.  

## kwargs
> `**kwargs`는 함수의 인수로 `key=value` 형태를 주었을 때 입력 값 전체가 `kwargs`라는 `dict`에 저장 됩니다.
```py
def func(**kwargs):
    print(kwargs)


func(x=1)
# {'x': 1}
```

## args and kwargs
> 일반적인 입력은 `args`의 `tuple`로 저장되고 `name='foo', age=3` 같은 형태는 `kwargs`의 `dict`로 저장됩니다.
```py
def func(*args, **kwargs):
    print(args)
    print(kwargs)


func(1, 2, 3, 4, name='foo', age=3)
# (1, 2, 3, 4)
# {'name': 'foo', 'age': 3}
```

> **Note:**  
키워드 형태의 인수 뒤에 키워드 형태가 아닌 인수는 올 수 없습니다.
```py
func(1, 2, 3, name='foo', age=3, 4)
#   File "example.py", line 28
#     func(1, 2, 3, name='foo', age=3, 4)
#                                     ^
# SyntaxError: positional argument follows keyword argument
```

## References
https://wikidocs.net/24
