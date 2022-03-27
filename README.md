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

### 🧤🧤🧤 git reset HEAD~숫자 --soft

- 커밋을 삭제!
- 소프트리셋
- 내가 수정한 상태는 그대로 둔다.

### 🚫 git reset HEAD~숫자

- 커밋을 삭제!
- ~숫자 만큼 커밋을 삭제!
- 삭제후에 원격저장소 push 는 강제로 한다.
- 하드리셋

```
git push origin master --force
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
