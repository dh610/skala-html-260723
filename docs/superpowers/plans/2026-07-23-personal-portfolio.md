# Personal Portfolio Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the existing HTML exercise page with a responsive, accessible, clean-modern developer portfolio that GitHub Pages can serve directly.

**Architecture:** Keep the portfolio as a single static `index.html` containing semantic HTML, embedded CSS, and no runtime dependencies. Use fragment links for navigation, CSS for visual behavior, and ordinary external links for GitHub so the page works without a build or JavaScript runtime.

**Tech Stack:** HTML5, embedded CSS, Git, GitHub Pages

## Global Constraints

- Keep `index.html` as the GitHub Pages entry point.
- Keep HTML and CSS in `index.html`; do not add a framework, package manager, build tool, or external font.
- Do not make external data requests or add server-side behavior.
- Use a balanced one-page layout with a clean-modern visual style.
- Use a light neutral background, dark body text, and blue only for links, primary actions, and small accents.
- Use example copy where personal content is not yet available, and never present an unavailable destination as a working link.
- Support desktop and mobile layouts, keyboard navigation, visible focus, and reduced-motion preferences.

## File Structure

- Modify: `index.html` — the complete portfolio document, embedded styles, content, navigation, and accessibility behavior.
- Modify: `README.md` — local preview, content customization, and GitHub Pages publishing instructions.
- Reference: `docs/superpowers/specs/2026-07-23-personal-portfolio-design.md` — approved requirements and validation checklist.

---

### Task 1: Semantic Portfolio Structure and Example Content

**Files:**
- Modify: `index.html:1-18`

**Interfaces:**
- Consumes: The browser's native support for semantic HTML and fragment identifiers.
- Produces: The stable section IDs `about`, `skills`, `projects`, and `contact`, plus the CSS class names used by Task 2.

- [ ] **Step 1: Verify the portfolio structure does not exist yet**

Run:

```bash
rg -n '<main|id="about"|id="skills"|id="projects"|id="contact"' index.html
```

Expected: no matches and exit status `1`.

- [ ] **Step 2: Replace the exercise markup with the complete semantic structure**

Replace `index.html` with:

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta
        name="description"
        content="문제를 이해하고 쓸모 있는 제품을 만드는 개발자 YDH의 포트폴리오"
    >
    <title>YDH | Developer Portfolio</title>
</head>
<body>
    <header class="site-header">
        <nav class="container nav">
            <a class="brand" href="#top">YDH.</a>
            <ul class="nav-links">
                <li><a href="#about">소개</a></li>
                <li><a href="#skills">기술</a></li>
                <li><a href="#projects">프로젝트</a></li>
                <li><a href="#contact">연락처</a></li>
            </ul>
        </nav>
    </header>

    <main id="top">
        <section class="hero container">
            <p class="eyebrow">Software Developer</p>
            <h1>문제를 이해하고,<br>쓸모 있는 제품으로 만듭니다.</h1>
            <p class="hero-description">
                사용자 경험과 견고한 구현을 함께 고민하며,
                배운 것을 실제 결과물로 연결하는 개발자 YDH입니다.
            </p>
            <div class="hero-actions">
                <a class="button button-primary" href="#projects">프로젝트 보기</a>
                <a
                    class="button button-secondary"
                    href="https://github.com/dh610"
                    target="_blank"
                    rel="noreferrer"
                >
                    GitHub
                </a>
            </div>
        </section>

        <section class="section" id="about">
            <div class="container section-grid">
                <div>
                    <p class="section-kicker">01 · About</p>
                    <h2>좋은 질문에서<br>개발을 시작합니다.</h2>
                </div>
                <div class="section-copy">
                    <p>
                        기능을 구현하기 전에 누구의 어떤 문제를 해결하는지 먼저 생각합니다.
                        읽기 쉬운 코드와 자연스러운 사용자 경험을 함께 만드는 것이 목표입니다.
                    </p>
                    <p>
                        현재는 웹의 기본기를 단단히 다지는 동시에,
                        다양한 프로젝트를 통해 제품 개발의 전체 흐름을 배우고 있습니다.
                    </p>
                </div>
            </div>
        </section>

        <section class="section section-muted" id="skills">
            <div class="container">
                <p class="section-kicker">02 · Skills</p>
                <h2>현재 다루는 기술</h2>
                <ul class="skill-list">
                    <li>HTML</li>
                    <li>CSS</li>
                    <li>JavaScript</li>
                    <li>Git</li>
                    <li>GitHub</li>
                </ul>
            </div>
        </section>

        <section class="section" id="projects">
            <div class="container">
                <div class="section-heading">
                    <div>
                        <p class="section-kicker">03 · Projects</p>
                        <h2>선택한 프로젝트</h2>
                    </div>
                    <p>문제를 발견하고 결과물로 완성한 과정을 소개합니다.</p>
                </div>

                <div class="project-grid">
                    <article class="project-card">
                        <div class="project-number">01</div>
                        <div>
                            <p class="project-type">Web · Portfolio</p>
                            <h3>개인 개발자 포트폴리오</h3>
                            <p>
                                별도 빌드 없이 GitHub Pages에서 동작하는
                                반응형 원페이지 포트폴리오입니다.
                            </p>
                            <ul class="project-tags">
                                <li>HTML</li>
                                <li>CSS</li>
                                <li>GitHub Pages</li>
                            </ul>
                        </div>
                        <a
                            class="project-link"
                            href="https://github.com/dh610/skala-html-260723"
                            target="_blank"
                            rel="noreferrer"
                        >
                            저장소 보기 <span aria-hidden="true">↗</span>
                        </a>
                    </article>

                    <article class="project-card">
                        <div class="project-number">02</div>
                        <div>
                            <p class="project-type">Next · Project</p>
                            <h3>다음 프로젝트</h3>
                            <p>
                                새로운 문제를 해결한 프로젝트가 완성되면
                                목적, 기여, 기술과 함께 이곳에 소개합니다.
                            </p>
                            <ul class="project-tags">
                                <li>Planning</li>
                                <li>Development</li>
                            </ul>
                        </div>
                        <span class="project-status">준비 중</span>
                    </article>
                </div>
            </div>
        </section>

        <section class="section contact" id="contact">
            <div class="container contact-inner">
                <div>
                    <p class="section-kicker">04 · Contact</p>
                    <h2>함께 이야기해요.</h2>
                    <p>새로운 기회와 개발 이야기를 언제든 환영합니다.</p>
                </div>
                <a
                    class="button button-primary"
                    href="https://github.com/dh610"
                    target="_blank"
                    rel="noreferrer"
                >
                    GitHub에서 연락하기
                </a>
            </div>
        </section>
    </main>

    <footer class="site-footer">
        <div class="container footer-inner">
            <p>© 2026 YDH</p>
            <a href="#top">맨 위로</a>
        </div>
    </footer>
</body>
</html>
```

- [ ] **Step 3: Verify the document language, metadata, landmarks, and section targets**

Run:

```bash
rg -n 'lang="ko"|name="description"|<header|<nav|<main|<section|<footer|id="about"|id="skills"|id="projects"|id="contact"' index.html
```

Expected: matches for the Korean language, description, all five landmark element types, and all four section IDs.

- [ ] **Step 4: Verify every internal navigation target exists**

Run:

```bash
python3 -c 'import re, pathlib; text=pathlib.Path("index.html").read_text(); ids=set(re.findall(r"id=\"([^\"]+)\"", text)); refs=set(re.findall(r"href=\"#([^\"]+)\"", text)); missing=sorted(refs-ids); print("internal links: OK" if not missing else f"missing: {missing}"); raise SystemExit(bool(missing))'
```

Expected: `internal links: OK`.

- [ ] **Step 5: Commit the semantic portfolio**

Run:

```bash
git add index.html
git commit -m "feat: add portfolio content structure"
```

Expected: one commit containing only `index.html`.

---

### Task 2: Clean-Modern Responsive Styling

**Files:**
- Modify: `index.html` inside `<head>`, immediately before `</head>`

**Interfaces:**
- Consumes: All class names and section IDs created in Task 1.
- Produces: The clean-modern desktop layout, mobile layout, buttons, skill tags, project cards, and contact section.

- [ ] **Step 1: Verify the design tokens and responsive layout do not exist**

Run:

```bash
rg -n -- '--color-primary|@media \\(max-width: 760px\\)|\\.project-grid' index.html
```

Expected: no matches and exit status `1`.

- [ ] **Step 2: Add the complete base and responsive styles**

Insert this block immediately before `</head>`:

```html
    <style>
        :root {
            --color-background: #f7f8fa;
            --color-surface: #ffffff;
            --color-surface-muted: #eef1f6;
            --color-text: #172033;
            --color-text-muted: #687087;
            --color-primary: #3258e8;
            --color-primary-dark: #2442b8;
            --color-border: #dde1eb;
            --shadow-card: 0 18px 50px rgba(23, 32, 51, 0.08);
            --radius-large: 24px;
            --radius-medium: 14px;
            --container-width: 1120px;
        }

        * {
            box-sizing: border-box;
        }

        html {
            color-scheme: light;
        }

        body {
            margin: 0;
            color: var(--color-text);
            background: var(--color-background);
            font-family:
                Inter, Pretendard, -apple-system, BlinkMacSystemFont,
                "Segoe UI", sans-serif;
            line-height: 1.65;
            word-break: keep-all;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        ul {
            margin: 0;
            padding: 0;
            list-style: none;
        }

        h1,
        h2,
        h3,
        p {
            margin-top: 0;
        }

        h1,
        h2,
        h3 {
            line-height: 1.2;
            letter-spacing: -0.035em;
        }

        h1 {
            max-width: 850px;
            margin-bottom: 28px;
            font-size: clamp(2.8rem, 7vw, 5.9rem);
        }

        h2 {
            margin-bottom: 28px;
            font-size: clamp(2rem, 4vw, 3.6rem);
        }

        h3 {
            margin-bottom: 14px;
            font-size: 1.55rem;
        }

        .container {
            width: min(calc(100% - 40px), var(--container-width));
            margin-inline: auto;
        }

        .site-header {
            position: sticky;
            top: 0;
            z-index: 10;
            border-bottom: 1px solid rgba(221, 225, 235, 0.8);
            background: rgba(247, 248, 250, 0.88);
            backdrop-filter: blur(16px);
        }

        .nav {
            display: flex;
            align-items: center;
            justify-content: space-between;
            min-height: 72px;
        }

        .brand {
            font-size: 1.15rem;
            font-weight: 800;
            letter-spacing: -0.04em;
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 28px;
            color: var(--color-text-muted);
            font-size: 0.94rem;
            font-weight: 600;
        }

        .hero {
            display: flex;
            min-height: min(820px, calc(100vh - 72px));
            flex-direction: column;
            justify-content: center;
            padding-block: 110px;
        }

        .eyebrow,
        .section-kicker,
        .project-type {
            color: var(--color-primary);
            font-size: 0.78rem;
            font-weight: 800;
            letter-spacing: 0.12em;
            text-transform: uppercase;
        }

        .eyebrow {
            margin-bottom: 24px;
        }

        .hero-description {
            max-width: 650px;
            margin-bottom: 36px;
            color: var(--color-text-muted);
            font-size: clamp(1.05rem, 2vw, 1.28rem);
        }

        .hero-actions {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .button {
            display: inline-flex;
            min-height: 50px;
            align-items: center;
            justify-content: center;
            padding: 0 22px;
            border: 1px solid transparent;
            border-radius: 999px;
            font-weight: 750;
        }

        .button-primary {
            color: #ffffff;
            background: var(--color-primary);
        }

        .button-secondary {
            border-color: var(--color-border);
            background: var(--color-surface);
        }

        .section {
            padding-block: 120px;
            scroll-margin-top: 72px;
        }

        .section-muted {
            background: var(--color-surface-muted);
        }

        .section-grid {
            display: grid;
            grid-template-columns: minmax(0, 0.9fr) minmax(0, 1.1fr);
            gap: clamp(50px, 10vw, 140px);
        }

        .section-kicker {
            margin-bottom: 18px;
        }

        .section-copy {
            color: var(--color-text-muted);
            font-size: 1.08rem;
        }

        .section-copy p + p {
            margin-top: 24px;
        }

        .skill-list {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .skill-list li {
            padding: 11px 17px;
            border: 1px solid var(--color-border);
            border-radius: 999px;
            background: var(--color-surface);
            font-weight: 700;
        }

        .section-heading {
            display: flex;
            align-items: end;
            justify-content: space-between;
            gap: 40px;
            margin-bottom: 42px;
        }

        .section-heading h2 {
            margin-bottom: 0;
        }

        .section-heading > p {
            max-width: 360px;
            margin-bottom: 6px;
            color: var(--color-text-muted);
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(2, minmax(0, 1fr));
            gap: 22px;
        }

        .project-card {
            display: flex;
            min-height: 430px;
            flex-direction: column;
            justify-content: space-between;
            padding: 34px;
            border: 1px solid var(--color-border);
            border-radius: var(--radius-large);
            background: var(--color-surface);
            box-shadow: var(--shadow-card);
        }

        .project-number {
            margin-bottom: 72px;
            color: var(--color-text-muted);
            font-size: 0.86rem;
            font-weight: 800;
        }

        .project-card > div:nth-child(2) {
            margin-bottom: auto;
        }

        .project-card > div:nth-child(2) > p:not(.project-type) {
            color: var(--color-text-muted);
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 26px;
        }

        .project-tags li {
            padding: 6px 10px;
            border-radius: 8px;
            color: var(--color-text-muted);
            background: var(--color-surface-muted);
            font-size: 0.8rem;
            font-weight: 700;
        }

        .project-link,
        .project-status {
            align-self: flex-start;
            margin-top: 32px;
            color: var(--color-primary);
            font-weight: 800;
        }

        .project-status {
            color: var(--color-text-muted);
        }

        .contact {
            color: #ffffff;
            background: var(--color-text);
        }

        .contact .section-kicker {
            color: #8aa1ff;
        }

        .contact h2 {
            margin-bottom: 16px;
        }

        .contact p:not(.section-kicker) {
            margin-bottom: 0;
            color: #b8c0d0;
        }

        .contact-inner {
            display: flex;
            align-items: end;
            justify-content: space-between;
            gap: 40px;
        }

        .site-footer {
            color: var(--color-text-muted);
            background: var(--color-text);
        }

        .footer-inner {
            display: flex;
            align-items: center;
            justify-content: space-between;
            min-height: 92px;
            border-top: 1px solid rgba(255, 255, 255, 0.12);
            font-size: 0.9rem;
        }

        .footer-inner p {
            margin-bottom: 0;
        }

        @media (max-width: 760px) {
            .container {
                width: min(calc(100% - 28px), var(--container-width));
            }

            .nav {
                min-height: 64px;
            }

            .nav-links {
                gap: 14px;
                font-size: 0.8rem;
            }

            .nav-links li:nth-child(2) {
                display: none;
            }

            .hero {
                min-height: auto;
                padding-block: 96px;
            }

            h1 {
                font-size: clamp(2.65rem, 14vw, 4.4rem);
            }

            .section {
                padding-block: 88px;
                scroll-margin-top: 64px;
            }

            .section-grid,
            .project-grid {
                grid-template-columns: 1fr;
            }

            .section-heading,
            .contact-inner {
                align-items: flex-start;
                flex-direction: column;
            }

            .project-card {
                min-height: 390px;
                padding: 26px;
            }

            .project-number {
                margin-bottom: 52px;
            }

            .contact-inner .button {
                width: 100%;
            }

            .footer-inner {
                min-height: 84px;
            }
        }

        @media (max-width: 420px) {
            .nav-links {
                gap: 10px;
            }

            .nav-links li:nth-child(1) {
                display: none;
            }
        }
    </style>
```

- [ ] **Step 3: Verify the style system covers required layout units**

Run:

```bash
rg -n -- '--color-background|--color-primary|\\.nav \\{|\\.hero \\{|\\.section-grid|\\.skill-list|\\.project-grid|\\.contact-inner|@media \\(max-width: 760px\\)' index.html
```

Expected: matches for both core color tokens, all seven layout units, and the mobile breakpoint.

- [ ] **Step 4: Preview desktop and mobile layouts**

Run:

```bash
python3 -m http.server 8000
```

Expected: the local server reports `Serving HTTP on ... port 8000`. Open `http://localhost:8000/`, inspect at widths around `1280px`, `760px`, and `375px`, and confirm there is no horizontal overflow or clipped text. Stop the server with `Ctrl+C` after inspection.

- [ ] **Step 5: Commit the responsive visual design**

Run:

```bash
git add index.html
git commit -m "style: add clean modern portfolio design"
```

Expected: one commit containing the embedded CSS changes in `index.html`.

---

### Task 3: Navigation and Accessibility Enhancements

**Files:**
- Modify: `index.html` inside `<body>` and the existing `<style>` block

**Interfaces:**
- Consumes: `#top`, `#about`, `#skills`, `#projects`, and `#contact` from Task 1, plus the visual rules from Task 2.
- Produces: Skip navigation to `#main-content`, smooth fragment navigation, keyboard focus feedback, hover feedback, and reduced-motion overrides.

- [ ] **Step 1: Verify the accessibility enhancements do not exist**

Run:

```bash
rg -n '본문 바로가기|id="main-content"|:focus-visible|prefers-reduced-motion|scroll-behavior' index.html
```

Expected: no matches and exit status `1`.

- [ ] **Step 2: Add the skip link and main landmark target**

Insert this link immediately after `<body>`:

```html
    <a class="skip-link" href="#main-content">본문 바로가기</a>
```

Change:

```html
<body>
```

to:

```html
<body id="top">
```

Change:

```html
    <main id="top">
```

to:

```html
    <main id="main-content" tabindex="-1">
```

- [ ] **Step 3: Add the interaction and accessibility styles**

Add these rules at the end of the existing `<style>` block, immediately before `</style>`:

```css
        html {
            scroll-behavior: smooth;
            scroll-padding-top: 72px;
        }

        .skip-link {
            position: fixed;
            top: 12px;
            left: 12px;
            z-index: 100;
            padding: 10px 14px;
            border-radius: 8px;
            color: #ffffff;
            background: var(--color-primary);
            transform: translateY(-150%);
        }

        .skip-link:focus {
            transform: translateY(0);
        }

        a:focus-visible {
            outline: 3px solid var(--color-primary);
            outline-offset: 4px;
            border-radius: 4px;
        }

        .button,
        .project-card,
        .project-link,
        .nav-links a {
            transition:
                color 180ms ease,
                background-color 180ms ease,
                border-color 180ms ease,
                box-shadow 180ms ease,
                transform 180ms ease;
        }

        @media (hover: hover) {
            .nav-links a:hover,
            .project-link:hover,
            .footer-inner a:hover {
                color: var(--color-primary);
            }

            .button-primary:hover {
                background: var(--color-primary-dark);
            }

            .button-secondary:hover {
                border-color: var(--color-primary);
                color: var(--color-primary);
            }

            .project-card:hover {
                box-shadow: 0 24px 60px rgba(23, 32, 51, 0.12);
                transform: translateY(-4px);
            }
        }

        @media (max-width: 760px) {
            html {
                scroll-padding-top: 64px;
            }
        }

        @media (prefers-reduced-motion: reduce) {
            html {
                scroll-behavior: auto;
            }

            *,
            *::before,
            *::after {
                scroll-behavior: auto !important;
                transition-duration: 0.01ms !important;
            }
        }
```

- [ ] **Step 4: Verify skip navigation, focus, link targets, and reduced motion**

Run:

```bash
python3 -c 'import re, pathlib; text=pathlib.Path("index.html").read_text(); ids=set(re.findall(r"id=\"([^\"]+)\"", text)); refs=set(re.findall(r"href=\"#([^\"]+)\"", text)); required=["top","main-content","about","skills","projects","contact"]; missing_ids=[x for x in required if x not in ids]; missing_refs=sorted(refs-ids); css=[":focus-visible","prefers-reduced-motion","scroll-behavior"]; missing_css=[x for x in css if x not in text]; skip_target_ok="<main id=\"main-content\" tabindex=\"-1\">" in text; failures=missing_ids+missing_refs+missing_css+([] if skip_target_ok else ["focusable main-content"]); print("accessibility checks: OK" if not failures else f"missing: {failures}"); raise SystemExit(bool(failures))'
```

Expected: `accessibility checks: OK`.

- [ ] **Step 5: Verify keyboard behavior in the browser**

Run:

```bash
python3 -m http.server 8000
```

Expected: at `http://localhost:8000/`, pressing `Tab` first reveals “본문 바로가기”; activating it moves focus to the main content; continued tabbing shows visible focus on navigation and action links. Stop the server with `Ctrl+C` after inspection.

- [ ] **Step 6: Commit navigation and accessibility behavior**

Run:

```bash
git add index.html
git commit -m "feat: improve portfolio navigation accessibility"
```

Expected: one commit containing only navigation, focus, hover, and reduced-motion changes.

---

### Task 4: Project Documentation and Final Verification

**Files:**
- Modify: `README.md:1-2`
- Verify: `index.html`

**Interfaces:**
- Consumes: The completed portfolio from Tasks 1–3.
- Produces: Reproducible local preview instructions, explicit customization locations, and GitHub Pages publishing steps.

- [ ] **Step 1: Verify the README does not document the portfolio workflow**

Run:

```bash
rg -n '로컬에서 확인하기|내용 수정하기|GitHub Pages 배포' README.md
```

Expected: no matches and exit status `1`.

- [ ] **Step 2: Replace the README with complete usage and publishing documentation**

Replace `README.md` with:

````markdown
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
````

- [ ] **Step 3: Run automated structural checks**

Run:

```bash
python3 -c 'from html.parser import HTMLParser; import pathlib; HTMLParser().feed(pathlib.Path("index.html").read_text()); print("HTML parse: OK")'
python3 -c 'import re, pathlib; text=pathlib.Path("index.html").read_text(); ids=set(re.findall(r"id=\"([^\"]+)\"", text)); refs=set(re.findall(r"href=\"#([^\"]+)\"", text)); missing=sorted(refs-ids); print("internal links: OK" if not missing else f"missing: {missing}"); raise SystemExit(bool(missing))'
rg -n 'lang="ko"|name="description"|:focus-visible|prefers-reduced-motion|@media \\(max-width: 760px\\)' index.html
git diff --check
```

Expected: both Python commands report `OK`, `rg` finds every required pattern, and `git diff --check` prints no output.

- [ ] **Step 4: Perform final visual verification**

Run:

```bash
python3 -m http.server 8000
```

Expected at `http://localhost:8000/`:

- At `1280px`, the about section has two columns and projects have two cards per row.
- At `760px` and `375px`, content becomes one column without horizontal overflow.
- Navigation links move to the correct sections.
- External GitHub links open the intended profile or repository.
- Keyboard focus remains visible.
- Reduced-motion emulation disables smooth scrolling and visible card movement.

Stop the server with `Ctrl+C` after inspection.

- [ ] **Step 5: Commit documentation and verification-ready state**

Run:

```bash
git add README.md
git commit -m "docs: add portfolio usage and deployment guide"
```

Expected: one commit containing only `README.md`.

- [ ] **Step 6: Confirm the final commit sequence and clean worktree**

Run:

```bash
git log -6 --oneline
git status --short
```

Expected: the six most recent commits are the design, implementation plan, semantic content, clean-modern styling, accessibility, and documentation commits; `git status --short` prints no output.
