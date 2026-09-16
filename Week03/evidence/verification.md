## 1차 검증 (Claude Code 실행 실패 후 학생 직접 작성)

| 주장 | 확인한 실제 경로 | 결과 | 학생의 처리 |
|---|---|---|---|
| 저장소 목적은 현재 확인할 수 없다 | 저장소 루트, `git status --short --branch` | 일치 | 목적을 추측하지 않고 미확인으로 표시했다. |
| `Week03/`은 제출 증거를 담는다 | `Week03/README.md`, `Week03/docs/`, `Week03/evidence/` | 일치 | 문서 역할을 실제 제출 구조에 맞게 기록했다. |
| 애플리케이션 실행 방법은 확인할 수 없다 | 저장소 루트 파일 목록, `Week03/evidence/clone_state.txt` | 일치 | 확인되지 않은 실행 명령을 추가하지 않았다. |

Claude Code는 이 터미널에서 로그인되지 않은 상태로 확인되어 최초 요청을 실행하지 못했다. 따라서 `ai_initial.md`는 Claude 출력이 아니라, 실행 실패 후 실제 파일 상태를 근거로 작성한 보존 초안이다.

## 2차 검증 (Claude Code 로그인 후 실제 실행)

Claude Code가 로그인된 상태에서 실제로 실행되어 `Week03/docs/repository_overview.md`를 새로 작성했다. 커밋 SHA: `eb1b6c1`.

| 주장 (Claude Code 출력) | 확인한 실제 경로 | 결과 |
|---|---|---|
| 저장소는 GitHub + AI 에이전트 연동 실습 과제 제출용이다 | `Week03/README.md` (제목 및 각 섹션) | 일치 |
| 저장소 루트에 프로젝트 소스 파일이 없다 | 저장소 루트 파일 목록 (`.git/`, `Week03/` 외 없음) | 일치 |
| clone 직후 main 브랜치에 커밋이 없었다 | `Week03/evidence/clone_state.txt` ("No commits yet on main") | 일치 |
| 원격 주소는 `https://github.com/JsonParc/2025240014jimin`이다 | `Week03/evidence/clone_state.txt` (origin fetch/push) | 일치 |
| Claude Code 최초 실행은 로그인 오류로 실패했다 | `Week03/evidence/diff_check.txt` ("Not logged in; Please run /login") | 일치 |
| `ai_initial.md`는 Claude 직접 출력이 아니라 학생 작성 초안이다 | `Week03/evidence/verification.md` 1차 검증 비고 | 일치 |
| 에이전트 버전은 Claude Code `2.1.50`이다 | `Week03/evidence/environment.txt` (Agent version) | 일치 |
| 강의/과목명은 파일에서 확인할 수 없다 | `Week03/README.md` (강의 정보 없음) | 일치 |
