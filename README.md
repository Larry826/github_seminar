# Git & GitHub 기초 세미나 자료

90분 입문 세미나를 위한 정적 프로필 실습과 강사용 문서다. PPT, PDF, 인쇄용 A4는 아직 제작하지 않았다.

```text
github_seminar/
├─ student_project/       학생용 초기 파일 (Git 초기화 전)
│  ├─ index.html
│  ├─ style.css
│  ├─ README.md
│  └─ .gitignore
├─ instructor/
│  ├─ INSTRUCTOR_GUIDE.md
│  ├─ PRACTICE_STEPS.md
│  ├─ SOLUTION_GUIDE.md
│  ├─ TROUBLESHOOTING.md
│  ├─ TEAMWORK_DEMO.md
│  ├─ CURRICULUM.md
│  └─ PRESENTATION_NOTES.md
├─ reference/
│  ├─ GIT_COMMANDS.md
│  └─ GITHUB_TIPS.md
└─ dist/
   └─ github_seminar_student.zip
presentation_source.zip   PPT 제작을 위한 원본 자료
```

## 사용과 배포

강사는 `instructor/INSTRUCTOR_GUIDE.md`와 `PRACTICE_STEPS.md` 순서로 진행하고 정답은 `SOLUTION_GUIDE.md`에서 확인한다. `dist/github_seminar_student.zip`만 학생에게 배포한다. 학생은 압축을 풀고 `student_project`를 VS Code에서 폴더로 열어 직접 `git init`한다. 원본 파일에는 예시 값과 두 TODO가 남아 있다. 실제 GitHub 주소는 각자 다르며 강사 자료와 정답은 배포하지 않는다.

## 검증 결과

- PASS: 학생 필수 4개 파일, 상대 CSS 경로, TODO·정답 코드 적용 확인. Chrome의 데스크톱(1280px)과 모바일(390px) 화면에서 스타일·반응형 배치와 가로 넘침을 확인했다.
- PASS: 별도 임시 복사본과 로컬 bare 원격에서 init, 두 커밋, main push, feature 브랜치 작업·push, 별도 복사본의 merge 및 main pull, 이력과 clean 상태 확인. 이는 GitHub 웹 PR을 모사한 로컬 테스트다.
- PASS: ZIP 파일 4개만 포함, CRC 검사, 압축 해제 후 SHA-256 일치. `.git`과 강사 자료 없음. 테스트 임시 폴더 정리 완료.
- 미검증: 실제 GitHub 계정 인증·웹 PR·외부 서비스의 개별 저장소 실행, 실제 macOS와 VS Code GUI에서의 실습. 사용자 저장소나 전역 Git 설정을 변경하지 않았으며 실제 GitHub 저장소 생성·push는 수행하지 않았다.

세미나 전 강사는 Git·VS Code 설치, GitHub 로그인과 네트워크, 공개 데모 저장소와 각 외부 서비스의 접속 가능성을 확인한다. PPT 원고는 `instructor/CURRICULUM.md`, `instructor/PRESENTATION_NOTES.md`, A4 원고는 `reference/`에 있다. `presentation_source.zip`에는 세 폴더와 이 README만 들어 있으며 정답을 포함하므로 학생용으로 배포하지 않는다.
