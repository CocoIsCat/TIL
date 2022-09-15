# Branching models

- git flow
    - (hotfix) - **master** - (release) - **develop** - feature
    - 핵심 브랜치 두 개를 바탕으로 브랜치의 상태를 변경함
    - **master 브랜치**
        - 프로젝트 매니저(CTO)가 develop 브랜치에서 검증을 거쳐 업데이트
        - 사용자가 사용할 완성된 코드가 들어감
        - 완벽하게 동작해야 함
    - **delevop 브랜치**
        - 팀원들이 달라 붙어서 기능을 추가함
        - 기능 통합해서 테스트
    - feature 브랜치
        - 팀원 개인이 develop 브랜치에서 따와서 개발을 진행
    - hotfix 브랜치
        - 긴급한 버그 수정이 필요할 때 master 브랜치에 직접 접근해서 수정
    - release 브랜치
        - 배포 주기가 일정한(규칙적인) 서비스를 개발할 때 사용
        - 배포 전 테스트를 진행함
            - End to End 테스트
            - 브라우저 테스트
            - Load Test 진행 (과부하 걸어봄)
- github flow
    - main 브랜치에서 featrue 브랜치만 따서 개발
    - 라이브러리 개발 팀들이 많이 씀(데이터 분석 모델 등)
    - 프레임워크 개발 등등
- gitlab flow
    - 잘 안 씀

---

# Git flow-avh

- git flow를 사용하면 git에서 사용하는 여러 가지 명령어를 한 번에 해결 가능함

<aside>
💡 Git flow-avh 설치 주소

[https://danielkummer.github.io/git-flow-cheatsheet/index.ko_KR.html](https://danielkummer.github.io/git-flow-cheatsheet/index.ko_KR.html)

</aside>

<aside>
💡 mac의 경우

- brew install git flow-avh
</aside>

- git flow init : main에서 develop 브랜치가 생성됨
    - gitignore, issue 템플릿 등을 main 브랜치에서 모두 설정한 뒤에 하는 것이 좋음
- git flow feature start [기능명] : develop에서 feature/[기능명] 브랜치가 생성됨
- git flow feature finish [기능명] : develop 브랜치로 merge 진행
- git flow release start [버전명]
    - 버전 네이밍 규칙
        - v 0.* : 베타 버전
        - v 1.* : 정식 출시 버전
        - 버전 업은 두 버전 사이에 많은 변화가 있거나 도저히 호환이 되지 않을 경우 진행
- git flow release finish [버전명] : 마지막 상태를 develop에 하나 main에 하나 전달함
    - vim 창이 세개 나옴
        1. main으로 merge
        2. 태그 메세지 작성
        3. develop으로 merge
- release가 끝나면 push 진행
    - develop에서 push 진행
        - git push -u origin [로컬 브랜치] : 로컬에는 있는 브랜치가 원격에는 없을 때 사용
    - main에서 push 진행
    - tag push 진행
        - git push —tags : tag push

---

# Static Site Generator

- 초기 웹사이트는 모두 정적인 사이트였음
- 90년대 중반에 lamp stack이 등장함
- 리눅스 OS, Apache, mysql 등의 기술이 등장함
- 사용자의 request에 따라 동적인 컨텐츠 구성이 가능해짐

1. Jekyll : Ruby 기반 정적인 블로그 생성기
    - 설치와 사용이 쉬움
    - 망해가는 언어를 사용해서 인기가 없음
2. Hugo : Golang 기반 블로그 생성기
    - 컨텐츠가 많아지면 유리함
    - 설치가 까다로움
3. Haxo : node 기반 블로그 생성기
    - 사용 방법
        1. node 설치
            - brew install node
        2. node 설치 확인
            1. node -v
            2. npm -v
        3. hexo.io로 이동
        4. `최상위 폴더에서 npm install -g hexo-cli`
        5. 원하는 폴더로 이동해서 hexo init [블로그명]
        6. npm install : 누락된 패키지 추가 설치
        7. `hexo new [layout] <title>` : 새 포스트나 페이지 생성
        8. hexo generate
        9. hexo server
            - 서버 열기
        10. Git에서 repo 생성
            - repo 이름은 반드시 Git 유저 이름.github.io
        11. one-command deployment 설정
            1. npm install hexo-deployer-git -- save
        12. User 이름, 블로그 이름 설정
            1. _config.yml 수정
                1. deploy 설정
        13. hexo clean && hexo generate 수행
            1. public 비워줘야함
        14. hexo deploy
        15. 테마 설정
            1. next 테마 예쁨

---

# 기타 등등

- 페이지 새로고침은 command + R 대신 command + shift + R로
    - 캐시를 삭제 하면서 해줘야 함
