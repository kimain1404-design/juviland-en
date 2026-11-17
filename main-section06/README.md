# 쥬비랜드 (EN) main-section06 – The people behind the change

"OUR PEOPLE" 섹션. 대표 카드, 이력 4개, 함께하는 전문가가 스크롤에 맞춰 순서대로 나타납니다. 모션 코드(`main-section06.js`)는 한글판 `juviland/main-section06`과 같습니다.

- 피그마: en-main-section06(pc) `109:754` · en-main-section06(mob) `109:1353`
- 배포 주소: https://kimain1404-design.github.io/juviland-en/main-section06/

## 파일 구성

```
main-section06/
├─ index.html                             (주소로 바로 열리도록 이름 유지)
├─ main-section06.css                     반응형 레이아웃 + 모션
├─ main-section06.js                      순서대로 등장 (한글판과 동일)
├─ main-section06-liveklass.html          라이브클래스에 붙여 넣을 iframe 코드
├─ README.md
└─ assets/
   ├─ main-section06(pc)-founder.webp     대표 사진 (pc, 카드 전체에 깔림) – 한글판과 같은 사진
   └─ main-section06(mob)-founder.webp    대표 사진 (mob·태블릿, 카드 위쪽) – 한글판과 같은 사진
```

## 한글판과 다른 점

- 인용 문장: 줄 간격 1.4 → 1.2. PC는 2줄, 모바일은 3줄이라 문장을 `founder__quote pc-only` / `founder__quote mo-only` 두 개로 나눴습니다 (줄 단위 모션 때문). 모바일 글자 크기 58 → 48px.
- 간격: 머리말 ↔ 대표 카드는 그대로 (PC 60 / 모바일 80), 대표 카드 ↔ 함께하는 전문가는 영문 시안대로 PC 40 / 모바일 36 (`.founder + .experts`의 음수 margin).
- 줄바꿈 고정: 제목·소개·이력·전문가 문구의 줄바꿈 위치를 시안대로 `<br>`로 고정했습니다. PC와 모바일 위치가 다른 곳은 `<br class="pc-only">`, `<br class="mo-only">`로 나눴습니다.
  - 모바일·태블릿: 한글판처럼 `nowrap`이라 섹션 높이가 화면 폭에 따라 일정하게 변합니다.
  - PC: 시안 줄바꿈은 `<br>`로 맞추되 `nowrap`은 쓰지 않았습니다. 글꼴이 늦게 뜨거나 달라 한 줄이 넘칠 때 이력 카드(고정 높이) 안에서 잘리지 않고 한 줄 더 내려갑니다.
- 문구를 바꾸면 줄바꿈 위치와 라이브클래스 높이 식도 함께 수정해야 합니다.

## 글꼴 확인 필요

인용 문장의 원주체는 한글판처럼 `main-section01/fonts/Wonju-Bold.woff2`를 찾는데, 현재 `juviland`·`juviland-en` 저장소 모두에 이 파일이 없습니다. 없으면 Pretendard Bold로 표시되며, 영문은 원주체보다 폭이 넓어 시안과 모양이 달라집니다.

- `juviland-en/main-section01/fonts/Wonju-Bold.woff2`를 올리면 이 섹션도 함께 원주체로 바뀝니다.
- 파일이 없을 때 모바일 인용 문장이 화면 밖으로 잘리지 않도록, 넘치는 줄은 자동으로 줄바꿈되게 해 두었습니다 (이 경우 섹션 아래 여백이 그만큼 줄어듭니다).

## 반응형

| 구간 | 폭 | 동작 |
|---|---|---|
| en-main-section06(pc) | 1200px 이상 | 1600 시안 비율로 축소. 대표 카드 + 이력 2×2 + 전문가 2열 (1600px 이상은 원본 크기) |
| 태블릿 | 768 ~ 1199px | (mob) 배치. 글자 크기는 648px 화면 기준에서 고정, 콘텐츠는 화면 폭을 채움 (좌우 여백 = 화면 폭의 5.6%). 사진은 높이 460px까지 |
| en-main-section06(mob) | 767px 이하 | 1080 시안 비율 그대로 |

## 모션 (한글판과 동일)

1. 머리말: `OUR PEOPLE` → 제목 → 설명
2. 대표 카드: 카드가 올라오며 사진이 걷히듯 드러남 (pc 오른쪽→왼쪽, mob 위→아래) + 살짝 줌아웃 → 이름 → 인용 문장(줄 단위, 모바일 3줄) → 소개
3. 이력 카드 4개: 0.14초 간격으로 올라오고, 안의 항목이 한 줄씩
4. 함께하는 전문가: 박스가 올라오고 두 카드가 모여듦 (pc 좌우에서, mob 아래에서)

라이브클래스 iframe 안에서도 부모 페이지 스크롤에 맞춰 동작합니다. "동작 줄이기" 설정 사용자는 모션 없이 완성 화면이 보입니다.

## 라이브클래스에 넣기

에디터 HTML(`<>`) 모드에 `main-section06-liveklass.html` 코드를 붙여 넣습니다. 높이 식이 계산하는 값:

- PC(1200px 이상): `93.5875vw + 3.96px`, 1600px 이상은 `1501.47px`
- 1199px 이하: `457.692vw + 8.49px`, `51.2vw + 2642.82px`, `3102.8px` 중 가장 작은 값 (모바일 → 태블릿 사진 커짐 → 사진 상한)
- 끝의 `+ 1px`은 바닥이 잘리지 않게 하는 여유분입니다.

320~2560px 26가지 폭에서 시안 줄바꿈 기준으로 iframe 높이가 실제 섹션보다 0.7~1.4px 큰 것을 확인했습니다 (잘림 없음). 1600px 섹션 높이 1501px (인용 문장 크기 조정으로 피그마 프레임 1503px보다 4.8px 낮음).

## 대표 카드 – 글이 사진을 가리지 않게 (PC)

- 인용 문장은 따옴표 없이, 두 줄 길이를 비슷하게 나눔: "Education means discovering a person's potential / and walking with them all the way as they grow."
- 인용 문장 글자 크기 34 → 32 (시안 기준 px). 원주체 파일이 없어 Pretendard로 표시돼도 오른쪽 얼굴과 간격이 남습니다.
- 카드가 사진 원본 비율보다 높아 사진이 커지면서 인물이 왼쪽으로 밀려 나오므로, `object-position: calc(100% + 45 * var(--u)) 50%`로 사진을 오른쪽 흐린 배경 여백만큼 밀었습니다 (값을 키우면 오른쪽 잎사귀가 잘림).
