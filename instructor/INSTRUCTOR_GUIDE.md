# 강사 진행 대본

사전 준비: ZIP을 배포하고 Git, VS Code, GitHub 계정과 네트워크를 확인한다. 비공개 정보 없는 공개 예제 계정·저장소를 시연용으로 준비한다. 참가자는 각자의 계정과 주소를 사용한다. 학생이 개인 정보를 입력하지 않아도 됨을 알린다. 각 실습은 `PRACTICE_STEPS.md`의 상태와 체크 항목을 확인하고 넘어간다.

초보자 지원을 위해 압축 해제 위치, VS Code 터미널의 현재 폴더, 파일 저장 여부, 각자의 원격 주소를 확인한다. 초기 브랜치 이름은 서로 다를 수 있다. 첫 push 전에 빈 저장소 옵션을, PR에서는 base와 compare를 함께 확인한다. 인증 대기나 설치 실패가 발생하면 강사가 개별 지원하고 다음 단계의 체크를 확인한 뒤 진행한다.

## 0–10분: Git과 GitHub
화면: 로컬 파일 → 커밋 이력 → GitHub 그림. 말하기: “저장은 현재 파일을 바꾸고, 커밋은 선택한 변경을 이력으로 남깁니다. GitHub는 그 이력을 공유하는 원격 공간입니다.” 브랜치는 분리된 작업 흐름, PR은 변경을 검토하고 합치자는 요청이다.

## 10–20분: 화면과 연결
GitHub 저장소의 Code, Commits, Branch, Pull requests, Issues를 짚는다. VS Code 탐색기, Source Control과 터미널을 보여준다. ZIP 압축을 풀고 `student_project`를 폴더로 열어 `index.html`을 브라우저에서 확인시킨다. 실제 GitHub 로그인은 브라우저 인증을 따른다.

## 20–40분: 첫 커밋
`PRACTICE_STEPS` A–D를 시연하고 함께 실행한다. init 후에만 로컬 user.name/email을 설정한다. status의 추적되지 않은 파일, add의 스테이징, commit과 log를 순서대로 보여준다. 커밋 성공을 개별 확인한다.

## 40–55분: 수정과 업로드
E에서 `index.html` TODO 1의 제목 또는 소개를 수정하고 diff와 두 번째 커밋을 확인한다. F–H에서 빈 Public 저장소를 만들고 README 등 초기화를 선택하지 않도록 강조한다. 각자의 HTTPS 주소로 origin을 연결해 push하고 GitHub Code와 Commits를 새로고침한다.

## 55–75분: 브랜치와 PR
I–O: feature/profile을 만들고 TODO 2에 새 영역을 추가한다. 저장·커밋·push 후 같은 저장소에서 base `main`, compare `feature/profile` PR을 만들고 Files changed를 확인한다. Merge pull request → Confirm merge 후 로컬 main으로 돌아와 pull한다. 브라우저 새로고침과 log 그래프로 결과를 확인한다.

## 75–80분: 팀 협업
`TEAMWORK_DEMO.md`를 이용해 두 브랜치의 같은 줄 충돌을 보여주고 해결한 뒤 Issue와 Fork를 설명한다. 학생 필수 실습이 아니다.

## 80–90분: 꿀팁
`reference/GITHUB_TIPS.md`에서 공개 저장소 예시로 주소를 바꾸고 각각의 용도와 한계를 보여준다. 서비스가 느리거나 접속되지 않으면 준비된 화면으로 설명하고 실제 접속 성공이라고 말하지 않는다. 마무리: “로컬 commit → push → PR → merge → pull의 방향을 기억하세요.”
