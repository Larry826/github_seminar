# 문제 해결

명령은 별도 표시가 없으면 VS Code에서 연 `student_project`의 터미널에서 실행한다. 오류 원문과 `git status`를 확인하고, 비밀번호·토큰은 화면 공유나 채팅에 올리지 않는다.

| 증상 | 확인과 해결 |
|---|---|
| `git --version` 명령을 찾지 못함 | [Git 공식 설치 안내](https://git-scm.com/install/)로 설치 후 VS Code와 터미널을 완전히 다시 열어 확인. Windows는 설치 시 PATH 옵션을 확인하고, macOS는 안내되는 개발자 도구 설치 대화상자를 따른다. |
| 터미널에서는 Git이 되지만 VS Code에서 안 보임 | VS Code 재시작, 올바른 폴더와 Source Control 확인. Windows `Get-Command git`, macOS `which git`으로 실행 파일 확인. VS Code 설정의 Git 실행 경로가 잘못 지정되어 있는지 확인. |
| `not a git repository` | 프로젝트 폴더를 열었는지 Windows `Get-Location`, macOS `pwd`로 확인. 해당 폴더에서 아직 init하지 않았다면 `git init`. 상위 저장소에 중첩하지 않는다. |
| 커밋 시 identity 오류 | init 후 `git config --local user.name "Seminar Student"`와 `git config --local user.email "student@example.com"`. `git config --local --list`로 확인. 이메일은 공개 커밋에 기록될 수 있다. |
| nothing to commit / diff가 비어 있음 | 파일 저장 후 `git status`; 스테이지된 차이는 `git diff --staged`. 이미 커밋했다면 log 확인. |
| GitHub 로그인/인증 실패 | 브라우저에서 올바른 계정 로그인. HTTPS push 시 Git Credential Manager 등의 브라우저 인증 요청을 완료한다. GitHub는 Git HTTPS 계정 비밀번호 인증을 지원하지 않는다. 토큰이 필요한 환경은 [공식 인증 안내](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github)를 따르고, 토큰을 공개하거나 명령에 넣지 않는다. |
| `remote origin already exists` | `git remote -v`로 대상 확인. 이 실습의 원격이 맞다면 add 생략. 잘못된 주소일 때만 `git remote set-url origin https://github.com/YOUR-USER/club-profile.git`에서 자신의 주소로 바꾼다. |
| `src refspec main does not match any` | 첫 커밋 유무를 `git log --oneline`으로 확인하고 `git branch -M main` 후 push. |
| push rejected / non-fast-forward | 빈 저장소인지 GitHub에서 확인. 원격에 README 등이 있으면 기존 내용을 지우거나 강제 push하지 말고 강사와 해결하거나 새 빈 저장소를 만든다. 계정 권한·주소도 확인한다. |
| `switch`가 없음 | Git을 업데이트하거나 생성은 `git checkout -b feature/profile`, 복귀는 `git checkout main` 사용. |
| PR이 없거나 비교 내용이 없음 | `git branch`, `git log --oneline --all`, `git remote -v` 확인 후 feature 브랜치 커밋과 push 확인. 웹에서 같은 저장소의 base main과 compare feature/profile을 선택한다. |
| pull 후 변경이 없음 | PR이 실제 Merged인지, 현재 로컬 브랜치가 main인지 `git branch`로 확인. 웹 main과 origin 주소를 확인. `git pull origin main`도 가능. 미커밋 변경이 방해하면 먼저 내용을 보존하고 강사와 상의한다. |
| 브라우저 스타일 누락 | `index.html`과 `style.css`가 같은 폴더인지 확인하고 저장 후 새로고침한다. |

GitHub 화면이나 인증 절차는 바뀔 수 있다. 공용 컴퓨터에서는 세션 종료에 주의한다.
