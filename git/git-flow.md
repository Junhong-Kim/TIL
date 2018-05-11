## git-flow란?
`Vincent Driessen`의 브랜칭 모델을 적용하여 고수준으로 저장소를 관리하기 위한 `Git`의 확장입니다.

![git-flow](./img/git-flow.png)

### 1. 시작하기
> 설치
```sh
$ brew install git-flow
```

> 초기 설정
```sh
# 로컬 저장소에 develop 브랜치가 생성되고 checkout 합니다.
$ git flow init -d
```

> 브랜치 확인
```sh
# -a 옵션으로 원격 브랜치를 포함한 모든 브랜치 목록을 확인할 수 있습니다.
$ git branch -a [-v]
```

> 주요 명령어
```sh
$ git flow [feature | release | hotfix] start <branch name>
$ git flow [feature | release | hotfix] finish <branch name>
```

### 2. 적용하기
#### 2-1. git-flow 최초 적용자
> 원격 저장소 연결
```sh
$ git clone <remote url>
$ git flow init -d
# 원격 저장소에 develop 브랜치 생성
$ git push origin develop
$ git branch --set-upstream-to=origin/develop develop
```

> `feature` 브랜치에서 개발
```sh
$ git flow feature start <branch name>
$ git flow feature finish <branch name>
$ git push origin develop
```

> `release` 시기
```sh
$ git flow release start <version>
$ git flow release finish <version>
$ git push origin master
```
    
#### 2-2. git-flow가 적용된 프로젝트를 `clone`하는 개발자
> 원격 저장소 연결
```sh
$ git clone <remote url>
$ git checkout -b develop origin/develop
$ git flow init -d
```

> `feature` 브랜치에서 개발
```sh
$ git flow feature start <branch name>
$ git flow feature finish <branch name>
$ git push origin develop
```

> `release` 시기
```sh
$ git flow release start <version>
$ git flow release finish <version>
$ git push origin master
```