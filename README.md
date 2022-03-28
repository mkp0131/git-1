# Git

## 명령어

### git clone [repo]

- github repo 가 이미 존재할때 사용.
- git init, git remote add 명령어를 사용하지 않아도 git repo 에 연결되어있다.

### git branch

- 현재 로컬 git 에 있는 branch 리스트

### git branch [branch]

- branch 생성

### git switch [branch]

- branch 변경
- 옛날 명령어: git checkout

### 🧤🧤🧤 git swich [branch] -c

- branch 생성, 변경 동시

### 🧤🧤🧤 git push [로컬저장소] [원격저장소] --set-upstream

- git push 명령에 뒤에 '--set-upstream' 붙여준다면 다음 push 부터는 'git push' 만으로 할 수 있다.
- 즉, 로컬 저장소에 선택된 branch 로 push 가 된다.

### git merge [파일을 가져올 branch]

- 파일을 가져오고 싶은(병합하고 싶은) branch 로 이동 후 get merge [파일을 가져올 branch] 를 실행한다.

### git log --pretty=format:"%h %s" --graph

- 그동안의 로그를 그래프 형식으로 보여준다.

### git checkout [깃 로그 ID]

- 돌아가고 싶은 [깃 로그 ID] 를 입력하면 해당 커밋으로 돌아갈 수 있다
- 다시 원래 상태로 돌아올때: git checkout master

### git reset HEAD~숫자

- reset은 과거 어느 시점의 commit으로 이동과 동시에 이동 시점 이후에 존재하는 commit을 삭제함
- ~숫자 만큼 커밋을 삭제!
- Mixed Reset (복합리셋): 현재 이동한 commit 이후의 생성됬었던 파일들을 unstage 영역(working tree)으로 옮기고, 과거 시점의 commit 상태로 이동함
- 역시 이력은 되돌려집니다. 이후에 변경된 내용에 대해서는 남아있지만, 인덱스는 초기화 됩니다. 커밋을 하려면 다시 변경된 내용은 추가해야 하는 상태
- 삭제후에 원격저장소 push 는 강제로 한다.
- checkout은 HEAD를 이동시켜 commit 위치를 변경시키는 것이라면, reset은 어느 시점으로 이동하고 그 이후에 commit들은 없앰

```
git push origin master --force
```

> 이런 방식으로도 리셋 가능

```
git reset --hard HEAD^ 👈 1개 commit 삭제 후 이전 commit으로 이동
git reset --hard HEAD^^ 👈 2개 commit 삭제 후 전전 commit으로 이동
git reset --hard HEAD^^^ 👈 3개 commit 삭제 후 전전전 commit으로 이동
```

### git reset HEAD~숫자 --soft

- soft rest (소프트 리셋): 돌아간 시점 이후의 파일을 stage area에 위치시키고 commit 시점을 이동함
- 돌아가려 했던 이력으로 되돌아 갔지만, 이후의 내용이 지워지지 않고, 해당 내용의 인덱스(또는 스테이지)도 그대로 있습니다. 바로 다시 커밋할 수 있는 상태로 남아있는 것

### git reset HEAD~숫자 -hard

- 돌아가려는 이력이후의 모든 내용을 삭제

### git commit --amend -m "commit message"

- 마지막 커밋의 메세지를 수정한다.
- 실수로 파일하나를 빼먹고 커밋했을때 `git commit --amend --no-edit` 명령어를 사용한다.
- 즉, 이전 커밋을 갱신한다.

```
git add filename
git commit --amend --no-edit
```

## 파일

### .gitattributes

- git 설정파일
- 디렉토리와 파일 단위로 다른 설정을 적용
- Merge는 어떻게 할지, 텍스트가 아닌 파일은 어떻게 Diff 할지, checkin/checkout 할 때 어떻게 필터링할지 설정
- 이 파일을 커밋하고 싶지 않으면 .gitattributes 가 아니라 .git/info/attributes 로 파일 생성
- 보통은 프로젝트 최상위 디렉토리에 생성

## github

### fork

- 다른 저장소의 모든 것들을 내 계정에 복사한다. (저장소 복사)
- 내 프로젝트로 복사한다.

### pull request

- fork 한 저장소에 내가 수정한 코드를 가져가라는 요청
- 회사에서 같이 협업할때 사용

### fetch request

- fetch 는 pull 한 원격저장소의 변경된 내역을 확인
- pull 은 fetch + merge

### upstream

- 다른 사람의 레포를 포크해왔을 때에 upstream은 일반적으로 오리지널 레포(다른 사람의 레포)를 의미
- origin: 내 레포명

## VSC (비쥬얼 스튜디어 코드)

### U, M, A 상태

- U: untracked / 아직 git 에 등록이 안된 상태
- A: add / 파일 추가된 상태
- M: modify? / 등록된 마지막 상태에서 파일이 수정된 상태

### HEAD -> master, origin/master

- HEAD -> master: 로컬 컴퓨터에서 커밋
- origin/master: 원격저장소에 push

## 궁금증

1. 이전에 버전으로 checkout 한다음 커밋을 하면 checkout 한 시점 이후의 커밋들은 사라지고 새로운 커밋이 덮어씌워지는 것인가?

2. 하드리셋이 아닌 리셋(복합, 소프트)를 하고 커밋을 했을때에 그 이후의 커밋은 덮어씌워지는 것인가?
