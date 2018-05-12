## 2차원 리스트 중복 제거
> 파이썬에서 2차원 리스트 중복을 제거하고 싶을 때가 있습니다.   
1차원 리스트는 `set()` 함수로 편리하게 중복을 제거할 수 있지만 2차원 리스트는 다릅니다.

## Example
```py
items = [[1, 2], [2, 1], [1, 3]]
print(items)
# [[1, 2], [2, 1], [1, 3]]

items = list(set([tuple(set(item)) for item in items]))
print(items)
# [(1, 2), (1, 3)]

formatted = []
for item in itmes:
  formatted.append(str(item[0], str(item[1])))

print(formatted)
# 1-2,1-3
```

## Description
```py
  items = [[1, 2], [2, 1], [1, 3]]

  print(set(items[0]))
  # {1, 2}
  print(tuple(set(items[0])))
  # (1, 2)
  print([item for item in items])
  # [[1, 2], [2, 1], [1, 3]]
  print([set(item) for item in items])
  # [{1, 2}, {1, 2}, {1, 3}]
  print([tuple(set(item)) for item in items])
  # [(1, 2), (1, 2), (1, 3)]
  print(set([tuple(set(item)) for item in items]))
  # {(1, 2), (1, 3)}
  print(list(set([tuple(set(item)) for item in items])))
  # [(1, 2), (1, 3)]
```
1. `for item in items`
    - **for**문을 수행하여 **item**을 가져옵니다.
    - 현재 값: `[1, 2]`
2. `set(item)`
    - **item**을 순서없는 집합으로 만듭니다.
    - 현재 값: `{1, 2}`
3. `tuple(set(item))`:
    - **tuple**은 **변경할 수 없고 hashable하다**는 점을 이용해서 **list** 값을 **고유한 값**(tuple)으로 만듭니다.
    - 현재 값: `(1, 2)`
4. `[tuple(set(item)) for item in items]`
    - **list comprehension**의 결과로 **리스트**가 반환됩니다.
    - 현재 값: `[{1, 2}, {1, 2}, {1, 3}]`
5. `set([tuple(set(item)) for item in items])`
    - **tuple**로 이루어진 **list**를 `set()`를 통해 중복을 제거합니다.
    - 현재 값: `{{1, 2}, {1, 3}}`
6. `list(set([tuple(set(item)) for item in items]))`
    - **set** 타입을 **list** 타입으로 변환합니다.
    - 최종 값: `[{1, 2}, {1, 3}]`

## References
https://stackoverflow.com/questions/33423008/remove-duplicate-sets-from-lists  
https://stackoverflow.com/questions/14535730/what-do-you-mean-by-hashable-in-python  