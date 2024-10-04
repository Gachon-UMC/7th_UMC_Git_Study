# git 이란?
  * 파일의 변경 사항을 추적하고 여러 사용자 간에 해당 파일들의 작업들을 조율하기 위한 분산 버전 관리 시스템

# git을 왜 사용할까?
  * 여러 사용자가 특정 내용에 대해 접근하고 공동으로 작업할 수 있기 때문이다

# 파일 관리 방법
  * 각 위치에 있는 저장소는 사용자의 컴퓨터 내에 있는 로컬 저장소(local repository), Github에 올라가 있는 원격 저장소(remote repository)로 나누어진다

# working Direcltory
  * 내가 현재 작업하고 있는 공간(폴더)를 워킹 디렉토리(working directory)라고 부릅니다. 워킹 디렉토리 내의 파일은 기본적으로 변경 사항이 모두 추적되지만, .gitignore로 처리된 파일들은 변화가 생겨도 추적되지 않고, 원격 레포에 올라가지 않습니다.

# staging Area
  * 변경 사항이 생긴 modified 상태일 때 체크포인트를      
    만드는 일을 commit 이라고 한다
  
  * staged는 commit을 위한 준비 단계로,   
    modified된 파일 중 선택적으로 해당 파일을 stage해서 해당 파일만 커밋할 수 있도록 하는 것

  * add : modified된 파일을 stage하는 것
    * 한꺼번에 모든 파일을 add하면 모든 파일이 staged가 
      되고, 선택적으로 add하면 선택된 파일만 staged
  
  * 이렇게 staged 된 상태의 파일들을 staging area에   
    있다고 한다

# Local Repository
  * commit을 통해 파일의 변경 사항을 기록하는 곳
  * 반영하고 싶은 변경 사항을 add를 통해 staged 상태로 
    만들고, 이후 commit을 통해 최종적으로 local repository에 반영하는 것
  * 이후 로컬 레포의 변경 사항들을 원격 레포에 반영하기   
    위해서는 push라는 명령어를 사용
  
