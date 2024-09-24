# Git

파일의 변경 사항을 추적하고 여러 사용자 간 해당 파일들의 작업들을 조율하기 위한 분산 버전 관리 시스템

- Git을 이용해 특정 파일에 일어난 변화를 기록하고 추적할 수 있음
- 한 파일을 여러 사용자들이 접근하고 작업할 수 있음
- 각각의 사용자들이 Github에 존재하는 내용들을 개별 컴퓨터로 가져와 작업하고 기록할 수 있는 시스템

## 파일의 관리

### Working Directory

내가 현재 작업하고 있는 공간!  
기본적으로 변경 사항이 모두 추적되지만 그렇지 않은 파일도 존재  
-> .gitignore 파일을 생성해 해당 파일을 작성해주면 변화가 추적되지 않음

### Staging Area

추적되는 파일들의 세 가지 상태

- unmodified: 변경되지 않은 파일
- modified: 변경된 파일
- staged: ??

변경 사항이 생긴 modified 상태일 때 commit 처리를 해주면  
체크 포인트를 만들 수 있음!

staged는 커밋을 위한 준비 단계!
modifed 된 파일 중 선택적으로 해당 파일을 stage 해서 커밋할 수 있음 -> add  
ex) 모든 파일을 add하면 모든 파일이 staged, 선택적으로 add하면 선택된 파일만 staged

이렇게 staged 된 상태의 파일들을 staging area에 있다고 함!

## Local Repository

commit을 통해 파일의 변경 사항을 기록하는 곳  
이후 local Repository의 변경 사항을 원격 레포에 반경하기 위해 push 명령어를 사용

## Git Issue

Main 브랜치에서 기능 브랜치를 나누기 전 팀원들과 프로젝트의 작업 진행 현황과 기능 구현, 버그 수정, 리팩토링 등을 공유하기 위해 Issue 라는 것을 생성!  
<br>
이슈는 크게 제목, 내용, Assignees와 Labels, Projects, Milestone, Development로 나눌 수 있음  
<br>
`이슈 제목`: 팀 내 프로젝트 컨벤션에 따라 달라질 수 있지만 보통 작업 태그(기능 구현 시 `feature`, 버그 수정 시 `fix`, …)와 대략적인 작업 요약이 들어감.

`이슈 내용`: 이 부분도 컨벤션에 따라 달라지는 부분

`Assignees`: 이슈를 작업할 담당자가 할당되는 부분. 보통 작업자가 이슈를 작성하기 때문에 작업자가 들어감

`Labels`: 작업 태그가 할당되는 부분. 이 부분도 팀 컨벤션에 따라 달라지는 부분

`Projects`, `Milestone`: 조금 더 큰 단위의 작업 내용을 적을 수 있는 부분

`Development`: 이슈와 연결된 브랜치 또는 PR을 연결할 수 있음
