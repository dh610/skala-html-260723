# YDH Developer Portfolio

GitHub Pages에서 별도 빌드 없이 동작하는 반응형 개인 개발자 포트폴리오입니다.

## 로컬에서 확인하기

저장소 루트에서 다음 명령을 실행합니다.

```bash
python3 -m http.server 8000
```

브라우저에서 `http://localhost:8000/`을 엽니다.

## 내용 수정하기

모든 페이지 내용과 스타일은 `index.html`에 있습니다.

- 소개 문구: `hero`, `about` 섹션
- 기술 목록: `skills` 섹션의 `skill-list`
- 프로젝트: `projects` 섹션의 `project-card`
- 연락처: `contact` 섹션
- 색상과 간격: `<style>`의 `:root` 변수

준비되지 않은 주소에는 빈 링크를 넣지 말고 “준비 중” 문구를 사용합니다.

## GitHub Pages 배포

1. GitHub 저장소의 **Settings → Pages**로 이동합니다.
2. **Build and deployment**의 Source를 **Deploy from a branch**로 선택합니다.
3. Branch를 `main`, 폴더를 `/(root)`로 선택하고 저장합니다.
4. 배포가 완료되면 Pages에 표시된 주소로 접속합니다.

이 저장소 이름을 유지하면 기본 주소는 `https://dh610.github.io/skala-html-260723/`입니다. 사용자 대표 페이지인 `https://dh610.github.io/`를 사용하려면 저장소 이름을 `dh610.github.io`로 변경하거나 같은 이름의 별도 저장소에 페이지를 배포해야 합니다.
