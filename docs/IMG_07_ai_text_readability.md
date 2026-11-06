# 07번 「AI가 써 준 글은 왜 잘 읽히지 않을까」 이미지 제작 명세서

| 항목 | 내용 |
|---|---|
| 페이지 | 07_ai_text_readability.html |
| 모드 / 주 앵커 | 논문 / C 장부 (회계실·금고) + D 보조 (전보 창구) |
| 시즌 | 기본 (cozy night laboratory) |
| 대결 | 무조건 짧게(주판봇) vs 맥락 따라(초파리) → 결과 **F**, 읽기 시간 12.72초 vs 14.30초 (차이 약 11%, 설명용 모형) |
| 새로 그릴 그림 | P1 2장 (cover_07, cut_07_think) · P2 4장 · P3 2장 (bg_07, og_07) |
| 공용 표정 | 18장 — 모두 캐릭터 저장소 fruitfly-lab-expressions 기본 팩(@24e395f)에 있음, 페이지에 넣음. 새로 그리지 않는다 |
| 그림이 없을 때 | 캐릭터 표정은 기본 팩 그림이 들어 있다. 배경은 CSS + 주판 그림으로 이미 완성 상태. 장면·컷 자리는 숨은 슬롯(.slot)이라 그림이 없으면 보이지 않는다 |
| 히어로 무대 (R2) | 따로 두지 않음 — 히어로는 배경 bg_07 + 캐릭터 대화창 4줄로 구성 |

## 1. 그림체와 고정 외형
- 스타일: SKILL 18-3 (16비트 RPG 픽셀아트, 굵은 외곽선, 2~3단계 명암)
- 캐릭터 고정 외형: SKILL 18-4 표 그대로. **로봇은 주판봇**(외국어판 AbaBot, 옛 Money-Robo): 베이지색 상자형 레트로 컴퓨터 로봇, 얼굴은 초록 화면. 성격은 그대로이고 소품만 금화 → 주판알로 바뀌었다. 외형 기준은 캐릭터 저장소 fruitfly-lab-expressions의 주판봇 그림이며, 스킬 18-4가 아직 Money-Robo 묘사라면 이 명세서의 묘사를 따른다
- 회사 로고의 하얀 로봇(주판봇)은 쓰지 않는다. 표정 키는 캐릭터 팩과 맞추려고 `robo_*`를 그대로 쓴다
- 이 페이지 장소: 연구실 옆 회계실(금화 탑, 가죽 장부, 원형 금고 문, 저울) + 오래된 전보 창구(글자마다 요금을 내던 곳)
- 장소 영어 묘사: *cozy accounting room beside the lab, large wooden abacuses with round beads, small piles of abacus beads, leather ledgers with blank striped pages, a round vault door, a brass scale* / *an old-fashioned telegram counter inside the same night lab world, a wooden counter with a brass bell, blank paper slips, purple lab light spilling in from one side*
- 생물 앵커가 아니므로 초파리 해부·현미경 소품을 넣지 않는다. 초파리는 의심하는 캐릭터로만 나온다.

## 2. 필요한 그림 전체

| # | 키 | 판 | 크기 | 상태 | 우선 | 들어가는 곳 | 대신 쓰는 그림 |
|---|---|---|---|---|---|---|---|
| 1 | `cover_07` | L | 1920×1080 | 완료·페이지에 넣음 191 KB | P1 | 글 표지 (내비 바로 아래, lab-cover 표시 블록) | 대체 표지: 그라데이션·벌집 무늬 + 네 캐릭터 기본 팩 그림 한 줄 (지금 페이지 상태) |
| 2 | `bg_07` | F | 1920×720 | 완료·별도 파일 62 KB | P3 | 히어로 배경 (header .hero-bg) — 표지가 있으므로 선택, 표지를 잘라 써도 됨 | CSS 그라데이션 + 벌집 무늬 + 픽셀 주판봇·주판 두 개 (지금 페이지 상태) |
| 3 | `cut_07_think` | G | 960×540 | 완료·페이지에 넣음 27 KB | P1 | 히어로 (논문 모드 생각 컷, R14) — 숨은 슬롯 | 없음 (슬롯 숨김, 대화창만 보임) |
| 4 | `cut_07_roundtrip` | G | 960×540 | 완료·페이지에 넣음 35 KB | P2 | 결과 2 위 — 숨은 슬롯 | 없음 (슬롯 숨김) |
| 5 | `cut_07_telegram` | G | 960×540 | 완료·페이지에 넣음 30 KB | P2 | 실험실 위 — 숨은 슬롯 | 없음 (슬롯 숨김, 전보 창구 캔버스가 대신함) |
| 6 | `sc_07_outro` | E | 1200×800 | 완료·페이지에 넣음 50 KB | P2 | 아웃트로 — 숨은 슬롯 | 없음 (슬롯 숨김, 말풍선 4개가 대신함) |
| 7 | `thumb_07` | I | 600×400 | 완료·별도 파일 59 KB | P2 | 시리즈 목차 카드 (이 HTML에는 없음) | 색 카드 |
| 8 | `og_07` | K | 1200×630 | 완료·별도 파일 97 KB | P3 | 공유 미리보기 (`og:image` 메타) | 없음 |
| 9 | `doc_front` | A | 192×192 | 공용·있음 | — | 해설 기본, 등장인물 카드 | 픽셀 지도 |
| 10 | `doc_think` | A | 192×192 | 공용·있음 | — | 히어로 대화창 첫마디 | doc_front |
| 11 | `doc_judge` | A | 192×192 | 공용·있음 | — | 대결 판정, 아웃트로 | doc_front |
| 12 | `doc_magic` | A | 192×192 | 공용·있음 | — | 박사의 한 줄 (한국어로 섹션) | doc_front |
| 13 | `asst_smile` | B | 180×220 | 공용·있음 | — | 히어로 대화창, 등장인물 카드 | 픽셀 지도 |
| 14 | `asst_firm` | B | 180×220 | 공용·있음 | — | 대결 결과 발표 전 | asst_smile |
| 15 | `asst_report` | B | 180×220 | 공용·있음 | — | 결과 1 말풍선 (숫자 출처 설명) | asst_smile |
| 16 | `asst_spark` | B | 180×220 | 공용·있음 | — | 대결 결과 후 (초파리 승), 아웃트로 | asst_smile |
| 17 | `asst_proud` | B | 180×220 | 공용·있음 | — | 꾸러미 섹션 | asst_smile |
| 18 | `fly_clip` | C | 220×220 | 공용·있음 | — | 등장인물 카드 | 픽셀 지도 |
| 19 | `fly_point` | C | 220×220 | 공용·있음 | — | 히어로, 1 질문, 대결 전 | fly_clip |
| 20 | `fly_magnify` | C | 220×220 | 공용·있음 | — | 결과 2 말풍선 (번역기 의심) | fly_clip |
| 21 | `fly_arms` | C | 220×220 | 공용·있음 | — | 대결 결과 후 (초파리 승), 아웃트로 | fly_clip |
| 22 | `robo_smile` | D | 180×200 | 공용·있음 | — | 등장인물 카드 | 픽셀 지도 |
| 23 | `robo_coin` | D | 180×200 | 공용·있음 | — | 히어로, 대결 전 | robo_smile |
| 24 | `robo_wow` | D | 180×200 | 공용·있음 | — | 결과 3 말풍선 | robo_smile |
| 25 | `robo_calc` | D | 180×200 | 공용·있음 | — | 실험실 말풍선 | robo_smile |
| 26 | `robo_sigh` | D | 180×200 | 공용·있음 | — | 대결 결과 후 (패배), 아웃트로 | robo_smile |
| — | 행동으로 보기 (짝 거리, 전보 창구, 왕복 번역 SVG, 계단 도식, 지식 그래프) | — | — | 코드 | — | 캔버스·SVG | — |

## 3. 새로 그릴 그림 상세

### 3-1. `cover_07` — 글 표지

| 항목 | 내용 |
|---|---|
| 판 · 크기 | L · 1920×1080 (정수배 가능) |
| 배경 | 그림 전체 |
| 구도 | 별도 지시문 COVER_07_ai_text_readability.md 참조 — 회계실 가운데 놋쇠 압착기, 긴 빈 종이 띠가 작고 빽빽한 상자로 눌려 나옴. 박사 가운데 뒤, 조수 한쪽 옆, 초파리 왼쪽(오른쪽을 봄), 주판봇 오른쪽(왼쪽을 봄). |
| 표정·몸짓 | doc_think · asst_smile · fly_magnify · robo_calc 느낌 (결과 암시 없음) |
| 소품 | 놋쇠 압착기, 빈 종이 띠, 빽빽한 빈 칸 상자와 빛줄기, 나무 주판 (글자 없음) |
| 빛·분위기 | 빛이 빽빽한 상자와 빛줄기에 모임 |
| 피할 것 | 글자·숫자, 금화, 회사 로고 로봇, 현미경 |
| 대체 글 (alt) | 밤의 연구실 옆 회계실에서 박사·조수·초파리 연구원·주판봇이 길게 풀린 종이 띠가 작은 상자로 꽉 눌려 나오는 압착기를 둘러싸고 들여다보는 표지 |
| 대신 쓰는 그림 | 대체 표지: 그라데이션·벌집 무늬 + 네 캐릭터 기본 팩 그림 한 줄 (지금 페이지 상태) |

**프롬프트:** 별도 파일 `COVER_07_ai_text_readability.md`의 'Genspark에 붙여 넣기' 블록을 쓴다.

### 3-2. `bg_07` — 히어로 배경

| 항목 | 내용 |
|---|---|
| 판 · 크기 | F · 1920×720 (정수배 가능) |
| 배경 | 그림 전체 |
| 구도 | 왼쪽 45%는 어둡고 단순하게(제목 자리). 오른쪽에 원형 금고 문, 커다란 나무 주판 두세 개, 쌓인 주판알, 저울. 오른쪽 끝에 전보 창구 카운터가 살짝 보인다. 인물 없음. |
| 표정·몸짓 | 없음 |
| 소품 | 나무 주판, 쌓인 주판알, 가죽 장부(빈 줄무늬), 원형 금고 문, 놋쇠 저울, 빈 쪽지가 꽂힌 전보 창구 (글자 없음) |
| 빛·분위기 | 금빛 램프가 금고 쪽에 모이고, 연구실 보라 빛이 왼쪽에서 들어온다 |
| 피할 것 | 글자·숫자가 보이는 장부나 쪽지, 금화·지폐 등 화폐, 은행 로고 |
| 대체 글 (alt) | 커다란 주판과 금고 문이 있는 연구실 옆 회계실, 한쪽에 오래된 전보 창구 |
| 대신 쓰는 그림 | CSS 그라데이션 + 벌집 무늬 + 픽셀 주판봇·주판 두 개 (지금 페이지 상태) |

**프롬프트 (복사해서 사용)**
```
16-bit RPG style pixel art, bold dark outline, 2–3 tone shading, small highlights, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, wide 8:3 background, left side simple and calm for title text, details on the right, cozy accounting room beside the lab, large wooden abacuses with round beads, small piles of abacus beads, leather ledgers with blank striped pages, a round vault door, a brass scale, at the far right edge an old telegram counter with blank paper slips, no characters, warm gold lamp light focused on the vault door, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-3. `cut_07_think` — 히어로

| 항목 | 내용 |
|---|---|
| 판 · 크기 | G · 960×540 (정수배 가능) |
| 배경 | 그림 전체 |
| 구도 | 박사가 왼쪽 아래에서 위를 올려다본다. 화면 오른쪽 위 생각 구름 안에 꽉 눌려 터질 듯한 상자(글자 대신 작은 빈 칸들이 빽빽이 찬 상자)와 물음표 기호. |
| 표정·몸짓 | doc_think 문구 (눈썹 올림, 턱에 손) |
| 소품 | 생각 구름(원 6개 겹침), 빽빽한 빈 칸 상자, 큰 물음표 기호 (글자 없음) |
| 빛·분위기 | 생각 구름 안쪽이 연한 분홍 형광으로 빛남 |
| 피할 것 | 생각 구름 안 글자, 실제 AI 제품 화면 |
| 대체 글 (alt) | 박사가 꽉 눌려 터질 듯한 글자 상자가 든 생각 구름을 올려다보는 장면 |
| 대신 쓰는 그림 | 없음 (슬롯 숨김, 대화창만 보임) |

**프롬프트 (복사해서 사용)**
```
16-bit RPG style pixel art, bold dark outline, 2–3 tone shading, small highlights, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, 16:9 illustration panel, chibi scientist, thin teal rectangular glasses, spiky black hair with one white streak, small ponytail at the back, white lab coat over black vest and tie standing at the lower left looking up with a hand on his chin, a large thought cloud at the upper right containing an overstuffed box crammed with tiny blank tiles and a big question mark symbol, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-4. `cut_07_roundtrip` — 결과 2 위

| 항목 | 내용 |
|---|---|
| 판 · 크기 | G · 960×540 (정수배 가능) |
| 배경 | 그림 전체 |
| 구도 | 조수가 가운데에서 시험관 하나를 들고 있다. 왼쪽 장비(빨간 표시등)와 오른쪽 장비(초록 표시등)가 화살표 고리로 이어져, 같은 시료가 한 바퀴 돌아오는 모습. 초파리가 오른쪽 아래에서 돋보기로 본다. |
| 표정·몸짓 | asst_firm, fly_magnify 문구 |
| 소품 | 시험관, 두 대의 측정 장비(빈 화면), 고리 모양 화살표 (글자 없음) |
| 빛·분위기 | 두 장비 화면의 빨강·초록 불빛 |
| 피할 것 | 장비 화면 글자, 실제 번역 앱 아이콘 |
| 대체 글 (alt) | 조수가 같은 시료를 두 장비에 차례로 넣어 비교하는 연구실 장면 |
| 대신 쓰는 그림 | 없음 (슬롯 숨김) |

**프롬프트 (복사해서 사용)**
```
16-bit RPG style pixel art, bold dark outline, 2–3 tone shading, small highlights, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, 16:9 illustration panel, girl researcher, long pink hair with two round buns and a navy streak, blue eyes, white lab coat over lavender hoodie, jeans in the center holding up one test tube between two lab machines with blank glowing screens, red light on the left machine and green light on the right, a looping arrow connecting them so the sample goes around and returns, anthropomorphic fruit fly researcher, black body, big red compound eyes, blue helmet with a gold stripe and pink and blue cables, white lab coat over a black vest, black gloves, transparent wings at the lower right peering through a magnifying glass, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-5. `cut_07_telegram` — 실험실 위

| 항목 | 내용 |
|---|---|
| 판 · 크기 | G · 960×540 (정수배 가능) |
| 배경 | 그림 전체 |
| 구도 | 주판봇이 전보 창구 안쪽에서 아주 짧은 쪽지를 내민다. 카운터 위에 작은 나무 주판 하나. 창구 밖에서 초파리가 쪽지를 받아 들고 고개를 갸웃한다. |
| 표정·몸짓 | robo_coin, fly_point 문구 (결과 전이므로 승패 암시 없음) |
| 소품 | 전보 창구, 놋쇠 종, 짧은 빈 쪽지, 작은 나무 주판 (글자 없음) |
| 빛·분위기 | 창구 램프의 금빛, 뒤쪽 연구실 보라 빛 |
| 피할 것 | 쪽지 위 글자, 승패를 암시하는 표정 |
| 대체 글 (alt) | 주판봇이 전보 창구에서 주판알을 튕기며 짧은 쪽지를 내미는 장면 |
| 대신 쓰는 그림 | 없음 (슬롯 숨김, 전보 창구 캔버스가 대신함) |

**프롬프트 (복사해서 사용)**
```
16-bit RPG style pixel art, bold dark outline, 2–3 tone shading, small highlights, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, 16:9 illustration panel, an old-fashioned telegram counter inside the same night lab world, a wooden counter with a brass bell, blank paper slips, purple lab light spilling in from one side, boxy beige retro CRT-monitor robot, dark green screen face with mint pixel eyes and mouth, short antenna topped with a red-brown abacus bead, gray segmented arms, two small tank treads, holding a wooden abacus behind the counter on the right facing left, handing over a very short blank paper slip, a small wooden abacus on the counter, anthropomorphic fruit fly researcher, black body, big red compound eyes, blue helmet with a gold stripe and pink and blue cables, white lab coat over a black vest, black gloves, transparent wings on the left facing right holding the slip with head tilted in curiosity, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-6. `sc_07_outro` — 아웃트로

| 항목 | 내용 |
|---|---|
| 판 · 크기 | E · 1200×800 (정수배 가능) |
| 배경 | 그림 전체 |
| 구도 | 결과 F(초파리 승): 초파리가 앞쪽 왼쪽에 크게, 길게 풀어 쓴 쪽지를 펼쳐 들고 팔짱. 주판봇은 오른쪽 뒤에서 장부를 덮으며 고개를 끄덕인다(조롱 없음). 박사는 가운데 뒤에서 옆을 가리키고, 조수는 한쪽에서 점수판을 든다. |
| 표정·몸짓 | fly_arms, robo_sigh, doc_judge, asst_spark 문구 |
| 소품 | 길게 펼친 빈 쪽지, 덮인 장부, 칸 셋짜리 빈 점수판 (글자 없음) |
| 빛·분위기 | 밤의 연구실 보라 빛, 쪽지에 초록 형광이 살짝 |
| 피할 것 | 패자 조롱, 점수판 숫자, 글자 |
| 대체 글 (alt) | 초파리 연구원이 펼친 쪽지를 들고 앞에 서 있고, 주판봇이 장부를 덮으며 뒤에서 인정하는 연구실 장면 |
| 대신 쓰는 그림 | 없음 (슬롯 숨김, 말풍선 4개가 대신함) |

**프롬프트 (복사해서 사용)**
```
16-bit RPG style pixel art, bold dark outline, 2–3 tone shading, small highlights, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, 3:2 landscape scene, medium brightness, night laboratory scene, anthropomorphic fruit fly researcher, black body, big red compound eyes, blue helmet with a gold stripe and pink and blue cables, white lab coat over a black vest, black gloves, transparent wings large in the front left with arms crossed holding up a long unrolled blank paper slip, boxy beige retro CRT-monitor robot, dark green screen face with mint pixel eyes and mouth, short antenna topped with a red-brown abacus bead, gray segmented arms, two small tank treads, holding a wooden abacus at the back right closing a ledger and nodding gracefully, chibi scientist, thin teal rectangular glasses, spiky black hair with one white streak, small ponytail at the back, white lab coat over black vest and tie at the back center pointing to the side, girl researcher, long pink hair with two round buns and a navy streak, blue eyes, white lab coat over lavender hoodie, jeans at one side holding a scoreboard with three blank panels, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-7. `thumb_07` — 시리즈 목차 카드

| 항목 | 내용 |
|---|---|
| 판 · 크기 | I · 600×400 (정수배 가능) |
| 배경 | 그림 전체 |
| 구도 | cover_07을 3:2로 잘라 쓴다 (없으면 bg_07의 오른쪽). |
| 표정·몸짓 | 없음 |
| 소품 | bg_07과 같음 (글자 없음) |
| 빛·분위기 | bg_07과 같음 |
| 피할 것 | 글자 |
| 대체 글 (alt) | 금고 문과 주판이 보이는 회계실 |
| 대신 쓰는 그림 | 색 카드 |

**처리:** 새로 그리지 않고 cover_07을 600×400(3:2)으로 잘라 쓴다.

### 3-8. `og_07` — 공유 미리보기

| 항목 | 내용 |
|---|---|
| 판 · 크기 | K · 1200×630 (정수배 가능) |
| 배경 | 그림 전체 |
| 구도 | bg_07 위에 주판봇(오른쪽, 왼쪽을 봄)와 초파리(왼쪽, 오른쪽을 봄)가 짧은 쪽지 하나를 사이에 두고 마주 본다. |
| 표정·몸짓 | robo_coin, fly_point 문구 |
| 소품 | 빈 쪽지 한 장, 주판알 하나 (글자 없음) |
| 빛·분위기 | bg_07과 같음 |
| 피할 것 | 글자, 승패 암시 |
| 대체 글 (alt) | 주판봇과 초파리 연구원이 짧은 쪽지를 사이에 두고 마주 보는 장면 |
| 대신 쓰는 그림 | 없음 |

**프롬프트 (복사해서 사용)**
```
16-bit RPG style pixel art, bold dark outline, 2–3 tone shading, small highlights, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, 1200x630 social preview image, main subject centered, cozy accounting room beside the lab, large wooden abacuses with round beads, small piles of abacus beads, leather ledgers with blank striped pages, a round vault door, a brass scale, anthropomorphic fruit fly researcher, black body, big red compound eyes, blue helmet with a gold stripe and pink and blue cables, white lab coat over a black vest, black gloves, transparent wings on the left facing right pointing, boxy beige retro CRT-monitor robot, dark green screen face with mint pixel eyes and mouth, short antenna topped with a red-brown abacus bead, gray segmented arms, two small tank treads, holding a wooden abacus on the right facing left holding up a large abacus bead, a single short blank paper slip floating between them, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

## 4. 일관성 지침
- 참고 이미지: 기존 캐릭터 그림(또는 표정 모음 한 장)을 함께 넣는다. 없으면 IMG_00의 첫 그림이 이후의 기준이 된다.
- 같은 캐릭터는 같은 세션에서 연달아 만들고, 시드를 고를 수 있으면 고정: 박사 {seed}, 조수 {seed}, 초파리 {seed}, 로봇 {seed}
- 표정만 바꿀 때 덧붙일 문장: *same character, same size and position, only change the facial expression and pose to ...*
- 투명 배경이 안 되면: *solid flat #00ff00 background* 로 받아 지운다.
- 장면 안 크기: 박사 키 = 조수 키 ≈ 초파리 키 × 1.3, 로봇은 초파리와 비슷한 높이로 떠 있음.
- 대결 구도: 초파리는 왼쪽에서 오른쪽을, 주판봇은 오른쪽에서 왼쪽을 본다.

## 5. 넘겨받은 뒤 처리
1. 크기·투명 배경 확인, 단색 배경 제거
2. 빌드 크기로 줄이고 WebP 압축 (A~D 높이 180 또는 128, E 너비 760, F 너비 1280, G 너비 640)
3. 64×64로 줄여 픽셀 지도 표정과 나란히 비교
4. 표정은 이미 기본 팩에서 넣었다(`SPRITE` 96px, `SPRITE2` 192px). 새 표정 그림이 나오면 `build_character_pack.py --pick`으로 다시 뽑아 바꾼다
5. 장면·컷은 해당 `.slot`에 `<img>`를 넣고 `display:block`으로 바꾼다. alt는 위 표의 대체 글
6. 그림 합계 400 KB 이하 확인 (넘으면 P3 → P2 순으로 뺀다)

## 6. 체크리스트 (SKILL 18-13)
- [x] HTML의 모든 `data-img` 키가 명세서에 있고, 명세서의 키는 HTML(또는 og 메타·목차)에 쓰임
- [x] 대결 결과 후 표정이 5-8절 표와 일치 (F → doc_judge, asst_spark, fly_arms, robo_sigh)
- [x] 결과 전 그림(cut_07_telegram, og_07)에 승패 암시 없음
- [x] 판별 크기·바라보는 쪽·투명 배경이 18-2 표와 일치
- [x] 모든 프롬프트에 고정 외형 영어 묘사와 금지 구절
- [x] 장소가 주 앵커와 일치, 초파리 해부·현미경 소품 없음
- [x] 그림 안 글자 없음, 실존 브랜드 없음, 회사 로고 로봇(Money-Robo)·금화 없음
- [x] 장면·배경·컷마다 대체 글
- [x] 새로 그릴 P1 2장 (표지 제외 1장, 6장 이하) · 공용 표정 18장은 기본 팩 그림을 넣음
- [ ] 그림 합계 400 KB 이하 — 그림을 넣은 뒤 확인

## 6-1. 받은 그림 반영 기록 (2026-11-05)
- 받은 그림 8장 모두 반영. 표지·컷·장면 5장은 페이지 안에 WebP base64로 넣었고(합계 약 335 KB, 캐릭터 표정 포함 약 550 KB — 표지 포함 600 KB 기준 안), bg_07·og_07·thumb_07은 별도 파일로 둔다
- cover_07: 원본 생성 크기 1360×768을 1920×1080으로 키운 판을 받음 → 1600×900 WebP 192 KB. 화면에서 픽셀 그림이라 흐림은 눈에 띄지 않음. 다음 표지는 처음부터 1920 이상으로 생성 권장
- cover_07: 왼쪽 아래에 초파리가 있어 이름 칩을 오른쪽 아래로 옮김 (규칙 18-14-2의 왼쪽 아래 빈 자리와 다름)
- bg_07: 표지가 있어 히어로에는 넣지 않음(P3). 히어로는 주판봇 그림 + 주판 캔버스 유지
- og_07: 페이지와 같은 폴더에 og_07.jpg로 올려야 공유 미리보기가 뜬다
- 390·768·1280 폭에서 표지 얼굴 잘림 없음, 콘솔 오류 0, 가로 넘침 0

## 7. 매니페스트
```json
{
  "page": "07_ai_text_readability",
  "robot": {
    "ko": "주판봇",
    "foreign": "AbaBot",
    "replaces": "Money-Robo"
  },
  "anchor": "C:accounting-room+D:telegram-counter",
  "season": "default",
  "duel": {
    "result": "F",
    "gap": 0.11,
    "note": "읽기 시간 상대 차이, 설명용 모형"
  },
  "images": [
    {
      "key": "cover_07",
      "plate": "L",
      "size": [
        1920,
        1080
      ],
      "status": "done",
      "received": "2026-11-05",
      "webp_kb": 191,
      "inline": true,
      "priority": "P1",
      "slot": "글 표지 (내비 바로 아래, lab-cover 표시 블록)",
      "fallback": "대체 표지: 그라데이션·벌집 무늬 + 네 캐릭터 기본 팩 그림 한 줄 (지금 페이지 상태)",
      "alt": "밤의 연구실 옆 회계실에서 박사·조수·초파리 연구원·주판봇이 길게 풀린 종이 띠가 작은 상자로 꽉 눌려 나오는 압착기를 둘러싸고 들여다보는 표지"
    },
    {
      "key": "bg_07",
      "plate": "F",
      "size": [
        1920,
        720
      ],
      "status": "done",
      "received": "2026-11-05",
      "webp_kb": 62,
      "inline": false,
      "priority": "P3",
      "slot": "히어로 배경 (header .hero-bg) — 표지가 있으므로 선택, 표지를 잘라 써도 됨",
      "fallback": "CSS 그라데이션 + 벌집 무늬 + 픽셀 주판봇·주판 두 개 (지금 페이지 상태)",
      "alt": "커다란 주판과 금고 문이 있는 연구실 옆 회계실, 한쪽에 오래된 전보 창구"
    },
    {
      "key": "cut_07_think",
      "plate": "G",
      "size": [
        960,
        540
      ],
      "status": "done",
      "received": "2026-11-05",
      "webp_kb": 27,
      "inline": true,
      "priority": "P1",
      "slot": "히어로 (논문 모드 생각 컷, R14) — 숨은 슬롯",
      "fallback": "없음 (슬롯 숨김, 대화창만 보임)",
      "alt": "박사가 꽉 눌려 터질 듯한 글자 상자가 든 생각 구름을 올려다보는 장면"
    },
    {
      "key": "cut_07_roundtrip",
      "plate": "G",
      "size": [
        960,
        540
      ],
      "status": "done",
      "received": "2026-11-05",
      "webp_kb": 35,
      "inline": true,
      "priority": "P2",
      "slot": "결과 2 위 — 숨은 슬롯",
      "fallback": "없음 (슬롯 숨김)",
      "alt": "조수가 같은 시료를 두 장비에 차례로 넣어 비교하는 연구실 장면"
    },
    {
      "key": "cut_07_telegram",
      "plate": "G",
      "size": [
        960,
        540
      ],
      "status": "done",
      "received": "2026-11-05",
      "webp_kb": 30,
      "inline": true,
      "priority": "P2",
      "slot": "실험실 위 — 숨은 슬롯",
      "fallback": "없음 (슬롯 숨김, 전보 창구 캔버스가 대신함)",
      "alt": "주판봇이 전보 창구에서 주판알을 튕기며 짧은 쪽지를 내미는 장면"
    },
    {
      "key": "sc_07_outro",
      "plate": "E",
      "size": [
        1200,
        800
      ],
      "status": "done",
      "received": "2026-11-05",
      "webp_kb": 50,
      "inline": true,
      "priority": "P2",
      "slot": "아웃트로 — 숨은 슬롯",
      "fallback": "없음 (슬롯 숨김, 말풍선 4개가 대신함)",
      "alt": "초파리 연구원이 펼친 쪽지를 들고 앞에 서 있고, 주판봇이 장부를 덮으며 뒤에서 인정하는 연구실 장면"
    },
    {
      "key": "thumb_07",
      "plate": "I",
      "size": [
        600,
        400
      ],
      "status": "done",
      "received": "2026-11-05",
      "webp_kb": 59,
      "inline": false,
      "priority": "P2",
      "slot": "시리즈 목차 카드 (이 HTML에는 없음)",
      "fallback": "색 카드",
      "alt": "금고 문과 주판이 보이는 회계실"
    },
    {
      "key": "og_07",
      "plate": "K",
      "size": [
        1200,
        630
      ],
      "status": "done",
      "received": "2026-11-05",
      "webp_kb": 97,
      "inline": false,
      "priority": "P3",
      "slot": "공유 미리보기 (`og:image` 메타)",
      "fallback": "없음",
      "alt": "주판봇과 초파리 연구원이 짧은 쪽지를 사이에 두고 마주 보는 장면"
    },
    {
      "key": "doc_front",
      "plate": "A",
      "size": [
        192,
        192
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "해설 기본, 등장인물 카드",
      "fallback": "pixel-map",
      "alt": ""
    },
    {
      "key": "doc_think",
      "plate": "A",
      "size": [
        192,
        192
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "히어로 대화창 첫마디",
      "fallback": "doc_front",
      "alt": ""
    },
    {
      "key": "doc_judge",
      "plate": "A",
      "size": [
        192,
        192
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "대결 판정, 아웃트로",
      "fallback": "doc_front",
      "alt": ""
    },
    {
      "key": "doc_magic",
      "plate": "A",
      "size": [
        192,
        192
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "박사의 한 줄 (한국어로 섹션)",
      "fallback": "doc_front",
      "alt": ""
    },
    {
      "key": "asst_smile",
      "plate": "B",
      "size": [
        180,
        220
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "히어로 대화창, 등장인물 카드",
      "fallback": "pixel-map",
      "alt": ""
    },
    {
      "key": "asst_firm",
      "plate": "B",
      "size": [
        180,
        220
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "대결 결과 발표 전",
      "fallback": "asst_smile",
      "alt": ""
    },
    {
      "key": "asst_report",
      "plate": "B",
      "size": [
        180,
        220
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "결과 1 말풍선 (숫자 출처 설명)",
      "fallback": "asst_smile",
      "alt": ""
    },
    {
      "key": "asst_spark",
      "plate": "B",
      "size": [
        180,
        220
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "대결 결과 후 (초파리 승), 아웃트로",
      "fallback": "asst_smile",
      "alt": ""
    },
    {
      "key": "asst_proud",
      "plate": "B",
      "size": [
        180,
        220
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "꾸러미 섹션",
      "fallback": "asst_smile",
      "alt": ""
    },
    {
      "key": "fly_clip",
      "plate": "C",
      "size": [
        220,
        220
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "등장인물 카드",
      "fallback": "pixel-map",
      "alt": ""
    },
    {
      "key": "fly_point",
      "plate": "C",
      "size": [
        220,
        220
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "히어로, 1 질문, 대결 전",
      "fallback": "fly_clip",
      "alt": ""
    },
    {
      "key": "fly_magnify",
      "plate": "C",
      "size": [
        220,
        220
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "결과 2 말풍선 (번역기 의심)",
      "fallback": "fly_clip",
      "alt": ""
    },
    {
      "key": "fly_arms",
      "plate": "C",
      "size": [
        220,
        220
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "대결 결과 후 (초파리 승), 아웃트로",
      "fallback": "fly_clip",
      "alt": ""
    },
    {
      "key": "robo_smile",
      "plate": "D",
      "size": [
        180,
        200
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "등장인물 카드",
      "fallback": "pixel-map",
      "alt": ""
    },
    {
      "key": "robo_coin",
      "plate": "D",
      "size": [
        180,
        200
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "히어로, 대결 전",
      "fallback": "robo_smile",
      "alt": ""
    },
    {
      "key": "robo_wow",
      "plate": "D",
      "size": [
        180,
        200
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "결과 3 말풍선",
      "fallback": "robo_smile",
      "alt": ""
    },
    {
      "key": "robo_calc",
      "plate": "D",
      "size": [
        180,
        200
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "실험실 말풍선",
      "fallback": "robo_smile",
      "alt": ""
    },
    {
      "key": "robo_sigh",
      "plate": "D",
      "size": [
        180,
        200
      ],
      "status": "shared-have",
      "priority": "-",
      "slot": "대결 결과 후 (패배), 아웃트로",
      "fallback": "robo_smile",
      "alt": ""
    }
  ]
}
```
