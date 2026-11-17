# 쥬비랜드 (EN) main-section02 – WHY ZUVILAND?

"Why connect the whole journey?" 섹션. 한글판 `juviland/main-section02`와 같은 모션으로 지표 카드 3개와 마무리 문장이 스크롤에 맞춰 순서대로 나타납니다.

- 피그마: en-main-section02(pc) `109:483` · en-main-section02(mob) `109:1042`
- 배포 주소: https://kimain1404-design.github.io/juviland-en/main-section02/

## 파일 구성

```
main-section02/
├─ index.html                        (주소로 바로 열리도록 이름 유지)
├─ main-section02.css                반응형 레이아웃 + 모션
├─ main-section02.js                 순서대로 등장 + 숫자 카운트 (한글판과 동일)
├─ main-section02-liveklass.html     라이브클래스에 붙여 넣을 iframe 코드
├─ README.md
└─ assets/
   └─ main-section02-leaf.png        마무리 박스 잎사귀 (pc·mob 공통)
```

## 한글판과 다른 점

- 마무리 박스: 작은 영어 문장 줄이 없고, 큰 문장이 영어. PC 2줄 / 모바일 3줄로 줄마다 따로 올라옵니다 (한글판 큰 문장 모션과 같은 방식, 1.55s부터 0.12초 간격).
- 줄바꿈 고정: 영어는 화면 폭에 따라 줄 수가 바뀌기 쉬워서, 시안의 줄바꿈 위치에 `<br>`을 넣고 `white-space: nowrap`으로 고정했습니다. 그래서 태블릿처럼 폭이 넓어져도 줄 수가 같고 iframe 높이식과 맞습니다.
  - PC·모바일 줄바꿈이 다른 곳은 `<br class="pc-only">`, `<br class="mo-only">`로 나눴습니다.
- PC 두 번째 카드 "Everyone deserves a safe, respectful place to live": 시안에서는 한 줄이라 카드 밖으로 잘려서, PC에서 "Everyone deserves a safe, / respectful place to live" 2줄로 넣었습니다. 그래서 카드 높이가 시안(229px)보다 조금 큽니다.
- 숫자 뒤 단위 "명"이 없음 (117,113).

## 반응형

| 구간 | 폭 | 동작 |
|---|---|---|
| en-main-section02(pc) | 1200px 이상 | 1600 시안 비율로 축소, 카드 3열 (1600px 이상은 원본 크기) |
| 태블릿 | 768 ~ 1199px | (mob) 배치. 글자 크기는 648px 화면 기준에서 고정, 콘텐츠는 화면 폭을 채움 |
| en-main-section02(mob) | 767px 이하 | 1080 시안 비율 그대로 |

## 모션 (한글판과 동일)

1. 머리말: 태그 → 제목 → 설명
2. 지표 카드: 0.16초 간격으로 올라옴 → 숫자 카운트(117,113 / 85) · "Gaps in care"는 왼쪽→오른쪽으로 그려짐 → 출처 → 체크 아이콘 → 필요 문구. 모바일은 바깥 카드가 먼저 나온 뒤 세 줄이 차례로.
3. 마무리: 연결선이 내려옴 → 점 → 남색 박스가 점에서 펼쳐짐 → 잎사귀 → 큰 문장(줄 단위) → 마지막 문장 → 밑줄

## 라이브클래스에 넣기

에디터 HTML(`<>`) 모드에 `main-section02-liveklass.html` 코드를 붙여 넣습니다. 높이 식이 계산하는 값:

- PC(1200px 이상): `57.779vw + 4.95px`, 1600px 이상은 `929.41px`
- 1199px 이하: `267.95vw + 5.48px`, 648px 이상은 `1741.72px`
- 끝의 `+ 1px`은 바닥이 잘리지 않게 하는 여유분입니다.

320~2560px 25가지 폭에서 iframe 높이가 실제 섹션보다 1.0~1.4px 큰 것을 확인했습니다 (잘림 없음). 글자 크기나 여백, 문구 줄 수를 바꾸면 이 식도 수정해야 합니다.
