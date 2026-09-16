# 저장소 개요

## 1. 저장소의 목적

이 저장소는 GitHub 저장소와 AI 코딩 에이전트 연동 작업 흐름을 실습하는 학생 과제 제출용 저장소다. 과제는 저장소를 clone하고, AI 에이전트(Claude Code)를 사용하여 저장소를 분석한 뒤, 그 결과와 증거 파일을 commit·push하는 과정으로 구성된다.

근거: `Week03/README.md` (제목 "GitHub 저장소와 AI 코딩 에이전트 작업 흐름" 및 각 섹션 내용), `Week03/evidence/ai_prompt.md` (과제 지시 내용)

저장소 루트에는 프로젝트 소스 파일이나 루트 README가 없다. clone 직후 main 브랜치에 커밋이 없었다는 사실도 확인된다.

근거: `Week03/evidence/clone_state.txt` ("No commits yet on main...origin/main [gone]"), 저장소 루트 파일 목록 (`.git/`, `Week03/` 외 파일 없음)

---

## 2. 주요 디렉터리와 파일의 역할

### `Week03/`
Week 3 과제 제출 최상위 디렉터리다. 하위에 `docs/`와 `evidence/`가 있다.

근거: 저장소 루트 파일 목록 (유일한 하위 디렉터리)

### `Week03/README.md`
Week 3 실습의 전체 흐름을 기록한 주 문서다. 사용 환경, clone 및 원격 저장소 확인, AI 에이전트 실행 결과, 학생 검증 과정, commit/push 결과, 문서 링크를 담고 있다.

근거: `Week03/README.md` (전체 내용)

### `Week03/docs/repository_overview.md`
AI 에이전트가 실제 파일을 읽고 작성하는 저장소 분석 문서다. 현재 이 파일이 해당 문서다.

근거: `Week03/evidence/ai_prompt.md` (이 파일 생성 지시 내용), `Week03/README.md` (문서 섹션의 링크 대상)

### `Week03/evidence/ai_prompt.md`
AI 에이전트에게 전달된 과제 지시 내용을 담은 파일이다. 실제 파일을 먼저 읽고 추측 없이 문서를 작성하도록 지시한다.

근거: `Week03/evidence/ai_prompt.md` (전체 내용)

### `Week03/evidence/ai_initial.md`
Claude Code가 로그인되지 않아 최초 실행에 실패한 후, 학생이 실제 파일 상태를 근거로 직접 작성한 초안이다. Claude가 직접 생성한 출력이 아님이 명시되어 있다.

근거: `Week03/evidence/verification.md` (마지막 문단: "ai_initial.md는 Claude 출력이 아니라, 실행 실패 후 실제 파일 상태를 근거로 작성한 보존 초안이다")

### `Week03/evidence/clone_state.txt`
`git remote -v`, `git branch`, `git status --short --branch` 결과를 기록한 파일이다. 원격 주소(`https://github.com/JsonParc/2025240014jimin`), 브랜치(`main`), clone 직후 커밋 없음 상태를 확인할 수 있다.

근거: `Week03/evidence/clone_state.txt` (전체 내용)

### `Week03/evidence/content_commit.txt`
첫 번째 콘텐츠 commit의 SHA를 기록한 파일이다. 값은 `97d8555`다.

근거: `Week03/evidence/content_commit.txt` (전체 내용)

### `Week03/evidence/diff_check.txt`
Claude Code 최초 실행 결과(실패, 원인: Not logged in), 첫 번째 content commit SHA, `git diff --check` 통과 여부, 예상 변경 범위(`Week03/`)를 기록한 파일이다.

근거: `Week03/evidence/diff_check.txt` (전체 내용)

### `Week03/evidence/environment.txt`
작업 환경 정보를 기록한 파일이다. OS(Windows), Git 버전(`2.47.1.windows.2`), 선택한 에이전트(Claude Code), 에이전트 버전(`2.1.50`), 실행 계획을 담고 있다.

근거: `Week03/evidence/environment.txt` (전체 내용)

### `Week03/evidence/verification.md`
학생이 AI 초안의 주요 주장 세 가지를 실제 경로와 대조한 검증 표와, Claude Code 로그인 실패 사실을 기록한 파일이다.

근거: `Week03/evidence/verification.md` (전체 내용)

---

## 3. 현재 확인 가능한 실행 또는 사용 방법

### Git 저장소 clone
```
git clone https://github.com/JsonParc/2025240014jimin
```
근거: `Week03/evidence/clone_state.txt` (origin 원격 주소)

### Claude Code 실행 (에이전트 구동)
에이전트는 Claude Code(`2.1.50`)이며, clone한 저장소 루트에서 실행하도록 계획되어 있었다. 실행 전 로그인이 필요하다(`/login`).

근거: `Week03/evidence/environment.txt` (에이전트 버전, 실행 계획), `Week03/evidence/diff_check.txt` ("Not logged in; Please run /login")

저장소에 별도의 애플리케이션 소스 코드, 빌드 스크립트, 실행 스크립트, `package.json`, `requirements.txt`, `Makefile` 등은 존재하지 않는다. 따라서 현재 파일 기준으로 AI 에이전트 구동 외에 확인 가능한 실행 방법은 없다.

근거: 저장소 전체 파일 목록 (위 파일들 부재 확인)

---

## 4. 파일에서 확인할 수 없는 정보와 추가 확인이 필요한 점

- **이 저장소가 속한 강의/과목명**: `Week03/README.md`에 과제 구조가 있으나 강의명이나 과목 코드는 기재되어 있지 않다. 근거: `Week03/README.md` (강의 정보 없음)

- **AI 에이전트가 실제로 생성한 출력물**: Claude Code가 로그인 오류로 실행에 실패했으므로, `ai_initial.md`는 Claude의 직접 출력이 아니다. 로그인 후 재실행 결과가 현재 파일에는 없다. 근거: `Week03/evidence/diff_check.txt`, `Week03/evidence/verification.md`

- **Week01, Week02 또는 이후 주차 제출 디렉터리**: 저장소에 `Week03/` 외의 주차 디렉터리가 없다. 다른 주차 과제가 있는지 확인할 수 없다. 근거: 저장소 루트 파일 목록 (`Week03/` 외 없음)

- **저장소에 추가될 프로젝트 파일의 내용**: 현재 프로젝트 소스 파일이 없으므로 향후 추가될 파일의 목적, 의존성, 실행 방법은 파일이 추가된 뒤 다시 확인해야 한다. 근거: 저장소 루트 파일 목록 (소스 파일 부재)

- **원격 저장소의 현재 상태**: `clone_state.txt`는 clone 직후 시점의 스냅샷이다. 원격 저장소에 이후 변경이 있었는지는 현재 파일만으로 확인할 수 없다. 근거: `Week03/evidence/clone_state.txt`
