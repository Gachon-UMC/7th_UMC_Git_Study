# 1주차 학습내용 정리


## <개발을 위한 Git과 Github>
### > Git이란?

1). Git :  파일의 변경 사항을 추적, 여러 사용자 간에 해당 파일들을 조율하기 위한 분산버전 관리 시스템 <br>
2). Github : 코드 저장, 공유, 협업 공간


### > 시스템 설명
* repository : 한 파일이 아닌 여러 파일을 관리할 수 있도록 저장소라는 개념 사용 <br>
	* 로컬 저장소(local repo) : 사용자의 컴퓨터 내에 있는 로컬 저장소 <br>
 		* staged 상태의 파일을 git commit 할 경우 변경 사항이 기록되는 곳
   		* commit의 경우 -m " " 을 통해 커밋 메시지를 남길 수 있음
	* 원격 저장소(remote repo) : Github에 올라가 있는 원격 저장소 <br>
* Working Directory : 내가 현재 작업하고 있는 공간(폴더) <br>
	* 이 폴더 내부 파일은 변경 사항 추적

* .gitignore : Git 시스템이 추적할 수 없는 파일을 설정하는 파일 <br>
	* 편집을 통해 특정 파일 설정 가능

* Staging Area : git add를 통해 commit을 대기하는 곳
	* 추적되는 파일은 변경 없음(unmodified), 변경됨(modeified), 스테이지됨(staged) 세 개로 분류
	* staged의 경우 commit을 준비하는 단계 => add된 경우 Stage Area로 이동
   	* git add . or (파일 이름)으로 staged 상태 만들 수 있음
   
* git clone (주소) : 원격 레포를 로컬 레포와 연결

* git push origin (브랜치) : 로컬 레포에 반영된 내용을 원격 레포로 보냄
  	* origin은 원격 레포의 URL을 의미
  	* main으로 바로 push는 위험

* git status : 내 파일 상태 확인 <br>

### > 브랜치(branch)란?
* 작업을 나눠서 할 수 있도록 영역을 나눈 것으로 내가 작업하는 독립적인 영역

* git branch (브랜치 명) : 브랜치 생성
* git switch (브랜치 명) : 브랜치 전환
* git merge (병합할 브랜치) : 현재 브랜치에서 다른 브랜치의 변경사항을 적용할 때 사용
  	* 보통은 merge 대신 Pull Request를 작성 (충돌 방지) <br>
   
### > 커밋 기록 확인
* git log : 파일 수정 일시, 변화 내용을 확인할 수 있음

* HEAD : 현재 브랜치의 최신 커밋을 참조하는 값 (최신 커밋을 포인터로 가리키고 있다는 개념) <br>

### > Issue & PR
* Issue : 목표 설정
  	* 레포지토리 주소에 들어가서 작성
  	* 제목, 내용, Assignees, Labels, Projects, Milestone, Development로 나뉨
  	* 작성은 컨벤션에 따라 달라짐
  	* Assignees는 작업자를 할당 <br>
* Pull Request : 브랜치에서 작업한 내용 메인 브랜치에 반영할 때 작성
	* 제목, 내용, Reviewers, Assignees, Labels, Projects, Milestone, Development로 나뉨
   	* 작성은 컨벤션에 따라 달라짐
   	* 리뷰어는 리뷰할 작업자 선택
   	* 코드 리뷰 진행
