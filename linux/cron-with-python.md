## 파이썬 모듈 `cron`으로 실행하기
> 디렉토리 위치 변경후 `shell script` 파일을 생성합니다.
```sh
$ cd ~/bin
$ vi <filename>.sh
```

> 파일 내용을 다음과 같이 작성합니다.
```sh
#!/bin/sh
if [ -f ~/.bashrc ]; then
        # .bashrc 실행
        . ~/.bashrc
fi
if [ -f ~/.bash_profile ]; then
        # .bash_profile 실행
        . ~/.bash_profile
fi

# 실행 날짜
TODAY=$(date + "%Y%m%d")
# 실행 시간
START_DATE=$(date + "%Y-%m-%d %T")
# 로그파일 경로
LOGPATH="~/log"
# 로그파일명 <filename>.YYYYMMDD.log
LOGFILE="<filename>.$TODAY.log"
# 로그파일이 저장될 위치와 이름
FILE=$LOGPATH$LOGFILE

((
  echo "START $START_DATE"
  echo ""
  cd ~/<django-project-path>/ && \
  echo "argument: $1" && \
  python manage.py <filename> && \
  END_DATE=$(date + "%Y-%m-%d %T") && \
  echo "END $END_DATE"
) > $FILE 2>&1 &)
```
> 파일 설정
```sh
# 실행 파일로 설정
$ chmod 755 <filename>
# 권한 설정 (root 또는 사용자)
$ chown root:root <filename>
```

> cron 명령어
```sh
# cron 목록
$ crontab -l
# cron 등록
$ crontab -e
```

```sh
# 매일 00:00에 실행
0 0 * * * ~/bin/<filename>.sh > /dev/null 2>&1
:wq
```

```sh
# cron 등록 완료
crontab: installing new crontab
```

## References
https://stackoverflow.com/questions/10508843/what-is-dev-null-21
