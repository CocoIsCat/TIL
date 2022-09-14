# 웹 개발자 동향

- 웹 개발자는 항상 최신 트렌드를 따라가야 함

# 수업의 목표

- git 사용의 궁극적인 목표는 git을 사용하여 타인과 협업하여 다른 프로젝트에 기여하는 것
- 현재 프로젝트의 규모는 개인이 혼자 해결할 수 없는 정도이기 때문에 반드시 필수적으로 형상 관리 프로그램을 사용함

---

# 리눅스의 역사

- Bell 연구소에서 유닉스 만들어짐
- GNU 프로젝트로 오픈소스 소프트웨어 운동 시작
- 리누스 토발즈가 리눅스 만듦

### Kernel(커널)

- 하드웨어와 응용프로그램을 이어주는 운영체제의 프로그램

### Shell(쉘)

- 커널과 사용자를 이어주는 소프트웨어
- bash, zsh 등이 있음

---

# 터미널

## 터미널 알아보기

- ~ : 현재 유저가 권한 없이 사용할 수 있는 최고 위치
- / : 최상단 디렉토리(root 디렉토리)
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
- rmdir : 디렉토리 삭제하기(거의 안 씀)

---

# 에디터

## Vim

- Normal Mode(press ‘esc’ on any mode)
    - 처음에 들어가면 노멀 모드로 진입 → 키를 누르면 명령어로 동작함
    - h - j - k - l : 왼쪽 - 아래 - 위 - 오른쪽
    - y : 복사하기
    - yy : 한 줄 복사
    - p : 붙여넣기
    - d : 삭제
    - dd : 한 줄 삭제하기
    - u : 복구
    - ``` : 코드 블럭
    - gg : 첫번째 줄로 이동
    - dg : 현재 위치 이하 모두 삭제

- Insert Mode (press ‘i’ on normal mode)
- Visual Mode(press ‘v’ on normal mode)
- Command Mode(press ‘:’ on normal mode)
    - q : 탈출
    - q! : 수정 내용을 저장하지 않고 탈출
    - w : 내용 저장
    - wq : 내용을 저장하고 탈출
    

## cat 명령어

- 파일 내용 확인하기

---

# Git

- 리누스 토발즈가 만든 형상 관리 프로그램

## Git의 장점

- 빠른 속도, 단순한 구조
- 분산형 저장소 지원
- 비선형적 개발 가능(branch 사용)

## Git objects

- Blob : 파일 하나의 내용에 대한 정보
- Tree : Blob이나 subtree의 메타 데이터(디렉토리 위치, 속성 이름 등)
- Commit : 커밋 순간의 스냅샷

## Git Process Flow

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/54ea5ca1-2be2-44be-b628-3833ff558d19/Untitled.png)

### Local

- working directory : 변경 사항이 발생하는 곳
- staging area : 변경 사항을 저장하는 곳
    - 여러 개의 변경 사항이 발생했을 때 특정 파일만 골라서 commit이 가능하게 해줌
- localrepo : 변경 사항에 대한 메타 데이터를 생성하는 곳

### Remote

- remote repo : 원격 저장소

## Git 명령어

- git add : 파일을 스테이지에 추가
- git commit : 저장소에 대한 변경 내용 기록
- git status : stage에 올라간 객체 상태 확인
    - -uall :상세 정보 보기
- git push : 로컬 저장소에서 원격 저장소로 객체 업데이트
- git pull : 원격 저장소의 객체를 로컬 저장소로 업데이트
- git clone : 저장소 clone 하기

---

# Github

- Git을 사용해서 웹 서비스를 제공함
- MS가 인수

### 비슷한 서비스

- Bitbucket : jira, confluence, trello 등의 부가도구와 유기적으로 협업, 대기업에서 많이 씀
- Gitlab : 사설 서버 구성이 가능, 보안에 특화됨

---

# README 작성하기

- 맨 위에 한줄 요약
- 목차
    - 설치 방법
    - 시작하는 방법
    - 특징
    - 기술 스택
    - 프로그램이 사회에 기여하는 것(선택)

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
    - ETC.

---

# .gitingnore

<aside>
💡 gitignore 파일을 만들어주는 곳

- https://www.gitignore.io
</aside>

git이 추적하지 않고 무시할 파일이나 폴더 등을 지정함

1. 확장자 무시
    - *.java : java 확장자의 파일 모두 지정
2. 파일명 무시
    - keyfile.* : 파일 이름이 keyfile인 파일 모두 지정
3. 디렉토리 무시
    - hidden/** : hidden 디렉토리에 있는 모든 파일 지정
    

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
- 매일 한번씩 commit해서 잔디밭 만들기

---

# Branch

- 분기점을 생성해서 독립적으로 코드를 변경할 수 있도록 도와주는 모델

## Branch 생성

- git branch [브랜치명]

## 브랜치 삭제

- git branch -D [브랜치명]

## 브랜치 병합

- git merge [병합할 브랜치명]

## Branch 이동

- git checkout [브랜치명]
    - -b 브랜치의 생성과 이동을 동시에
    
    <aside>
    💡 시간이나 공간을 갈아 탈 때도 쓰이지만 브랜치를 복구할 때도 사용해서 문제가 발생해서
    
    - git switch
    - git restore
    </aside>
    
- git switch [브랜치명]
    - -c : 브랜치의 생성과 이동을 동시에

---

# 브랜치 사용 시 유의할 점

- 브랜치 이름 잘 만들자
    - 직관적으로 브랜치 이름만으로 알 수 있도록
- 작업이 끝났으면 바로 삭제하기
- 사용할 브랜치를 모두 push할 필요는 없음
    - 생명 주기가 짧은 경우 main에 병합하고 올리는 것이 더 좋음

## Merge Conflict (충돌)

- 두 개의 다른 브랜치에서 동시 작업이 일어나던 중 코드의 충돌이 일어나는 경우
- Automatic merge가 불가능하기 때문에 직접 겹치는 부분을 수정해줘야 함

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e1c11b22-86b4-4e6c-9182-cfeed9146d3f/Untitled.png)

---

# Remote 저장소

- git push [원격 저장소] [브랜치명]
- git remote : 원격 저장소 확인
    - -v : 저장소 주소 보기
    - add [원격 저장소 이름] [원격 저장소 주소] : 저장소 이름 지정해서 추가
- 팀 단위로 협업 시 다른 팀원의 최신 사항을 참조하는 용도로 만들어서 자주 씀

---

# 기타 등등

<aside>
💡 github 서버 상태 알 수 있음

- [https://www.githubstatus.com/](https://www.githubstatus.com/)
</aside>

## 면접 꿀팁

- 질문 있냐고 물어보면 코드 리뷰는 어떻게 하는지 물어보기
