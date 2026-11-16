# 강사용 정답 예시

학생 파일은 개인화한 문구가 달라도 된다. 코드가 저장되고 단계별 커밋과 브랜치가 맞으면 정답이다.

## TODO 1 — 첫 커밋 후 현재 브랜치에서
초기 브랜치 이름은 환경에 따라 다를 수 있다. 뒤의 F–H 단계에서 `git branch -M main`으로 이름을 통일한다.
초기 코드 `<h1>함께 배우며 성장하는 개발자</h1>`를 예를 들어 아래로 교체한다. TODO 주석은 남겨도 된다.
```html
<h1>함께 만드는 즐거움을 배우는 개발자</h1>
```
저장 → `git diff` → `git add index.html` → `git commit -m "Update profile introduction"`. 기존 소개 문장을 바꾸는 것도 정답이다.

## TODO 2 — feature/profile에서
초기 코드의 TODO 2 주석 바로 뒤, `<a class="link" ...>` 앞에 추가한다. 기존 CSS만으로도 정상 표시된다.
```html
<section>
  <h3>관심 분야</h3>
  <p>웹 접근성 배우기</p>
</section>
```
저장 → diff → add → `git commit -m "Add profile interests"` → `git push -u origin feature/profile`. PR을 main으로 병합한 다음 로컬 main에서 pull하면 두 수정이 모두 보인다. 실습 전체 명령과 GUI는 PRACTICE_STEPS 참조.
