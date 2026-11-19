# 쥬비랜드 (EN) main-section04 – 6-Stage Career Roadmap

공통 단계(STEP 01~03) → Choose your path → Settlement Track·Return Track(STEP 04~06 → 리더)으로 이어지는 경력 로드맵 섹션. 한국어판 `juviland/main-section04`와 같은 구조입니다. 모션 없이 시안 이미지 그대로의 레이아웃이 화면 크기에만 반응합니다.

- 피그마: main-section04(pc) `109:658` (1600×512) · main-section04(mob) `109:1252` (1080×1080)
- 배포 주소: https://kimain1404-design.github.io/juviland-en/main-section04/

## 파일 구성

```
main-section04/
├─ index.html                        (주소로 바로 열리도록 이름 유지)
├─ main-section04.css                반응형 레이아웃 (스크립트 없음)
├─ main-section04-liveklass.html     라이브클래스에 붙여 넣을 iframe 코드
├─ README.md
└─ assets/
   └─ main-section04-leaf.png        리더 상자·트랙 이름 옆 잎사귀 (section02와 같은 그림)
```

화살표·연결선은 이미지 없이 SVG·CSS로 그렸습니다.

## 반응형

| 구간 | 폭 | 동작 |
|---|---|---|
| main-section04(pc) | 1200px 이상 | 1600×512 시안 비율로 축소 (1600px 이상은 원본 크기). 공통 단계는 아래에서 위로 계단, 진로 선택은 세로 바, 두 트랙은 위·아래 |
| 태블릿 | 768 ~ 1199px | (mob) 배치. 글자·높이는 648px 화면 기준에서 고정, 콘텐츠는 화면 폭을 채움 |
| main-section04(mob) | 767px 이하 | 1080×1080 시안 비율 그대로. 공통 단계 가로, 진로 선택 가로 바, 두 트랙 좌·우 |

섹션 높이는 시안 프레임 높이로 고정입니다 (pc 512, mob 1080 → 화면 폭의 32% / 100%).

### 한국어판과 다른 점

- 영문 문구 줄바꿈은 시안대로 `<br>`로 고정 (PC 트랙 단계 이름·리더 2줄, "Choose your path" 3줄 / 모바일 STEP 02·03 설명 2줄).
- PC : 제목 ↔ 본문 간격 14, 트랙 카드 여백 10·24·16, 트랙 이름 18px, 리더 16px, "Choose your path" 16px.
- PC 왼쪽 흰 상자 높이는 두 트랙 높이를 따라가고, 계단 화살표는 상자 아래 기준으로 놓았습니다.
- 모바일 연결선 시작 위치 332.9 (공통 단계가 설명 2줄만큼 높음).

## 라이브클래스에 넣기

에디터 HTML(`<>`) 모드에 `main-section04-liveklass.html` 코드를 붙여 넣습니다. 높이 식이 계산하는 값:

- PC(1200px 이상): `32vw`, 1600px 이상은 `512px`
- 1199px 이하: `100vw`, 648px 이상은 `648px`
- 끝의 `+ 1px`은 바닥이 잘리지 않게 하는 여유분입니다.

섹션 높이가 시안 프레임 높이로 고정이라, 글꼴이 달라도 높이가 바뀌지 않습니다.

주소 끝의 `?v=날짜-번호`는 캐시 방지용입니다. 파일을 고친 뒤 예전 화면이 계속 보이면 `index.html`의 CSS 링크와 라이브클래스 코드의 `?v=` 값을 함께 바꿔 주세요.
