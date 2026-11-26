# Zuviland EN main-section01 – Global Farming Talent Career Pass

한국어판 `juviland/main-section01`의 영어 버전입니다. 레이아웃·모션·일러스트는 한국어판과 같고 문구와 버튼 링크만 다릅니다.

- 피그마: en-main-section01(pc) `109:461` · en-main-section01(mob) `109:1033`
- 배포 주소: https://kimain1404-design.github.io/juviland-en/main-section01/

## 파일 구성

```
main-section01/
├─ index.html                               (주소로 바로 열리도록 이름 유지)
├─ main-section01.css                       반응형 레이아웃 + 모션
├─ main-section01.js                        화면 진입 시 모션 + 제목 폭 맞춤
├─ main-section01-liveklass.html            라이브클래스에 붙여 넣을 iframe 코드
├─ README.md
├─ assets/
│  ├─ main-section01-bg.jpg                 수채화 배경 (pc·mob 공통)
│  ├─ main-section01-people.webp            가운데 인물, 위아래 모션 (pc·mob 공통)
│  ├─ main-section01(pc)-scene.webp         주변 일러스트, 고정 (pc 전용)
│  └─ main-section01(pc)-farm.webp          왼쪽 트랙터 언덕 (pc 전용)
└─ fonts/                                   원주체 파일을 넣는 위치 (Wonju-Bold.woff2)
```

## 버튼 링크 (새 탭)

| 버튼 | 주소 |
|---|---|
| Government Inquiries (기관 폼) | https://zuviland-en.liveklass.com/forms/RSUzZaSeN9XWVYJSatbT |
| Investment Partnership (투자 폼) | https://zuviland-en.liveklass.com/forms/mb87rtMVzQvM6uarZXrT |

## 제목 서체

시안의 제목은 원주체(Wonju TTF Bold)입니다. `fonts/Wonju-Bold.woff2`가 없으면 Pretendard로 표시되는데, 영어에서는 Pretendard가 더 넓어 휴대폰에서 "Global Farming Talent"가 넘칠 수 있습니다. 그래서 `main-section01.js`가 제목이 글자 영역보다 넓으면 그 줄이 딱 맞게 글자만 줄입니다(줄 높이는 그대로라 섹션 높이는 변하지 않음). 원주체 파일을 넣으면 시안 크기 그대로 들어가 이 처리는 동작하지 않습니다.

## 반응형 · 모션

한국어판과 같습니다.
- PC(1200px 이상): 1600 시안 비율로 통째로 축소. 1600px 이상은 원본 크기로 가운데 정렬.
- 태블릿(768~1199px): 글자 고정 크기, 일러스트는 버튼 아래로.
- 모바일(767px 이하): 1080 시안 비율, 인물 그룹만 표시.
- 모션: 배경 → 제목 2줄 → 설명 → 버튼 → 인물(아래에서 올라온 뒤 3초 주기로 위아래). 주변 일러스트는 고정.

## 라이브클래스에 넣기

에디터 HTML(`<>`) 모드에 `main-section01-liveklass.html` 코드를 붙여 넣습니다. 섹션 높이가 한국어판과 같아 높이 식도 한국어판과 같습니다.

- PC(1200px 이상): `46.35vw`, 1600px 이상은 `741.6px`
- 태블릿(768~1199px): `211.2px + 35.46vw`
- 모바일(767px 이하): `100.05vw`, 540px 이상은 `540.3px`
