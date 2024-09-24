# Git
분산 버전 관리 시스템

Github = 원격(remote)

Local = 내 컴퓨터(local)

## working directory
현재 작업하고 있는 공간

## staging area
'staged' 파일이 존재하는 곳

## local repository
commit을 통해 파일의 변경 사항을 기록하는 곳 

## .gitignore
워킹 디렉토리 내에서 추적되지 않아야하는 파일 목록 지정하는 파일
여기 파일이나 폴더를 추가해 놓으면 파일 추적 되지 않음.

# 사용법
1. clone하고자 하는 레파지토리 주소를 복사
2. `git clone (레파지토리 주소)`
3. `해당 폴더에 들어가기`
4. `git add . `
#전체 파일을 staged상태로 변경
5. `git commit -m "(커밋 메세지)"  `#staged 된 파일의 변경사항을 로컬에 반영하기 위해 commit 사용
6. `git push origin (브랜치 이름)`  #주로 기본은 main
7. `git status`  #내 파일의 상태를 확인하는 방법

### 브랜치(branch)
다수가 동시에 같은 파일에 작업을 하더라도 브랜치가 있다면 서로에게 영향을 끼치지 않고 처리할 수 있다. 보통 기능 단위로 많이 분리한다. 
1. `git branch (새로 만들 브랜치 이름)`
2. `git switch (브랜치 이름)`
3. `git merge (병합할 브랜치) `
#### 그러나 협업 시 merge를 사용하기 보다는 pull request 한다.

## 커밋 기록 확인
`git log`
#버전 기록. 
#### HEAD : 현재 브랜치의 최신 커밋을 참조하는 값

### ISSUE
나의 작은 목표 설정

### Pull Request
메인 브랜치에게 pull을 받아줄 것을 요청(request)하는 것
