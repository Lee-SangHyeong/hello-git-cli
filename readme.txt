cd D:/01_web/pjt002/gitStudy/hello-git-cli

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
    --> 이버전이 되겠다 라는 의미  (checkout 차이는 되돌아 가지 못함....?)
git reset --help : 도움

git revert 4629b440ddec581daa3bce11dd0a85b7de7350ef
    --> revert 는 단계적으로 revert 해야 한다.