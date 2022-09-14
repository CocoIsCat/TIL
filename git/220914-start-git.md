# 첫 수업

# 웹 개발자 동향

- 웹 개발자는 항상 최신 트렌드를 따라가야 함

# 수업의 목표

- git 사용의 궁극적인 목표는 git을 사용하여 타인과 협업하여 다른 프로젝트에 기여하는 것
- 현재 프로젝트의 규모는 개인이 혼자 해결할 수 없는 정도이기 때문에 반드시 필수적으로 형상관리 프로그램을 사용함

---

# 리눅스의 역사

- Bell 연구소에서 유닉스 만들어짐
- GNU 프로젝트로 오픈소스 소프트웨어 운동 시작
- 리누스 토발즈가 리눅스 만듦

### 커널

- 하드웨어와 응용프로그램을 이어주는 운영체제의 프로그램

### Shell

- 커널과 사용자를 이어주는 소프트웨어
- bash, zsh 등이 있음

---

# 터미널

## 터미널 알아보기

- ~ : 현재 유저가 권한 없이 사용할 수 있는 최고 위치
- / : 최상단 디렉토리
- . : 현재 디렉토리
- .. : 상위 디렉토리
- * : 조건과 일치하는 모든 것

## 터미널 명령어

- pwd : 현재 위치
- ls : 디렉토리에 있는 파일 표시
    - - a : 숨김 파일까지 출력
    - - l : 파일의 상세 정보 출력
- cd : 디렉토리 이동
- mkdir : 디렉토리 만들기
- touch : 파일 만들기
- mv  : 이동하기
- cp : 복사하기
- rm : 파일 삭제하기
    - -r : 디렉토리 삭제
    - delete 와 remove의 차이
        - delete : 물리적인 삭제
        - remove : 논리적인 삭제
- rmdir : 디렉토리 삭제하기
    
    

---

# 에디터

## Vim

- Normal Mode(press esc on any mode)
    - 처음에 들어가면 노멀 모드로 진입 → 키를 누르면 명령어로 동작함
- Insert Mode (press i on normal mode)
- Visual Mode(press v on normal mode)
- Command Mode(press : on normal mode)

## Vim commands

- hjkl : 방향키 대신
- y : 복사하기
- p : 붙여넣기
- dd : 한 줄 삭제하기
- ``` : 코드 블럭

## cat

- 파일 내용 확인

---

# Git

- 리누스 토발즈가 만든 형상 관리 프로그램

## Git의 장점

- 빠른 속도, 단순한 구조
- 분산형 저장소 지원
- 비선형적 개발 가능

## Git objects

- Blob : 파일 하나의 내용에 대한 정보
- Tree : Blob이나 subtree의 메타 데이터(디렉토리 위치, 속성 이름 등)
- Commit : 커밋 순간의 스냅샷

## Git Process Flow

### Local

- working directory : 변경 사항이 발생하는 곳
- staging area : 변경 사항을 저장하는 곳
    - 여러 개의 변경 사항이 발생했을 때 특정 파일만 골라서 commit이 가능하게 해줌
    - 
- localrepo : 변경 사항에 대한 메타 데이터를 생성하는 곳

## Git 명령어

- git add
- git status
    - -uall :상세 정보 보기
- git commit
- git push
- git pull
- git clone

### Remote

- remote repo : 원격 저장소

---

# Github

- Git을 사용해서 웹 서비스를 제공함
- MS가 인수

## 비슷한 서비스

- Bitbucket : jira, confluence, trello 등의 부가도구와 유기적으로 협업, 대기업에서 많이 씀
- Gitlab : 사설 서버 구성이 가능, 보안에 특화됨

---

# README 작성하기

[README 예제](https://www.notion.so/README-640583bec3964aa78225842d3b9c0ce8)

- 맨 위에 한줄 요약
- 목차
    - 설치 방법
    - 시작하는 방법
    - 특징
    - 기술 스택
    - 프로그램이 사회에 기여하는 것

---

# Commit 메세지 작성

- 해당 작업 단위에 수행된 모든 파일 변화가 해당 commit에 포함되어야 함
- 모두가 이해할 수 있는 log를 작성할 것
- 영어 사용하기
- 제목은 축약하여 쓰기(40자 이내로 구나 절의 형태)
- 내용은 문장형으로 작성하여 추가설명
- 제목과 내용은 한 줄 띄워서 분리
- prefix 꼭 달기
    - feat : 기능 개발 관련
    - fix : 오류 개선 혹은 버그 패치
    - docs : 문서화 작업
    - test : test 관련
    - conf : 환경설정 관련
    - refactor : 알고리즘 개선
    - build : 빌드 관련
    - BREAKING CHANGE : 매우 중요한 변경 사항(ex. 버전 업데이트 시 전 버전의 지원 종료를 통보)
    - ci : Continuous Integration 관련
    - etc..

---

# .gitingnore

git이 추적하지 않고 무시할 파일이나 폴더 등을 지정함

1. 확장자 무시
    - *.java
2. 파일명 무시
    - keyfile.*
3. 디렉토리 무시
    - hidden/**
    

gitignore 파일을 만들어주는 곳

https://www.gitignore.io

---

# License

- MIT License
    - 저작권 아예 없음
    - 영리적 사용 가능
- Apache License 2.0
    - 특허권을 주장함
- GNU General Public License v3.0
    - 한 줄이라도 해당 라이센스가 적용된 소스코드 사용 시 GPL을 따라야 한다는 의무사항이 존재

---

# TIL 사용법

- 공부하는 언어 별, 프레임워크 별로 디렉터리 만들기
- 매일 한번씩 commit하기
