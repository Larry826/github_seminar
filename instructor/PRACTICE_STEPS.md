# 학생 실습 단계

각 명령은 별도 표시가 없으면 VS Code에서 **압축을 푼 `student_project` 폴더**를 열고 터미널 → 새 터미널에서 실행한다. Windows는 PowerShell, macOS는 기본 터미널(zsh 등) 모두 아래 Git 명령이 같다. 프롬프트에 경로가 보이는지 확인하고, Windows `Get-Location`, macOS `pwd`로 현재 위치를 확인한다. 경로가 다르면 VS Code에서 올바른 폴더를 다시 열고 새 터미널을 연다. `<...>`는 설명용이므로 괄호까지 자신의 값으로 바꾼다. 명령의 출력은 Git 버전과 환경에 따라 다르다. GUI 명칭은 VS Code 버전에 따라 다를 수 있다.

## A. 폴더 열기
- 전: ZIP 다운로드. 압축을 푼 뒤 VS Code 파일 → 폴더 열기에서 `student_project` 선택. 파일 탐색기에서 `index.html`을 브라우저로 열기.
- 결과: 프로필이 보인다. 오류: CSS가 없다면 두 파일이 같은 폴더인지 확인.
- 체크: [ ] 탐색기에 index.html과 style.css가 보인다. [ ] 브라우저에서 화면 확인.

## B–C. Git 확인과 초기화
- 전: 프로젝트 폴더, Git 설치. 터미널에서 실행:
```sh
git --version
git init
git config --local user.name "Seminar Student"
git config --local user.email "student@example.com"
git config --local --get user.name
git config --local --get user.email
```
- 결과: Git 버전과 Initialized empty Git repository, 설정값 표시. 이름·이메일은 예시로 가능하며 공개 커밋에 기록된다. GitHub 기여 연결을 원할 때는 계정에 등록한 이메일 또는 GitHub 제공 noreply 주소를 사용한다. 기존 전역 설정을 변경하지 않는다.
- GUI: Source Control → Initialize Repository. 사용자 정보는 위 터미널 명령을 init 이후 사용한다.
- 주의/오류: git을 찾지 못하면 설치 후 VS Code를 재시작한다. 상위 폴더가 이미 Git 저장소라면 강사에게 알리고 독립된 폴더에서 진행한다.
- 체크: [ ] 버전과 로컬 사용자 정보 확인. [ ] 프로젝트에 저장소 초기화.

## D. 첫 커밋
- 전: 초기화 후 프로젝트 폴더. 아래를 순서대로 실행한다.
```sh
git status
git add .
git status
git commit -m "Add profile starter"
git log --oneline
```
- 결과: 처음에는 untracked files, add 후 staged changes, 커밋 후 짧은 해시와 메시지가 보인다. 해시는 개인마다 다르다.
- 주의: 초기 브랜치 이름은 설정에 따라 `main` 또는 다른 이름일 수 있으며 F–H에서 `main`으로 바꾼다. 이력이 화면에 멈추고 하단에 `:` 또는 `(END)`가 표시되면 `q`를 눌러 빠져나온다.
- GUI: Source Control 변경 목록 옆 +로 스테이징 → 메시지 입력 → Commit. `...` 메뉴에서 이력 또는 터미널의 log 확인.
- 오류: author identity 오류는 B의 로컬 설정 확인; nothing to commit이면 파일 저장과 status 확인.
- 체크: [ ] 첫 커밋이 log에 보인다.

## E. 제목 수정과 두 번째 커밋
- 전: 첫 커밋 완료. `index.html`의 TODO 1 아래 `<h1>` 또는 다음 소개 문장을 바꾸고 저장, 브라우저 새로고침.
```sh
git status
git diff
git add index.html
git commit -m "Update profile introduction"
git log --oneline
```
- 결과: diff에 기존 줄 `-`, 새 줄 `+`가 보이고 이력에 두 커밋이 보인다. 이미 stage했다면 `git diff --staged`로 확인한다.
- GUI: Source Control에서 index.html을 클릭해 비교 → + → 메시지와 Commit.
- 오류: diff가 비면 저장 여부와 스테이징 여부 확인.
- 체크: [ ] 화면과 diff에서 바뀐 내용 확인. [ ] 두 번째 커밋 완료.

## F–H. 빈 원격 저장소와 업로드
- 전: 두 커밋 완료, GitHub 로그인. GitHub의 New repository에서 예시 이름 `club-profile`을 정하고 Public 선택. **Add README, .gitignore, LICENSE를 모두 추가하지 않고** Create repository. 각자 계정·저장소 주소가 다르다. HTTPS 주소를 Code 또는 생성 직후 화면에서 복사한다.
- 프로젝트 터미널에서 아래 주소 전체를 자신의 실제 HTTPS 주소로 교체한다. `YOUR-USER`를 그대로 실행하지 않는다.
```sh
git branch -M main
git remote add origin https://github.com/YOUR-USER/club-profile.git
git remote -v
git push -u origin main
```
- 결과: push 성공 후 GitHub 저장소 새로고침 시 파일과 Commits의 두 커밋이 보인다. 원격이 빈 저장소여야 충돌을 피한다.
- GUI: 왼쪽 아래 브랜치 이름으로 이름 변경 가능; Source Control의 `...` → Remote → Add Remote에서 origin과 주소 입력 후 `...` → Push 또는 Publish Branch. UI가 다르면 위 명령 사용. 인증 화면이 뜨면 브라우저에서 GitHub 로그인·승인을 진행한다. 계정 비밀번호를 터미널에 넣지 않는다.
- 오류: origin already exists는 `git remote -v` 확인 후 문제 해결 문서 참조; rejected는 원격의 기존 내용을 확인하고 강사 도움을 받는다.
- 체크: [ ] GitHub Code에 파일 표시. [ ] Commits에서 이력 확인.

## I–K. 새 브랜치에서 작업
- 전: main push 완료. 프로젝트 터미널:
```sh
git switch -c feature/profile
git branch
```
- `index.html`의 TODO 2 바로 아래, GitHub 링크 앞에 관심 기술·취미·목표 중 하나를 담은 HTML 영역을 추가하고 저장한다. 예: `<section><h3>관심 분야</h3><p>웹 접근성 배우기</p></section>`. 브라우저 새로고침.
```sh
git diff
git add index.html
git commit -m "Add profile interests"
git push -u origin feature/profile
```
- 결과: branch 출력의 `* feature/profile`, 새 영역 및 push 성공. 기존 Git에 switch가 없으면 `git checkout -b feature/profile`을 사용한다.
- GUI: 왼쪽 아래 브랜치 → Create new branch → 이름 입력 → 수정과 스테이징·Commit → Publish Branch.
- 오류: 전환 거절 시 저장하지 않은 변경과 status 확인; push 인증은 문제 해결 문서 참조.
- 체크: [ ] feature/profile에서 커밋. [ ] GitHub에 해당 브랜치 표시.

## L–M. Pull Request와 Merge
- 전: feature/profile push 완료. GitHub 저장소에서 Compare & pull request 또는 Pull requests → New pull request 선택. **base: main**, **compare: feature/profile**을 같은 자기 저장소로 선택한다. Create pull request, Files changed 확인, Merge pull request → Confirm merge.
- 결과: PR이 Merged 상태가 되고 GitHub main의 index.html에 새 영역이 있다. 자기 PR이라도 실습상 직접 merge한다.
- GUI: 이 단계는 GitHub 웹에서 진행한다. VS Code 확장 없이도 가능하다.
- 오류: 비교할 변경이 없다면 base/compare와 push한 브랜치를 확인. Merge 버튼이 막히면 저장소 규칙·권한을 확인한다.
- 체크: [ ] PR의 변경 확인. [ ] Merged 표시 확인.

## N–O. 로컬 동기화와 이력
- 전: GitHub에서 merge 완료. 프로젝트 터미널:
```sh
git switch main
git pull
git branch
git log --oneline --graph --all
git status
```
- 결과: pull 후 로컬 index.html에 새 영역이 보이고 status는 working tree clean. 그래프 모양은 GitHub merge 방식에 따라 다르다. 브라우저 새로고침한다. 구버전은 `git checkout main`을 사용한다.
- 주의: 로그가 페이지 단위로 열리면 `q`를 눌러 종료한다. PR을 merge해도 로컬 파일은 pull 전까지 자동으로 바뀌지 않는다.
- GUI: 왼쪽 아래에서 main 선택 → Source Control `...` → Pull → 파일 및 이력 확인.
- 오류: pull 전에 수정 사항이 남았다면 status를 확인하고 강사와 처리한다. upstream이 없다면 `git pull origin main`을 사용한다.
- 체크: [ ] 로컬 main에서 영역 확인. [ ] branch와 log 확인.
