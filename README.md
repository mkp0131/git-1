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

### 🧤🧤🧤 git swich [branch] -c

- branch 생성, 변경 동시

### 🧤🧤🧤 git push [로컬저장소] [원격저장소] --set-upstream

- git push 명령에 뒤에 '--set-upstream' 붙여준다면 다음 push 부터는 'git push' 만으로 할 수 있다.

## 파일

### .gitattributes

- git 설정파일
- 디렉토리와 파일 단위로 다른 설정을 적용
- Merge는 어떻게 할지, 텍스트가 아닌 파일은 어떻게 Diff 할지, checkin/checkout 할 때 어떻게 필터링할지 설정
- 이 파일을 커밋하고 싶지 않으면 .gitattributes 가 아니라 .git/info/attributes 로 파일 생성
- 보통은 프로젝트 최상위 디렉토리에 생성
