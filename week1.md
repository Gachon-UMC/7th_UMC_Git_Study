- working directory내의 파일중 올리고 싶지 않은 파일을 .gitignore로 관리
- staging area: 아직 커밋되지 않은, 변경된 파일들을 관리
> git은 버전관리 시스템, 즉 파일의 변경사항을 추적. staged란 변경된 파일중 선택적으로 파일을 골라 커밋할수 있도록 하는것
- local repository: 커밋된 파일이 올라가는 곳
- gitignore.io: .gitignore 파일을 자동으로 생성시켜 주는 사이트
> 특정 확장자나 폴더를 추적헤제하고 싶다면? -> *.txt # *.(확장자 이름) 또는 folder_name/ # (폴더 이름)/을 통해 추적 해제
- git add . : 모든 파일 스태이징
- git add 파일이름: 특정 파일 스테이징
스테이징이 끝나고 나면 -> git commit -m "(커밋 메시지)" -> git push origin (브랜치 이름) 
- git status: 내 파일의 상태를 확인. 만약 커밋 전이면 변경된 파일이 뜨고 커밋 후에는 커밋할 부분이 없다는 메시지가 나옴
- 브랜치: 내가 작업하는 독립적인 영역, 서로의 작업물에 영향을 주지 않기 위해 사용
브랜치를 이동하고 싶은 경우 -> git switch (브랜치 이름)
파일의 수정내용을 복원하고 싶은 경우 -> restore
현재 브랜치의 작업물을 다른 브랜티에 적용하고 싶을 경우: git merge 병합할 브랜치
-> 하지만 충돌 위함이 있기때문에 **Pull Request**를 작성함
---
commit 기록을 살펴보는법: git log

커밋의 구성:
> **커밋 해시** : `commit 691ceb4268ec2c5b2d1afd79dd41f5783dcfac46`
> 
> 
> **커밋 생성자** : `youz2me <kynhun20@gachon.ac.kr>`
> 
> **커밋 일시** : `Sun Sep 22 18:34:03 2024 +0900`
> 
> **커밋 메시지:** `fix: validate 명령어 파라미터 안들어가게 수정`
>

(HEAD -> main, origin/main, origin/HEAD): head는 현재 브랜치의 최신 커밋을 참조하는 값. 
---
git flow: 기능별로 브랜치를 나누고 관리하는 것
issue: 프로젝트 진행현황, 버그 수정등을 공유하기 위해 사용
PR: Pull Request