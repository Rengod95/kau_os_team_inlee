#  오픈소스 도서 소개 Git 팀 프로젝트

이 저장소는 "오픈소스 도서 소개 텍스트 기반 Git 팀 프로젝트" 실습을 위한 공간입니다. Git/GitHub 협업 기능, 브랜치 전략, 커밋 메시지, Pull Request, 충돌 해결, 이슈 및 마일스톤 관리를 실습합니다. 주요 작업은 book_list.txt와 markdown_guide.txt 문서 작성 및 관리를 중심으로 진행됩니다.

# 프로젝트 개요

본 프로젝트는 Git 협업 기능을 실습하기 위한 텍스트 기반 프로젝트입니다. GitHub 저장소를 생성하고 브랜치, 커밋, PR, 충돌 해결, 이슈 및 마일스톤 관리 과정을 체험하며, 코드가 아닌 텍스트 문서(book_list.txt, markdown_guide.txt)를 중심으로 실습을 진행합니다.

# 시작하기

## 저장소 클론:

git clone https://github.com/{YOUR_USERNAME}/git-team-project-book-list.git
cd git-team-project-book-list
develop 브랜치로 이동: git checkout develop

# Git Workflow & 협업 규칙

저희 팀은 Git Flow 전략을 기반으로 main, develop, feature 브랜치를 사용하여 협업합니다. 이 섹션은 효율적인 팀 프로젝트를 위한 핵심 협업 규칙을 담고 있습니다.

##  브랜치 관리 방식

### main 브랜치:

항상 최종 릴리스 버전의 안정적인 코드를 유지합니다.

develop 브랜치에서 통합된 기능들이 충분한 테스트를 거쳐 완료된 후 병합됩니다.

절대 직접 커밋하지 않습니다. develop 브랜치로부터의 Pull Request만 허용하며, 병합은 팀 리더의 책임 하에 이루어집니다.

### develop 브랜치:

다음 릴리스를 위한 모든 개발 내용이 통합되는 브랜치입니다.

모든 feature 브랜치는 develop 브랜치에서 분기(checkout)하여 시작하고, 작업 완료 후 develop 브랜치로 Pull Request를 통해 병합됩니다.

main 브랜치로의 병합은 팀 리더가 프로젝트의 특정 시점에 수행합니다.

### feature 브랜치:

특정 기능 개발 또는 이슈 해결을 위해 develop 브랜치에서 분기하는 브랜치입니다.

개별 작업이 완료되면 develop 브랜치로 Pull Request를 생성합니다.

## 브랜치 생성 및 작업 흐름:

git checkout develop            # develop 브랜치로 이동

git pull origin develop         # 최신 develop 브랜치 내용 반영

git checkout -b feature/이슈번호-간략설명 # 새 feature 브랜치 생성 및 이동

## 작업 수행

git add .

git commit -m "커밋 메시지"

git push origin feature/이슈번호-간략설명

Use code with caution.

Bash

## 브랜치 네이밍 규칙

main: 프로덕션 릴리스를 위한 안정적인 브랜치.

develop: 개발 통합을 위한 브랜치.

feature/{이슈번호}-{작업__내용__간략__설명}: 기능 개발 또는 특정 이슈 해결을 위한 브랜치._

_예시: feature/1-add-initial-booklist, feature/2-create-markdown-guide, feature/3-update-readme-teaminfo_

## 커밋 메시지 규칙 (Conventional Commits)

_커밋 메시지는 작업 내용을 명확하게 전달하고 프로젝트 이력을 쉽게 추적할 수 있도록 다음 규칙을 따릅니다._

Type : Subject Body Footer

**Type (유형):**

feat: 새로운 기능 추가 (e.g., book_list.txt에 도서 목록 추가)

fix: 버그 수정 (e.g., 오타 수정, 기능 오류 수정)

docs: 문서 관련 변경 (e.g., README.md 업데이트, 가이드 문서 내용 수정)

style: 코드 포맷팅, 세미콜론, 공백 등 (코드 동작에 영향 없음)

refactor: 코드 리팩토링 (기능 변경 없이 코드 구조 개선)

test: 테스트 코드 추가 또는 수정

chore: 빌드 시스템, 패키지 매니저 설정, 기타 유지보수 (생산 코드와 관련 없는 변경)

**Subject (제목):**

50자 이내로 간결하게 작성합니다.

명령형 동사 사용 (e.g., "Add new feature", "Fix bug")

첫 글자는 대문자, 끝에 마침표는 사용하지 않습니다.

**Body (본문):**

선택 사항이지만, 변경 사항에 대한 자세한 설명이 필요할 때 사용합니다.

어떻게 (How), 왜 (Why) 변경했는지 설명합니다.

**Footer (꼬리말):**

선택 사항. 주로 관련 이슈 트래커 ID를 참조할 때 사용합니다.

예시: Closes #123, Resolves #456

**커밋 메시지 예시:**

------------------------
feat: Add initial book list content
Adds 5 sample books to book_list.txt, including title, author, and description.

Closes #1

------------------------

fix: Resolve merge conflict in README.md from develop  

Manually resolved conflict in the Team Members section of README.md,
ensuring both Developer A and Developer B's information is present.

Closes #3

------------------------


# Pull Request (PR) 가이드라인

PR 제목: [Type]: Title (#이슈번호)

커밋 메시지 규칙과 유사하게 작성하며, 관련된 이슈 번호를 반드시 포함합니다.

예시: feat: Add initial book list (#1)

PR 본문 (템플릿): 다음 내용을 포함하여 작성합니다.

## 작업 개요

  

*   이 PR에서 어떤 작업을 했는지 간략하게 설명해주세요.

  

##  주요 변경 사항

  

*   변경된 파일 목록 및 각 파일에서 어떤 내용을 변경했는지 구체적으로 작성해주세요.

    *   `book_list.txt`: 도서 목록 초기 5권 추가

    *   `README.md`: 팀원 정보 섹션에 본인 이름 추가

*   ****특이사항 / 충돌 해결 내용 (해당하는 경우):****

    *   이 PR을 병합하는 과정에서 발생한 충돌 내용과 해결 방법을 상세히 기술합니다.

    *   예: `README.md` 파일의 '팀원 정보' 섹션에서 발생한 충돌을 수동으로 해결하고, 양쪽 변경 사항을 모두 반영했습니다.

  

##  관련 이슈

  

*   이 PR이 해결하는 이슈를 연결합니다. (예: `Closes #1`)

  

## ✅ 체크리스트

  

*   [ ]  커밋 메시지 규칙을 준수했습니다.

*   [ ]  브랜치 네이밍 규칙을 준수했습니다.

*   [ ]  관련 이슈를 연결했습니다.

*   [ ]  (선택) 스크린샷 또는 추가 설명이 필요한 경우 첨부했습니다.

  

##  기타 (리뷰어에게 전달할 내용)

*   리뷰 시 특별히 확인해주었으면 하는 부분이 있다면 작성해주세요.


# 리뷰 및 병합 절차:

PR 생성 후, 최소 1명 이상의 팀원에게 리뷰를 요청합니다.

리뷰어는 변경 사항을 꼼꼼히 확인하고, 필요 시 코멘트를 남깁니다.

모든 코멘트가 해결되고 ****Approve****를 받으면 해당 PR을 병합할 수 있습니다. (팀 리더 또는 지정된 팀원이 최종 병합)

# 라벨 (Labels) 종류 및 규칙

이슈 및 PR의 분류 및 우선순위 지정을 위해 다음 라벨을 사용합니다.

유형 (Type):

documentation: 문서 관련 작업 (README.md, 가이드, 주석 등)

enhancement: 기능 개선 및 새로운 기능 추가

bug: 버그 수정

task: 특정 작업 또는 할 일

chore: 유지보수, 설정 등 비기능적 변경

우선순위 (Priority):

priority: high: 즉시 처리 필요

priority: medium: 빠른 시일 내 처리 필요

priority: low: 낮은 우선순위, 여유 있을 때 처리

상태 (Status):

in progress: 작업 중

needs review: 검토 필요

blocked: 작업 진행 불가 (원인 명시)

resolved: 해결 완료 (PR 병합 후 자동)

# 이슈 (Issues) 관리 규칙

생성: 모든 작업 시작 전, GitHub Issues에 해당 작업을 나타내는 이슈를 생성합니다.

명확하고 간결한 제목을 사용합니다.

이슈 내용에는 작업 목표, 상세 설명, 필요한 경우 참고 자료 등을 포함합니다.

관련 라벨 및 마일스톤을 반드시 할당합니다.

할당: 이슈는 해당 작업을 수행할 팀원에게 할당합니다.

연결: Pull Request 생성 시, 해당 PR이 해결하는 이슈를 반드시 본문에 연결합니다 (예: Closes #이슈번호). PR이 병합되면 이슈는 자동으로 닫힙니다.

# 마일스톤 (Milestones) 관리 규칙

목표 설정: 프로젝트의 큰 단계 또는 목표를 나타내기 위해 마일스톤을 생성합니다.

예시: v1.0.0 - 초기 문서 완성

이슈 그룹화: 관련된 이슈들을 특정 마일스톤에 할당하여 프로젝트 진행 상황을 추적합니다.

진행 상황: 마일스톤 페이지에서 해당 마일스톤에 속한 이슈들의 완료율을 확인할 수 있습니다.

# 팀 정보
팀장 : 이 인 (2021125050 / 소프트웨어학과)
기획자 : 김병진 (2022125008 / 소프트웨어학과)
개발자 : 강정훈 (2024125003 / 소프트웨어학과)

