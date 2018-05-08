## String byte 크기
```py
def utf8len(s):
    return len(s.encode('utf-8'))

print(utf8len('123456789'))

# Output:
# 9
```
