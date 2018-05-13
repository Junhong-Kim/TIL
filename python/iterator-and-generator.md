## Iterator
> `collection(list, tuple, set, dictionary)`, `문자열` 등은 `for`문을 사용해서 데이터를 하나씩 처리할 수 있습니다.   
이 처럼 데이터를 하나씩 처리할 수 있는 `collection`이나 `sequence`를 `Iterable Object`라고 부릅니다.

```py
# List iterable
for n in [1, 2, 3, 4, 5]:
  print(n)

# String Iterable
for c in 'HelloWorld':
  print(c)
```

파이썬 built-in 함수 `iter()`는 `iter([iterable_object])`로 사용하며 Iterable Object의 `iterator`를 리턴합니다.   
Iterable Object에서 실제 Iteration을 실행하는 것은 `iterator`이고 iterator는 `next()`를 사용하여 다음 `element`를 가져옵니다.  
만약, 더 이상 `next()` 요소가 없을 경우 `StopIteration Exception`을 발생시킵니다.

```py
my_list = [1, 2, 3]
i = iter(my_list)

print(next(i))
# 1
print(next(i))
# 2
print(next(i))
# 3
print(next(i))
# Traceback (most recent call last):
#   File "exp-iterator.py", line 10, in <module>
#     print(next(i))
# StopIteration
```

## Generator
> `Generator`는 Iterator의 특수한 형태입니다. Generator 함수는 함수 안에 `yield`를 사용하여 데이터를 하나씩 리턴합니다.
Generator 함수가 호출되면 함수 실행 중 처음으로 만나는 `yield`에서 값을 리턴합니다.  
이후 Generator 함수가 호출되면 직전에 실행되었던 `yield`문에서 부터 다음 `yield`문을 만날때 까지 실행합니다.  
이러한 `Generator` 함수를 변수에 할당하면 그 변수는 `generator 클래스 객체`가 됩니다. 

```py
# Generator 함수
def gen():
    yield 1
    yield 2
    yield 3


if __name__ == '__main__':
    # Generator 객체
    g = gen()
    print(type(g))
    # <class 'generator'>

    print(next(g))
    # 1
    print(next(g))
    # 2
    print(next(g))
    # 3

    for i in gen():
        print(i)
    # 1
    # 2
    # 3
```

## Refernces
http://pythonstudy.xyz/python/article/23-Iterator%EC%99%80-Generator
