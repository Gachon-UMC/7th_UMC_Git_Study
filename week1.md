# Week1: Git & Github for Developers

## Git?

<hr>

파일의 변경 사항을 추적하고 여러 사용자 간에 해당 파일들의 작업들을 조율하기 위한 분산 버전 관리 시스템
<br>

### Working Directory

현재 내가 작업하고 있는 공간.
기본적으로 워킹 디렉토리 내의 모든 파일은 추적의 대상이 되지만 `.gitignore` 파일을 통해 이를 제어할 수 있다.
<br>

추적을 원치 않는 폴도 혹은 파일을 `.gitignore` 파일에 등록해주면 된다.

- `fileName.txt`: 허용을 원치 않는 파일 하나 등록
- `*.txt`: 해당 확장자를 가지는 모든 파일의 추적 불허
- `folderName/`: 해당 폴더 추적 금지

### File Status

크게 세 가지가 있다.

- unmodified: 변경 내용 없는 파일들
- modified: 변경 내용 있는 파일들
- staged: 커밋을 위한 준비 단계

1. `add` : modified -> staged
2. `commit` : making check point about staged files
3. `push` : local repository -> remote repository

## Branch?

<hr>
내가 작업하는 독립적인 영역. 한 시점에서 서로에게 영향을 끼치지 않도록 처리해주는 것. 주로 기능 단위로 분리한다.

## Issue, PR?

<hr>

### Issue

메인 브랜치에서 기능 브랜치를 나누기 전 팀원들과 프로젝트의 작업 진행 현황과 기능 구현, 버그 수정, 리팩토링 등을 공유하기 위해 생성

- 이슈 제목
- 이슈 내용
- Assignees
- Labels
- Projects, Milestone
- Development

### Pull Request

브랜치에서 작업한 내용을 메인 브랜치에 적용하고 싶을 때, `내 pull 을 받아주세요 ~` 하는 것.

- 제목
- 내용
- Reviewers
- Assignees
- Labels
- Projects, Milestone
- Development

## How to Git

<hr>

- `git clone (reposit URL)`: 레포지토리 클론하기
- `touch .gitignore`: 깃 이그노어 파일 생성
- `git add .`: 모든 파일을 staged 상태로 변경
- `git add (file name)`: 해당 파일을 staged 상태로 변경
- `git commit -m "commit messgae"`: staged 상태의 파일들 커밋하기
- `git push origin (branch name)`: 로컬 레포 내용 원격 레포로 푸쉬하기
- `git status`: 파일의 상태 확인
<hr>

- `git branch (branch name)`: 새로운 브랜치 생성
- `git switch (branch name)`: 해당 브랜치로 이동
- `git merge (branch to merge)`: 다른 브랜치에 현 브랜치 변경사항 적용
<hr>

- `git log`: 커밋을 통해 기록된 내용들 확인
