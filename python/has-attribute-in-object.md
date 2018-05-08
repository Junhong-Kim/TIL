## Object에 특정 attribute 가 존재하는지
```py
class Person:
    name = None

    def __init__(self, name):
        self.name = name

p = Person('kim')
if hasattr(p, 'name'):
    print(p.name)
    