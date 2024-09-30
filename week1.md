### git

: 파일의 변경 사항을 추적하고 여러 사용자 간에 해당 파일들의 작업들을 조율하기 위한 분산 버전 관리 시스템

#### git의 기능

1. 파일의 변경 사항을 추적
2. 여러 사용자 간에 해당 파일들의 작업들을 조율
3. 분산 버전 관리 시스템

---

### git 사용 방법

1. 원격 레포지토리 생성하고 로컬 레포지토리와 연결
   `git clone (레포지토리 주소)`
   <br>
2. .gitignore을 통해 추적되지 않아야 할 파일 관리
   `touch .gitignore`
   <br>
3. add, commit, push로 내 파일 추적 상태 관리
   `git add .` or `git add (file name)`
   `git commit -m "(commit message)"`
   `git push origin (branch name)`
   <br>
4. 내 파일 상태 확인
   `git status`
   <br>

---

### branch

: 개발자가 동시에 작업하지만 서로에게 영향을 끼치지 않도록 처리해주는 것

#### branch 사용 방법

1. branch 생성 및 이동
   `git checkout (branch name)`
   `git switch (branch name)`
   <br>
2. branch merge
   `git merge (branch_name)`
   <br>

---

### commit 기록 확인

로그 조회
`git log` & `head`를 통해 현재 브랜치의 최신 커밋 참조

<br>

---

### ISSUE & PR

##### issue의 구성요소

- 제목
- 내용
- Assignees
- Labels
- Projects
- Milestone
- development

<br>

---

#### pull request

: 메인 브랜치에게 pull을 받아줄 것을 request하는 것
