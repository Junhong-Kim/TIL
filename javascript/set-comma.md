## 쉼표 찍기
```js
function setComma(str) {
    str = String(str)
    return str.replace(/(\d)(?=(?:\d{3})+(?!\d))/g, '$1,')
}
```

## 쉼표 제거
```js
function removeComma(str) {
    str = String(str)
    return str.replace(/[^\d]+/g, '')
}
```

## Input box에서 사용자 입력시 쉼표 찍기
```js
function formattingComma(obj) {
    obj.value = setComma(removeComma(obj.value))
}
 
// <input type="text" onkeyup="formattingComma(this)"/>
```

## References
http://blog.munilive.com/javascript-comma-uncomma/
