# 📚 Git Study 1주차 정리

## Git이란?
`파일의 변경 사항을 추적`하고 `여러 사용자 간에 해당 파일들의 작업들을 조율`하기 위한 `분산 버전 관리 시스템`

<br>

## Repository란?
여러 파일을 관리할 수 있도록 Git에서 제공하는 저장소
- 로컬 저장소 (`local repository`): 사용자의 컴퓨터 내에 있는 저장소
- 원격 저장소 (`remote repository`): Github에 올라가 있는 저장소

<br>

## 파일 관리 구조
- **Local repository**
  - **Working directory:** 현재 작업하고 있는 공간
  - **Staging Area:** 파일의 변경사항을 반영하는 공간
  - **Repository**
- **Remote repository**

<br>

## Git 사용 방법
1. **원격 레포 생성**하고 **로컬 레포와 연결**하기
    - Github에서 Repository 생성
    - `git clone (레포지토리 주소)` 명령어를 통해 로컬 레포와 연결
2. **.gitignore**로 파일 추적되지 않게 관리하기
    - `touch .gitignore` 명령어를 통해 gitignore 파일 생성
    - `*.txt`, `folder_name/` 등 추적을 피하고 싶은 파일 추가
3. **add**, **commit**, **push**로 내 파일 추적 상태 관리하기
    - `git add` 명령어를 통해 변경 사항을 stated 상태로 전환
    - `git commit` 명령어를 통해 로컬 레포에 반영
    - `git push origin` 명령어를 통해 원격 레포로 전달
5. 내 **파일 상태 확인**하기
    - `git status` 명령어를 통해 파일 상태 확인

<br>

## Branch란?
각자 작업할 수 있는 독립적인 영역
- 브랜치 생성: `git branch (브랜치 이름)`
- 브랜치 이동: `git switch (브랜치 이름)`
- 브랜치 병함: `git merge (병합할 브랜치)`

<br>

## 커밋 기록 확인
- `git log`를 통한 커밋 조회
- `HEAD` 값을 통한 최신 커밋 참조

<br>

## Issue와 PR
1. Issue 생성하기
    - 이슈를 통해 팀원들과 프로젝트의 작업 진행 사항 등을 공유
2. Pull Request 올리기
    - PR을 통해 작업한 내용을 메인 브랜치로 반영
