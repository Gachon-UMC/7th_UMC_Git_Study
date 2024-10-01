# GIT 1주차 내용 정리
1. 내 작업공간 (WORKING DIRECTORY)
    : git에 업로드 한 내 디렉토리 내의 파일은 추적됨.
    >unmodified
    >modified
    >staged : commit을 위한 준비단계

2. GIT 사용법!
    * 깃에서 레포지토리 생성 후
        - git add . : 모든 파일을 add하여 stage상태로 만들기
        - git commit -m "커밋 메세지" : stage된 파일들을 commit하기
        - git push origin 브랜치 이름 : 로컬 레포지토리에 반영된 내용을 원격 레포지토리에 보내는 명령어
        - git status : 현재 나의 디렉토리 상태를 확인 하는 명령어
    * Branch 란? ~~내가 제일로 어려워 했던거 ㅠㅠ~~
        : 현 시점에서 서로에게 영향을 주지 않는 작업진행을 위한 작업 공간!
        - git branch 브랜치 이름 : 브랜치 생성하기
        - git checkout / switch 브랜치 이름 : 브랜치로 이동하기