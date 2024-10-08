cd D:/01_web/pjt002/gitStudy/hello-git-cli

git : git 설치되어 있다면 명령어 도움내용 제공
git init : initialize repository
.git : git repository
git status : working tree status
git add : add to staging area

git commit -m "Message 1"  : create version
git log : show version
git log --stat

git diff : show changes
git log -p
git checkout b26dcc41fef7f52f56413b55d2ce571250086a4b : 이전버전으로 돌아감
git checkout master : 현재버전으로 다시 원위치

git add .  : 현재 폴더포함 하위 폴더까지 모두 add 함
git add 폴더명  : 폴더명 하위 폴더까지 모두 add 함
git commit -am "Message 6" : add 하고 commit까지 한번에 함 
                             --> 최초 add 기록이 있는것만 해당

git config --global core.editor "vim"  : 기본 editor 변경 vim 또는 nano

git reset --hard d0e84fe184ec649bb384606da8458b30281c3151 : 
    --> 이버전이 되겠다 라는 의미 삭제의 의미  (checkout 차이는 되돌아 가지 못함....?)
git reset --help : 도움

git revert 4629b440ddec581daa3bce11dd0a85b7de7350ef
    --> revert 는 단계적으로 revert 해야 한다.

[https 원격지 연결 및 push]
git remote add origin https://github.com/Lee-SangHyeong/hello-git-cli.git : 원격저장소 등록
git remote : 원격저장소 이름 알아 보기
git remote -v : 원격저장소 주소 알아 보기

git push : 이명령어 실행 후 아래 명령어 바로 실행하면 
           --> 다음부터는 git push 명령어는 origin master 로 push 함
git push --set-upstream origin master

git branch -M main
git push -u origin main    

[원격저장소 복사 방법]
git clone https://github.com/Lee-SangHyeong/hello-git-cli.git [원하는 폴더명]
git clone https://github.com/Lee-SangHyeong/hello-git-cli.git my-repo
  --> 원하는 폴더에서 위 명령어 입력 하면 됨
  --> [원하는 폴더명:생략하면 hello-git-cli 폴더]

git pull : 원격지 자료 갖고옴

[로그 보기 옵션등]
git log --all --graph --oneline

git branch : 브랜치 목록 조회
git branch apple : apple 브랜치 생성
git branch google : google 브랜치 생성
git branch ms : ms 브랜치 생성

git log --all --graph --oneline
* 2ac96df (HEAD -> master, ms, google, apple) content 3

PS D:\01_web\pjt002\gitStudy\hello-git-cli> git checkout apple 
Switched to branch 'apple'
PS D:\01_web\pjt002\gitStudy\hello-git-cli> git log --all --graph --oneline
* 87a3cf1 (master) work 4
* 2ac96df (HEAD -> apple, ms, google) content 3

PS D:\01_web\pjt002\gitStudy\hello-git-cli> git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 5 commits.
  (use "git push" to publish your local commits)
PS D:\01_web\pjt002\gitStudy\hello-git-cli> git log --all --graph --oneline
* 87a3cf1 (HEAD -> master) work 4
* 2ac96df (ms, google, apple) content 3

merge 설명
git commit --amend : commit 문구 수정하고자 할때 명령어

1)병합을 하고자 할때는 먼저 master 상태로 checkout
2)갖고오고 싶은 브랜치명
git merge o2

git reset --hard 2065b61 : 이전 마스터 상태로 리셋
--> 이전 상태로 리셋하고 다시 한번더 병합해 볼것

[아래내용 알고 있나?]
git fetch -> git merge FETCH_HEAD -> commit -> push

git pull == git fetch + git merge origin/master 
           --> git pull은 위 2개 작업하고 일치함

cat .git/FETCH_HEAD -->  branch 'master' of https://github.com/Lee-SangHyeong/hello-git-cli             
1ae977ae850288f879bf7a9903a786853234eadd            

git fetch; git merge FETCH_HEAD
           --> 위 2개 명령어 동일함
           --> 이방법은 신중하게 먼저 갖고 오고
               머지는 나중에 하고자 할때 하는 방식 임

patch : open source 기반으로 진행할때 .... 사용하는 기능: 생활코딩
  너튜브참조 --> https://www.youtube.com/watch?v=BLm0zsK3K_I&list=PLcDtUrBwapUOQzycPhaGUFnc-ogBOI6N_&index=50

pull request
