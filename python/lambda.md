## Lambda
> `lambda`는 함수를 생성할 때 사용하는 예약어로 `def`와 동일한 역할을 한다. 
```py
lambda parameter1, parameter2, ..: expression statement
```

## Example
> `lambda` 예제
```py
ld = lambda x, y: x + y
print(ld(1, 2))
# 3
```
> `lambda` 예제와 동일한 `def` 예제
```py
def sum(x, y):
  return x + y

print(sum(1, 2))
# 3
```

> `def`가 있는데 `lambda`가 존재하는 이유
1. `lambda`는 `def` 보다 간결하게 함수를 정의할 수 있다.
2. `lambda`는 `def`를 사용할 수 없는 곳에서 사용할 수 있다.
```py
ld = [lambda x, y: x + y, lambda x, y: x * y]
print(ld)
# [<function <lambda> at 0x103abfe18>, <function <lambda> at 0x103ceb0d0>]
print(ld[0])
# <function <lambda> at 0x103abfe18>
print(ld[0](1, 2))
# 3
print(ld[1](1, 2))
# 2
```

## References
https://wikidocs.net/24