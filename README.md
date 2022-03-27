# Git

## 명령어

### git clone [repo]

- github repo 가 이미 존재할때 사용.
- git init, git remote add 명령어를 사용하지 않아도 git repo 에 연결되어있다.

## 파일

### .gitattributes

- git 설정파일
- 디렉토리와 파일 단위로 다른 설정을 적용
- Merge는 어떻게 할지, 텍스트가 아닌 파일은 어떻게 Diff 할지, checkin/checkout 할 때 어떻게 필터링할지 설정
- 이 파일을 커밋하고 싶지 않으면 .gitattributes 가 아니라 .git/info/attributes 로 파일 생성
- 보통은 프로젝트 최상위 디렉토리에 생성
