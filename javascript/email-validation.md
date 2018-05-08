## 이메일 유효성 검사
```js
const email = 'test@test.com'
const regex = /^([\w-]+(?:\.[\w-]+)*)@((?:[\w-]+\.)*\w[\w-]{0,66})\.([a-z]{2,6}(?:\.[a-z]{2})?)$/
 
if(regex.test(email) === false) {
 alert("잘못된 이메일 형식입니다.")
} else {
 // something to do
}
```
