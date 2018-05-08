## Custom HTTP header
> custom HTTP hedaer 이름이 `my-custom-header`일 때
```py
# request.META.get('HTTP_{uppercased_custom_header_name}')
request.META.get('HTTP_MY_CUSTOM_HEADER')

# request.META['HTTP_{uppercased_custom_header_name}']
request.META['HTTP_MY_CUSTOM_HEADER']
```

## References
https://stackoverflow.com/questions/14377050/custom-http-header-in-django
