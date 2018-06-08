## 불필요한 미디어 파일 삭제
> `django`에서 사용자가 올린 파일을 수정 또는 삭제할 경우 이전 파일은 서버에 저장할 필요가 없습니다. 일반적으로 수정 또는 삭제할 때 해당 파일을 찾아서 삭제하는 로직을 구현해야하는데 장고에서는 이를 간편하게 처리할 수 있는 `django-cleanup`이라는 패키지가 존재합니다. `django-cleanup`은 장고 모델이 삭제될 때 `FileField delete` 메서드를 자동으로 호출합니다.

- 설치
```sh
$ pip install django-cleanup
```

- 적용  
```py
# settings.py

INSTALLED_APPS = (
  ...
  'django_cleanup', # should go after your apps
)
```


## References
https://stackoverflow.com/questions/21941503/django-delete-unused-media-files