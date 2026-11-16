# Git 명령어 원고

실습 명령은 `../instructor/PRACTICE_STEPS.md`가 기준이다. 아래는 나중에 유인물로 편집할 참고 원고다. 달리 적지 않으면 **해당 Git 저장소 폴더의 터미널**에서 실행한다. 주소·파일·브랜치명은 예시다. `git switch`는 구버전에서 `git checkout`을 사용할 수 있다.

| 명령 | 예시 | 의미와 주의 |
|---|---|---|
| init | `git init` | 현재 프로젝트 폴더에 저장소 생성. 상위 저장소 중첩 주의 |
| clone | `git clone https://github.com/OWNER/REPO.git` | **저장소가 아닌 원하는 부모 폴더**에서 원격을 새 폴더에 복제 |
| status | `git status` | 현재 브랜치와 변경·스테이징 상태 |
| add | `git add index.html` | 해당 파일의 현재 변경을 스테이징 |
| commit | `git commit -m "Update profile"` | 스테이징한 변경을 기록 |
| log | `git log --oneline --graph --all` | 이력과 브랜치 그래프. 종료는 q |
| diff | `git diff` / `git diff --staged` | 미스테이징 / 스테이징 변경 비교 |
| branch | `git branch` | 로컬 브랜치 확인 |
| switch | `git switch -c feature/profile` / `git switch main` | 새 브랜치 생성·전환 / main 전환 |
| merge | `git merge feature/profile` | 현재 브랜치에 대상 브랜치 병합. 충돌 시 해결 후 커밋 |
| fetch | `git fetch origin` | 원격 변경 정보만 가져옴. 작업 파일에 자동 반영하지 않음 |
| pull | `git pull` | 현재 추적 원격에서 가져와 현재 브랜치에 통합. 설정에 따라 merge 또는 rebase |
| push | `git push -u origin main` | 로컬 main을 원격에 올리고 추적 관계 설정 |
| rebase | `git rebase main` | 현재 브랜치의 커밋을 main 위에 다시 적용. 공유된 이력 변경에 주의 |
| revert | `git revert <commit>` | 지정 커밋을 되돌리는 새 커밋 생성 |
| bisect | `git bisect start`, `git bisect bad`, `git bisect good <commit>` | 정상·문제 구간을 이분 탐색. 종료는 `git bisect reset` |
| blame | `git blame index.html` | 줄별 마지막 변경 커밋과 작성자 확인 |

merge, rebase, revert, bisect는 상태를 바꿀 수 있다. 임의의 실제 저장소에서 연습하지 말고 별도 실습 저장소에서 먼저 익힌다.
