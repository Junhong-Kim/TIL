## 1. Local Repository (로컬 저장소)
### 1-1. 사용자 정보 설정
```sh
$ git config --global user.name [user name]
$ git config --global user.email [user email]

# 사용자 정보 확인
$ git config --list
$ git config [user.name | user.email]
```

### 1-2. 저장소 생성
> 새로운 디렉토리를 생성하고 이동합니다.
```sh
$ mkdir [directory name] && cd [directory name]
```

> `init` 명령어로 현재 디렉토리를 로컬 저장소로 설정합니다.
```sh
$ git init
```

> 현재 디렉토리에 `.git` 파일이 생성된 것을 확인합니다.
```sh
$ ls -al
```

### 1-3. 버전 관리
> `status` 명령어로 현재 디렉토리 상태를 확인합니다.
```sh
$ git status
```

> `add` 명령어로 Git이 파일을 추적하도록 합니다.
```sh
# 해당 파일은 commit 대기 상태가 되며 stage area에 올라갑니다. ('*'은 모든 파일을 뜻합니다.)
$ git add [file name | *]
```

### 1-4. 버전 생성
> `commit` 명령어로 새로운 버전을 생성합니다.
```sh
$ git commit
$ git commit -m [commit message]
```

> `-a` 옵션으로 `add` 명령어 없이 바로 `commit` 할 수 있습니다.
```sh
# 최초 파일은 add 되어있어야 합니다.
$ git commit -a
$ git commit -am [commit message]
```

> `--amend` 옵션으로 로컬 저장소에 있는 마지막 commit message를 수정할 수 있습니다.
```sh
$ git commit --amend
```

### 1-5. 버전 확인
> `log` 명령어로 commit message를 확인합니다.
```sh
$ git log [--reverse]
```

> `-p` 옵션으로 소스 변경사항을 확인할 수 있습니다.
```sh
$ git log -p
```

> `diff` 명령어로 `add` 전/후를 비교할 수 있습니다.
```sh
$ git diff
$ git diff [version id1]..[version id2]
```

### 1-6. 버전 복구
> `reset`과 `revert` 명령어로 과거 버전으로 돌아갈 수 있습니다.
```sh
# commit 내역과 코드 삭제
$ git reset --hard [version id]
$ git revert [version id]
```

```sh
# commit 내역만 삭제 (코드는 남습니다)
$ git reset --soft [version id]
```

## 2. Remote Repository (원격 저장소)
### 2-1. remote
> `remote` 명령어로 로컬 저장소와 연결된 원격 저장소를 확인합니다.
```sh
$ git remote [-v]
```

> `remote add` 명령어로 로컬 저장소와 원격 저장소를 연결합니다.
```sh
# alias는 remote url의 별칭을 뜻합니다.
$ git remote add [alias] [remote url]
$ git remote add origin https://github.com/Junhong-Kim/GitExample.git
```

> `remote remove` 명령어로 로컬 저장소와 원격 저장소 연결을 삭제합니다.
```sh
$ git remote remove [remote url]
$ git remote remove origin
```

### 2-2. clone
> `clone` 명령어로 원격 저장소의 소스를 로컬 저장소로 복제합니다.
```sh
$ git clone [remote url] [directory name]
$ git clone https://github.com/Junhong-Kim/GitExample.git GitExample
```

### 2-3. pull
> `pull` 명령어로 로컬 저장소로 원격 저장소 소스를 다운로드합니다.
```sh
$ git pull [remote url] [branch]
$ git pull origin master
```

### 2-4. push
> `push` 명령어로 로컬 저장소의 소스를 원격 저장소로 업로드합니다.
```sh
$ git push [remote url] [branch]
$ git push origin master
```

> `-u` 또는 `--set-upstream` 옵션으로 `push` 명령어 설정을 합니다.
```sh
# 아래 명령어를 입력한 이후, git push 명령어는 해당 원격 저장소 브랜치로 push 됩니다.
$ git push [-u | --set-upstream] origin master
```

### 2-5. clean
> `clean -f` 명령어로 untracked 파일을 제거할 수 있습니다.
```sh
$ git clean -f
```

> `clean -fd` 명령어로 untracked 파일 및 디렉토리를 제거할 수 있습니다.
```sh
$ git clean -fd
```

## 3. Branch
### 3-1. 브랜치 목록
> default 브랜치는 `master` 입니다.
```sh
$ git branch
```

> `-a` 옵션으로 원격 브랜치를 포함한 모든 브랜치 목록을 확인합니다.
```sh
$ git branch -a [-v]
```

### 3-2. 브랜치 생성
> `branch` 명령어로 브랜치를 생성합니다.
```sh
$ git branch [branch name]
```

### 3-3. 브랜치 전환
> `checkout` 명령어로 브랜치를 전환합니다.
```sh
$ git checkout [branch name]
```

> `-b` 옵션으로 브랜치 생성후 브랜치를 전환합니다.
```sh
$ git checkout -b [branch name]
```

### 3-4. 브랜치 비교
> `branches` 모든 브랜치 표시, `graph` 그래프로 표현, `decorate` 브랜치명 표시, `oneline` 한 줄로 표시
```sh
$ git log --branches --graph --decorate --oneline
```

> 브랜치간 비교
```sh
$ git log [branch name1]..[branch name2]
```

> 브랜치간 소스 비교
```sh
$ git diff [branch name1]..[branch name2]
```

### 3-5. 브랜치 병합
> `master` 브랜치로 `develop` 브랜치를 병합합니다. (master ← develop)
```sh
$ git checkout master
$ git merge develop
```

### 3-6. 브랜치 삭제
> `-d` 옵션으로 브랜치를 삭제합니다.
```sh
$ git branch -d [branch name]
```

> `-D` 옵션으로 병합하지 않은 브랜치를 강제로 삭제합니다.
```sh
$ git branch -D [branch name]
```

## 4. Tag
### 4-1. 태그 목록
```sh
$ git tag
```

### 4-2. 태그 생성 
```sh
# light weight tag
$ git tag [tag name] [version id]

# annotated tag
$ git tag -a [tag name] -m [tag message] [version id | branch name]
```
### 4-3. 태그 삭제
```sh
$ git tag -d [tag name]
```

### 4-4. 태그 업로드
```sh
# 원격 저장소로 태그가 업로드 됩니다.
$ git push --tags
```

## 5. Conflict
> `merge`할 때 충돌이 발생할 경우 다음 메시지가 출력됩니다.
```sh
Auto-merging [conflicted file name]
CONFLICT (content): Merge conflict in [conflicted file name]
Automatic merge failed; fix conflicts and then commit the result.
```

> 충돌한 파일을 확인합니다.
``` sh
$ git status
```

> 충돌한 파일의 코드를 수정합니다.
```js
function b() {
}
<<<<<<< HEAD
function a(master) {
=======
function a(develop) {
>>>>>>> develop
}
function c() {

}
```

`<<<<<<< HEAD` 부터 `=======` 사이가 현재 체크 아웃된 파일의 내용이고  
`=======` 부터 `>>>>>>> develop` 사이가 병합하려는 대상인 develop 브랜치의 코드 내용입니다.  
이 정보를 참고해서 두개의 코드를 병합한 뒤 특수 기호를 제거하면 됩니다.
> 충돌을 해결한 뒤 파일을 `add` 하고 `commit` 합니다.
```sh
$ git add [conflicted file name | *]
$ git commit [conflicted file name | *]
```

## 6. gitignore
> `git`으로 관리하지 않을 파일은 `.gitignore` 파일에 이름을 추가합니다.
```sh
$ echo "secrets.js" >> .gitignore
```

> `rm` 명령어로 원격 저장소와 로컬 저장소에 있는 파일을 삭제합니다.
```sh
$ git rm [file name]
$ git add --all
$ git commit -m "Apply, .gitignore"
$ git push origin master
```

> `rm --cached` 명령어로 원격 저장소에 있는 파일을 삭제합니다.
```sh
$ git rm --cached [file name]
$ git add --all
$ git commit -m "Apply, .gitignore"
$ git push origin master
```
