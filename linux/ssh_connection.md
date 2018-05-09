## SSH 접속 방법

### 일반적인 SSH 접속 방법
```sh
$ ssh -l [username] [ipaddress] [-p portnumber]
```

### 간편한 SSH 접속 방법
> 쉘 스크립트 파일에 해당 SSH 정보를 저장하고 실행합니다.

#### 1. 쉘 생성
```sh
$ cd ~/bin
$ vi [filename].sh
```
#### 2. 쉘 코드
```sh
#!/bin/sh

# 실행시 출력 메시지
echo "Welcome to [filename]"
# user명 입력받기
read -p "user: " user
# 실제 실행되는 쉘
ssh -l $user xxx.xxx.xxx.xxx [-p portnumber]
```
#### 3. 쉘 실행
```sh
# 쉘 실행
$ sh [filename].sh
Welcome to [computer_name]
user: root
root@xxx.xxx.xxx.xxx`s password: 

# 접속 성공시
[root@xxx.xxx.xxx.xxx ~]$
```
