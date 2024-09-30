## Git이란 무엇일까
> - **파일의 변경 사항을 추적**하고 **여러 사용자 간에 해당 파일들의 작업들을 조율**하기 위한 ***분산 버전 관리 시스템***

### 파일 관리
- 레포지토리(레포) repository : 작업하는 파일들이 저장되는 폴더

1. Working Directory
   - 내가 현재 작업하고 있는 공간
   - 원격 레포에 올라가지 못하는 파일들은 *.gitignore* 파일을 통해 관리
   - *.gitignore*로 처리된 파일들은 변화가 생겨도 추적되지 않고, 원격 레포에도 올라가지 않음
2. Staging Area
    - 추적되는 파일들의 상태
      1.  변경 없음(*unmodified*) : 변경되지 않은 파일
      2.  변경됨(*modified*) : 변경된 파일
      3.  스테이지됨(*staged*) : *commit*을 위한 준비 단계
          - ***add***: modified된 파일을 stage
          - ***commit***: staging area에 올라가 staged 상태가 되었을 때 체크포인트 만드는 것 -> Local Repository에 기록됨
          - ***push***: 로컬 레포의 변경 사항들을 원격 레포에 반영
   

### .gitignore
````
touch .gitignore
````

````
// .gitignore
temp1.txt
*.txt  # *.(확장자 이름)
folder_name/  # (폴더 이름)/
````

### 기타 유용한 shell command
