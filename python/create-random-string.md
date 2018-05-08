## 대문자와 숫자로 무작위 문자열 생성
```py
import random
import string

print(''.join(random.choice(string.ascii_uppercase + string.digits) for _ in range(8)))

# Output:
# IWQSYEV1
```

## References
https://stackoverflow.com/questions/2257441/random-string-generation-with-upper-case-letters-and-digits-in-python
