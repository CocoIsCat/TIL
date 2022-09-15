# Branching models

- git flow
    - (hotfix : 긴급한 버그 수정이 필요할 때 master에 직접 접근해서 해결) - **master** - (release : 배포 주기가 일정한(규칙적인) 서비스를 개발할 때 사용) - **develop** - feature
    - 핵심 브랜치 두 개를 바탕으로 브랜치의 상태를 변경함
    - master 브랜치
        - 프로젝트 매니저(CTO)가 develop 브랜치에서 검증을 거쳐 업데이트
        - 사용자가 사용할 완성된 코드가 들어감
        - 완벽하게 동작해야 함
    - delevop 브랜치
        - 팀원들이 달라 붙어서 기능을 추가함
        - 기능 통합해서 테스트
    - feature 브랜치
        - 팀원 개인이 develop 브랜치에서 따와서 개발을 진행
    - release 브랜치
        - end to end 테스트
        - 브라우저 테스트
        - load 테스트 진행 (과부하 걸어봄)

- github flow
    - main 브랜치에서 featrue 브랜치만 따서 개발
    - 라이브러리 개발 팀들이 많이 씀(데이터 분석 모델 등)
    - 프레임워크 개발 등등
- gitlab flow

---

# Git flow-avh

- 사용하면 여러가지 명령어를 한 번에 해결 가능함

<aside>
💡 Git flow-avh 설치 주소

[https://danielkummer.github.io/git-flow-cheatsheet/index.ko_KR.html](https://danielkummer.github.io/git-flow-cheatsheet/index.ko_KR.html)

</aside>

- gitignore, issue 템플릿 등을 main 브랜치에서 모두 설정한 뒤에 git flow init을 하는 것이 좋음 : main에서 develop 브랜치가 생성됨
- git flow feature start [기능명] : develop에서 feature/[기능명] 브랜치가 생성됨
- git flow feature fihish [기능명] : develop 브랜치로 merge 진행
- git flow release start [버전명]
    - 네이밍 규칙
        - v *.* : 버전 명을 붙임
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