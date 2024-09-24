## 목차

### 1. Git이란?

### 2. 파일 관리 방법

### 3. Git 사용 방법

### 4. 브랜치란?

### 5. 커밋 기록 확인 방법

### 6. Issue와 PR(Pull & Request)

---

<br>

### 1. Git이란?

-> Git : 파일의 변경 사항을 추적하고 사용자 간에 해당 파일들의 작업들을 조율하기 위한 분산 버전 관리 시스템<br>

#### \* 파일 변경 사항 추적

파일을 언제 수정했는지, 그 때 파일 내에서 어떠한 변화가 있었는지를 로그 형식으로 기록하여 파일 내 변화를 기록하고 찾아준다.

#### \* 작업 조율

Github(원격)에 있는 한 파일을 각 사용자의 컴퓨터(로컬)에서 다운 받아 동시에 접근하고 공동으로 작업 및 조율할 수 있다.

#### \* 분산 버전 관리 시스템

Division VCS로 여러 명이 한 파일에 접근해 개별적으로 작업하고, 작업 결과를 기록으로서 반영하는 시스템이다.

- 버전 : 파일이 수정되고 기록되는 시점

---

### 2. 파일 관리 방법

#### \* Working Directory

내가 현재 작업하고 있는 폴더로, 추적되지 않는 파일들을 관리하는 .gitignore 파일을 제외하고 원격 레포로 올린다.

#### \* Staging Area

git add . or git add (파일 이름)<br>
체크포인트라고 이해하면 쉽다. 변경 사항이 생긴 modified 상태인 파일을 commit할 수 있게 준비해주는 단계이다.

#### \* Local Repository

git push origin (브랜치)<br>
Staging Area에 올라간 파일을 commit 하면 파일의 변경 사항이 기록되는데, 이 기록하는 곳을 말한다.

---

### 3. Git 사용 방법

#### 1. git repoitory 생성 후 적절한 폴더와 연결 - git clone (레포지토리 주소)

#### 2. .gitignore 파일로 추적되지 않는 파일 관리(직접 만들 수 있지만, gitignore.io 사이트 이용하면 편함)<br>

- cmd에서 파일 생성 : fsutil file createnew week1.md 0

#### 3. add-commit-push -> 원격 레포로 보내기

#### 4. git status를 통해 파일 상태 확인 가능

---

### 4. 브랜치란?

#### \* Branch

한 프로덕트를 만들 때 서로에게 영향을 주지 않는 작업을 진행하기 위해서 만듬. 보통 기능 단위로 브랜치를 분리한다.

#### \* 브랜치 생성 및 전환

- 생성 : git branch (브랜치 이름)
- 전환 : (git checkout) git switch (브랜치 이름)인데 최근에는 switch 사용(checkout = switch + restore)

#### \* 브랜치 merge

다른 브랜치의 변경 사항을 현재 브랜치에 적용시키고 싶을 때 사용하는 명령어이다. 하지만 협업 과정에서 충돌이 일어날 수 있기 때문에 merge보다 Pull Request를 사용한다.

---

### 5. 커밋 기록 확인 방법

#### \* git log 조회

로그를 살펴보면 커밋들의 기록을 살펴볼 수 있어 파일을 언제 수정했는지, 그 때 파일 내에서 어떠한 변화가 있었는지 확인할 수 있다.

#### \* HEAD

내 브랜치의 가장 최신 주소로, 최신 커밋을 포인터로 가리키고 있다고 생각하면 편하다.

---

### 6. Issue와 PR(Pull & Request)

#### \* Issue

프로젝트를 할 때 기능 별로 브랜치를 나누고 관리하는 Git-Flow 방식을 사용하는데, 이 때 Issue에 제목, 내용, Assignees, Labels, Projects, Milestone, Development를 활용하여 기능을 관리할 수 있다.

#### \* Pull Request

Issue 생성 후 브랜치를 만들고 진행한 작업을 메인 브랜치에 반영하는 것이다. PR에는 제목, 내용, Reviewers, Assignees, Labels, Projects, Milestone, Development로 나누어 볼 수 있다.

---
