**[한국어](#ko) · [English](#en) · [中文](#zh) · [日本語](#ja) · [Oʻzbekcha](#uz) · [Русский](#ru) · [Tiếng Việt](#vi)**

---

<a id="ko"></a>

# AI가 써 준 글은 왜 잘 읽히지 않을까 — 글자 벌금이 만든 말투

AI 연구실 해설 대시보드 제 07 편 · 논문 리뷰 **안상선** · 원 논문 Clark, Martin & Mahowald (2026)

최신 AI 모델 14종이 쓴 대화·코딩 답변·에세이를 모아, 사람이 읽기 힘들다고 알려진 표현이 얼마나 많은지 잰 논문을 한국어 독자에게 맞게 다시 풀었습니다. 박사 · 조수(하루) · 초파리 연구원 · 주판봇이 진행하는 단일 HTML 인터랙티브 해설입니다.

- 공개 주소: https://adminmrobo.github.io/ai_text_read_ability/
- 목차: [index.html](index.html) · 해설 바로 열기: [07_ai_text_readability.html](07_ai_text_readability.html)

![표지](cover_07.webp)

## 언어

이 시리즈는 한국어 원본과 외국어판 6개로 볼 수 있다.

- 고르는 방법: 화면 최상단 메뉴의 🌐 언어 선택 상자나 오른쪽 아래 🌐 배너에서 고른다. 고른 언어는 브라우저에 기억된다.
- 자동 전환: 한국어 페이지에 처음 들어오면, 브라우저 언어가 지원 언어일 때 그 언어판으로 옮겨 간다. 번역판 주소로 들어오면 그대로 연다.
- 주소 끝에 `?lang=en`처럼 붙이면 그 언어로 바로 연다.
- 언어판 파일은 `이름.언어코드.html` 꼴이다.

<!-- i18n:langtable -->
| 언어 | 파일 이름 | 바로 보기 |
|---|---|---|
| 한국어 | `index.html` | [바로 보기](https://adminmrobo.github.io/ai_text_read_ability/index.html) |
| English | `index.en.html` | [바로 보기](https://adminmrobo.github.io/ai_text_read_ability/index.en.html) |
| 中文 | `index.zh.html` | [바로 보기](https://adminmrobo.github.io/ai_text_read_ability/index.zh.html) |
| 日本語 | `index.ja.html` | [바로 보기](https://adminmrobo.github.io/ai_text_read_ability/index.ja.html) |
| Oʻzbekcha | `index.uz.html` | [바로 보기](https://adminmrobo.github.io/ai_text_read_ability/index.uz.html) |
| Русский | `index.ru.html` | [바로 보기](https://adminmrobo.github.io/ai_text_read_ability/index.ru.html) |
| Tiếng Việt | `index.vi.html` | [바로 보기](https://adminmrobo.github.io/ai_text_read_ability/index.vi.html) |
<!-- /i18n:langtable -->

## 한 편에 들어 있는 것

1. **질문** — 문법은 맞는데 왜 두 번 읽게 될까?
2. **방법** — 글 모으기, 문장 해부, 사람 글 기준선, 왕복 번역, 모델끼리 비교, 글자 벌금 실험
3. **여섯 습관** — that 빠진 관계절, 명사를 동사로, 사물이 사람처럼, 명사 기차, 짝 거리, 처음 보는 단어 짝
4. **왕복 번역** — 모델이 같은 뜻의 다른 표현을 두고 "골랐다"는 증거
5. **모델 차이** — 훈련 단계가 쌓일수록 커지고, 고칠 수도 있다
6. **글자 벌금 실험실** — λ와 β를 바꾸며 논문 식 (2)를 직접 계산
7. **대결** — 무조건 짧게(주판봇) vs 맥락 따라(초파리 연구원)
8. **한국어로 다시 읽기** — 개조식·행정 명사·번역투와 견주기, 점검표
9. **지식 색인과 꾸러미** — 검색 가능한 색인, JSON-LD·Turtle·CSV·BibTeX·RIS 내려받기

## 숫자로 보기

| 항목 | 값 |
|---|---|
| 분석한 모델 | 14종 (최신·준최신 9 + 소형 공개 5) |
| 대화 장면 모델 응답 | 1,428개 (대화 120개) |
| 에세이 | AI 980편 : 학생 2,934편 |
| 사람 글보다 사물 주어·낯선 단어 짝이 많은 최신 모델 | 9 / 9 |
| Opus 5.5가 Opus 5보다 낮게 나온 비교 | 19 / 21 |
| 글자 벌금만 주면(β=0) 짧은 쪽을 고른 비율 | 98% 넘음 |

## 주의

- 논문은 영어 글만 분석했습니다. 한국어 예문은 설명용이며 측정된 결과가 아닙니다.
- 대결의 읽기 시간 모형과 일부 그림은 설명용 모형입니다. 페이지 안에 노란 도장으로 표시했습니다.

## 저장소 구성

| 파일 | 내용 |
|---|---|
| `index.html` | 목차 (표지 + 편 카드) |
| `07_ai_text_readability.html` | 해설 페이지 (그림·지식 색인·꾸러미 내장) |
| `*.en.html` 등 | 외국어판 6개 (en·zh·ja·uz·ru·vi) |
| `cover_07.webp` · `thumb_07.webp` · `og_07.jpg` · `bg_07.webp` | 표지·목차 카드·공유 미리보기·배경 그림 |
| `docs/` | 제작 문서: 표지 지시문, 이미지 명세서, 개념 ID 등록부 |

## 출처

Clark, T. H., Martin, M. B., & Mahowald, K. (2026). Why is AI-generated language so hard to understand? arXiv preprint arXiv:2610.29162v1. https://arxiv.org/abs/2610.29162 (CC BY 4.0)

## 저자와 라이선스

글 · 안상선 ((주)M-Robo 대표). 캐릭터 그림은 [fruitfly-lab-expressions](https://adminmrobo.github.io/fruitfly-lab-expressions/) 기본 팩을 썼습니다.

이 페이지는 [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)으로 공개합니다. 교육·연구 목적 사용을 환영합니다.

---

<a id="en"></a>

# Why AI-written text is hard to read — the tone that length penalties created

AI Lab Explainer Dashboard Vol. 07 · Paper review **Ahn Sangsun** · Original paper Clark, Martin & Mahowald (2026)

A reworking, for Korean readers, of a paper that gathered conversation answers, coding answers and essays written by 14 of the latest AI models and measured how many expressions known to be hard for people to read they contain. It is a single-file interactive HTML explainer presented by the Doctor, the Assistant (Haru), the Fruit Fly Researcher and AbaBot.

- Public address: https://adminmrobo.github.io/ai_text_read_ability/index.en.html
- Contents: [index.html](index.en.html) · Open the commentary directly: [07_ai_text_readability.html](07_ai_text_readability.en.html)

![Cover](cover_07.webp)

## Languages

This series is available in the Korean original and in 6 foreign-language editions.

- How to choose: pick from the 🌐 language selector at the top of the menu or the 🌐 banner at the lower right. The language you choose is remembered by the browser.
- Automatic switching: when you first open the Korean page, if your browser language is a supported language, it switches to that language's edition. If you enter through a translated address, it opens as is.
- Add `?lang=en` to the end of the address to open directly in that language.
- Language edition files are named `name.languagecode.html`.

<!-- i18n:langtable -->
| Languages | File name | Open |
|---|---|---|
| 한국어 | `index.html` | [View now](https://adminmrobo.github.io/ai_text_read_ability/index.html) |
| English | `index.en.html` | [View now](https://adminmrobo.github.io/ai_text_read_ability/index.en.html) |
| 中文 | `index.zh.html` | [View now](https://adminmrobo.github.io/ai_text_read_ability/index.zh.html) |
| 日本語 | `index.ja.html` | [View now](https://adminmrobo.github.io/ai_text_read_ability/index.ja.html) |
| Oʻzbekcha | `index.uz.html` | [View now](https://adminmrobo.github.io/ai_text_read_ability/index.uz.html) |
| Русский | `index.ru.html` | [View now](https://adminmrobo.github.io/ai_text_read_ability/index.ru.html) |
| Tiếng Việt | `index.vi.html` | [View now](https://adminmrobo.github.io/ai_text_read_ability/index.vi.html) |
<!-- /i18n:langtable -->

## What is on one page

1. **Question** — the grammar is right, so why do I read it twice?
2. **Method** — collecting text, dissecting sentences, human-text baseline, round-trip translation, comparing models, length penalty experiment
3. **Six habits** — relative clauses without "that", nouns as verbs, inanimate subjects acting like people, noun trains, dependency length, unattested word pairs
4. **Round-trip translation** — evidence that the model "chose" one of several ways of saying the same thing
5. **Model differences** — grow as training stages accumulate, and can be fixed
6. **Length penalty lab** — change λ and β and calculate the paper's equation (2) yourself
7. **Showdown** — always short (AbaBot) vs. by context (Fruit Fly Researcher)
8. **Reading in Korean** — comparison with report-style, administrative and translationese writing, plus a checklist
9. **Knowledge index and package** — searchable index; downloads in JSON-LD, Turtle, CSV, BibTeX and RIS

## Numbers at a glance

| Item | Value |
|---|---|
| Models analyzed | 14 (9 latest or near-latest + 5 small open) |
| Model responses in conversation scenes | 1,428 (120 conversations) |
| Essays | AI 980 : student 2,934 |
| Latest models using more inanimate subjects and unfamiliar word pairs than human text | 9 / 9 |
| Comparisons where Opus 5.5 scored lower than Opus 5 | 19 / 21 |
| Share choosing the shorter option with only a length penalty (β=0) | Over 98% |

## Note

- The paper analyzed English text only. The Korean examples are illustrative and are not measured results.
- The reading-time model in the showdown and some figures are illustrative models. They are marked with yellow stamps on the page.

## Repository structure

| Files | Content |
|---|---|
| `index.html` | Contents (cover + episode cards) |
| `07_ai_text_readability.html` | Commentary page (figures, knowledge index, and export bundle built in) |
| `*.en.html` etc. | 6 foreign-language editions (en·zh·ja·uz·ru·vi) |
| `cover_07.webp` · `thumb_07.webp` · `og_07.jpg` · `bg_07.webp` | Cover, contents cards, share previews, background art |
| `docs/` | Production docs: cover instructions, image specifications, concept ID register |

## Sources

Clark, T. H., Martin, M. B., & Mahowald, K. (2026). Why is AI-generated language so hard to understand? arXiv preprint arXiv:2610.29162v1. https://arxiv.org/abs/2610.29162 (CC BY 4.0)

## Author and license

Text · Ahn Sangsun (CEO, M-Robo Inc.). Character drawings use the [fruitfly-lab-expressions](https://adminmrobo.github.io/fruitfly-lab-expressions/) base pack.

This page is published under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.en). Use for education and research is welcome.

---

<a id="zh"></a>

# AI 写的文章为何不好读——字数罚款塑造的文风

AI 实验室解说仪表板 第 07 篇 · 论文评论 **Ahn Sangsun** · 原论文 Clark, Martin & Mahowald (2026)

将收集最新 AI 模型 14 个的对话、编程回答与论文，统计人们公认难读的表达有多少的论文，为韩语读者重新编写。由博士 · 助手（Haru） · 果蝇研究员 · 算盘宝主持的单文件 HTML 互动解说。

- 公开地址：https://adminmrobo.github.io/ai_text_read_ability/index.zh.html
- 目录：[index.html](index.zh.html) · 直接打开解说：[07_ai_text_readability.html](07_ai_text_readability.zh.html)

![封面](cover_07.webp)

## 语言

本系列可以用韩语原版和 6 个外语版阅读。

- 选择方法：在页面最上方菜单的 🌐 语言选择框或右下角 🌐 横幅中选择。所选语言会记在浏览器里。
- 自动切换：首次进入韩语页面时，如果浏览器语言是受支持的语言，就会切换到该语言版。通过译文地址进入则直接打开。
- 在地址末尾加上 `?lang=en` 这样的参数，即可直接以该语言打开。
- 语言版文件名为 `名称.语言代码.html`。

<!-- i18n:langtable -->
| 语言 | 文件名 | 直接查看 |
|---|---|---|
| 한국어 | `index.html` | [直接查看](https://adminmrobo.github.io/ai_text_read_ability/index.html) |
| English | `index.en.html` | [直接查看](https://adminmrobo.github.io/ai_text_read_ability/index.en.html) |
| 中文 | `index.zh.html` | [直接查看](https://adminmrobo.github.io/ai_text_read_ability/index.zh.html) |
| 日本語 | `index.ja.html` | [直接查看](https://adminmrobo.github.io/ai_text_read_ability/index.ja.html) |
| Oʻzbekcha | `index.uz.html` | [直接查看](https://adminmrobo.github.io/ai_text_read_ability/index.uz.html) |
| Русский | `index.ru.html` | [直接查看](https://adminmrobo.github.io/ai_text_read_ability/index.ru.html) |
| Tiếng Việt | `index.vi.html` | [直接查看](https://adminmrobo.github.io/ai_text_read_ability/index.vi.html) |
<!-- /i18n:langtable -->

## 本篇包含的内容

1. **问题** — 语法没错，为什么要读两遍？
2. **方法** — 收集文本、句子解剖、人类文本基线、往返翻译、模型间比较、字数罚款实验
3. **六种习惯** — 去掉 that 的关系从句、名词动词化、事物像人一样、名词串、配对距离、生疏的词对
4. **往返翻译** — 模型在同义的其他表达中“选择”了某一种的证据
5. **模型差异** — 随训练阶段累积而增大，并且可以修正
6. **字数罚款实验室** — 改变 λ 与 β，亲自计算论文式 (2)
7. **对决** — 一律写短（算盘宝） vs 随语境而定（果蝇研究员）
8. **用韩语再读** — 与开列式·行政名词·翻译腔对照，检查表
9. **知识索引与文献包** — 可搜索的索引，下载 JSON-LD·Turtle·CSV·BibTeX·RIS

## 用数字看

| 项目 | 数值 |
|---|---|
| 分析的模型 | 14 个（最新·准最新 9 + 小型公开 5） |
| 对话场景的模型回复 | 1,428 个（对话 120 个） |
| 论文 | AI 980 篇 : 学生 2,934 篇 |
| 比人类文本更多使用无生命主语·生疏词对的最新模型 | 9 / 9 |
| Opus 5.5 低于 Opus 5 的比较 | 19 / 21 |
| 仅给字数罚款（β=0）时选择短表达的比例 | 超过 98% |

## 注意

- 论文只分析了英语文本。韩语例句为说明用，并非测量结果。
- 对决的阅读时间模型和部分图为说明用模型。页面中以黄色图章标示。

## 仓库结构

| 文件 | 内容 |
|---|---|
| `index.html` | 目录（封面 + 篇目卡片） |
| `07_ai_text_readability.html` | 解说页面（内嵌图表、知识索引、资料包） |
| `*.en.html` 等 | 外语版 6 个（en·zh·ja·uz·ru·vi） |
| `cover_07.webp` · `thumb_07.webp` · `og_07.jpg` · `bg_07.webp` | 封面、目录卡片、分享预览、背景图 |
| `docs/` | 制作文档：封面说明、图像规格书、概念 ID 登记表 |

## 出处

Clark, T. H., Martin, M. B., & Mahowald, K. (2026). Why is AI-generated language so hard to understand? arXiv preprint arXiv:2610.29162v1. https://arxiv.org/abs/2610.29162 (CC BY 4.0)

## 作者与许可

文 · Ahn Sangsun（M-Robo 公司 CEO）。角色图使用了 [fruitfly-lab-expressions](https://adminmrobo.github.io/fruitfly-lab-expressions/) 基础包。

本页面以 [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.zh-hans) 公开。欢迎用于教育·研究目的。

---

<a id="ja"></a>

# AIが書いた文章はなぜ読みにくいのか — 文字罰金がつくった文体

AI研究室 解説ダッシュボード 第07編 · 論文レビュー **Ahn Sangsun** · 原論文 Clark, Martin & Mahowald (2026)

最新AIモデル14種が書いた会話・コーディング回答・エッセイを集め、人が読みにくいとされる表現がどれほど多いかを測った論文を、韓国語の読者向けに組み直しました。博士・助手（ハル）・ショウジョウバエ研究員・アバボットが進める、単一のHTMLインタラクティブ解説です。

- 公開アドレス: https://adminmrobo.github.io/ai_text_read_ability/index.ja.html
- 目次: [index.html](index.ja.html) · 解説をすぐ開く: [07_ai_text_readability.html](07_ai_text_readability.ja.html)

![表紙](cover_07.webp)

## 言語

このシリーズは韓国語の原本と外国語版6つで読めます。

- 選び方：画面最上部のメニューの 🌐 言語選択ボックス、または右下の 🌐 バナーから選びます。選んだ言語はブラウザに記憶されます。
- 自動切り替え：韓国語のページに初めて入ると、ブラウザの言語が対応言語であればその言語版へ移ります。翻訳版のアドレスで入った場合はそのまま開きます。
- アドレスの末尾に `?lang=en` のように付けると、その言語ですぐ開きます。
- 言語版ファイルは `名前.言語コード.html` の形です。

<!-- i18n:langtable -->
| 言語 | ファイル名 | すぐ見る |
|---|---|---|
| 한국어 | `index.html` | [今すぐ見る](https://adminmrobo.github.io/ai_text_read_ability/index.html) |
| English | `index.en.html` | [今すぐ見る](https://adminmrobo.github.io/ai_text_read_ability/index.en.html) |
| 中文 | `index.zh.html` | [今すぐ見る](https://adminmrobo.github.io/ai_text_read_ability/index.zh.html) |
| 日本語 | `index.ja.html` | [今すぐ見る](https://adminmrobo.github.io/ai_text_read_ability/index.ja.html) |
| Oʻzbekcha | `index.uz.html` | [今すぐ見る](https://adminmrobo.github.io/ai_text_read_ability/index.uz.html) |
| Русский | `index.ru.html` | [今すぐ見る](https://adminmrobo.github.io/ai_text_read_ability/index.ru.html) |
| Tiếng Việt | `index.vi.html` | [今すぐ見る](https://adminmrobo.github.io/ai_text_read_ability/index.vi.html) |
<!-- /i18n:langtable -->

## 一編に入っているもの

1. **問い** — 文法は合っているのに、なぜ二度読むことになるのか？
2. **方法** — 文章を集める、文の解剖、人の文章の基準線、往復翻訳、モデル同士の比較、文字罰金の実験
3. **六つの癖** — that 抜きの関係節、名詞を動詞に、無生物が人のように、名詞の列車、ペアの距離、初めて見る単語のペア
4. **往復翻訳** — モデルが同じ意味の別の表現の中から「選んだ」という証拠
5. **モデルの差** — 訓練段階が積み重なるほど大きくなり、直すこともできる
6. **文字罰金の実験室** — λとβを変えながら論文の式 (2) を直接計算
7. **対決** — 無条件に短く（アバボット） vs 文脈に応じて（ショウジョウバエ研究員）
8. **韓国語で読み直す** — 箇条書き・行政名詞・翻訳調と見比べる、点検表
9. **知識索引とパッケージ** — 検索可能な索引、JSON-LD・Turtle・CSV・BibTeX・RIS のダウンロード

## 数字で見る

| 項目 | 値 |
|---|---|
| 分析したモデル | 14種（最新・準最新 9 + 小型公開 5） |
| 会話場面のモデル応答 | 1,428件（会話 120件） |
| エッセイ | AI 980編 : 学生 2,934編 |
| 人の文章より無生物主語・見慣れない単語の組み合わせが多い最新モデル | 9 / 9 |
| Opus 5.5 が Opus 5 より低く出た比較 | 19 / 21 |
| 文字罰金だけを与えた場合（β=0）に短い方を選んだ割合 | 98%超 |

## 注意

- 論文は英語の文章だけを分析しました。韓国語の例文は説明用で、測定された結果ではありません。
- 対決の読み時間モデルと一部の図は説明用のモデルです。ページ内に黄色い印で示しました。

## リポジトリの構成

| ファイル | 内容 |
|---|---|
| `index.html` | 目次（表紙＋編カード） |
| `07_ai_text_readability.html` | 解説ページ（図・知識索引・エクスポートを内蔵） |
| `*.en.html` など | 外国語版6つ (en·zh·ja·uz·ru·vi) |
| `cover_07.webp` · `thumb_07.webp` · `og_07.jpg` · `bg_07.webp` | 表紙・目次カード・共有プレビュー・背景画像 |
| `docs/` | 制作文書: 表紙の指示文、画像仕様書、概念ID台帳 |

## 出典

Clark, T. H., Martin, M. B., & Mahowald, K. (2026). Why is AI-generated language so hard to understand? arXiv preprint arXiv:2610.29162v1. https://arxiv.org/abs/2610.29162 (CC BY 4.0)

## 執筆者とライセンス

執筆 · 株式会社M-Robo 代表 Ahn Sangsun。キャラクター画は [fruitfly-lab-expressions](https://adminmrobo.github.io/fruitfly-lab-expressions/) の基本パックを使いました。

このページは [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.ja) で公開します。教育・研究目的の利用を歓迎します。

---

<a id="uz"></a>

# AI yozgan matn nega yaxshi oʻqilmaydi — harf jarimasi yaratgan uslub

AI laboratoriyasi tushuntirish paneli 07-son · Maqola sharhi **Ahn Sangsun** · Asl maqola Clark, Martin & Mahowald (2026)

Eng yangi 14 AI modeli yozgan suhbat·kod javoblari·esselarni yigʻib, odamga oʻqish qiyin deb maʼlum iboralar qanchalik koʻpligini oʻlchagan maqolani koreys oʻquvchilariga moslab qayta bayon qildik. Doktor · Yordamchi (Haru) · Meva pashshasi tadqiqotchisi · AbaBot olib boradigan yagona HTML interaktiv tushuntirish.

- Ochiq manzil: https://adminmrobo.github.io/ai_text_read_ability/index.uz.html
- Mundarija: [index.html](index.uz.html) · Tushuntirishni darhol ochish: [07_ai_text_readability.html](07_ai_text_readability.uz.html)

![Muqova](cover_07.webp)

## Til

Bu turkumni koreys asl nusxasi va 6 ta xorijiy til versiyasida koʻrish mumkin.

- Tanlash usuli: ekranning yuqori menyusidagi 🌐 til tanlash qutisi yoki oʻng pastdagi 🌐 bannerdan tanlang. Tanlangan til brauzerda eslab qolinadi.
- Avtomatik oʻtish: koreys sahifasiga birinchi marta kirganda, brauzer tili qoʻllab-quvvatlanadigan til boʻlsa, oʻsha til versiyasiga oʻtiladi. Tarjima versiyasi manzili bilan kirilsa, oʻsha holicha ochiladi.
- Manzil oxiriga `?lang=en` kabi qoʻshsangiz, oʻsha tilda darrov ochiladi.
- Til versiyasi fayllari `nom.tilkodi.html` shaklida.

<!-- i18n:langtable -->
| Til | Fayl nomi | Darrov koʻrish |
|---|---|---|
| 한국어 | `index.html` | [Darhol koʻrish](https://adminmrobo.github.io/ai_text_read_ability/index.html) |
| English | `index.en.html` | [Darhol koʻrish](https://adminmrobo.github.io/ai_text_read_ability/index.en.html) |
| 中文 | `index.zh.html` | [Darhol koʻrish](https://adminmrobo.github.io/ai_text_read_ability/index.zh.html) |
| 日本語 | `index.ja.html` | [Darhol koʻrish](https://adminmrobo.github.io/ai_text_read_ability/index.ja.html) |
| Oʻzbekcha | `index.uz.html` | [Darhol koʻrish](https://adminmrobo.github.io/ai_text_read_ability/index.uz.html) |
| Русский | `index.ru.html` | [Darhol koʻrish](https://adminmrobo.github.io/ai_text_read_ability/index.ru.html) |
| Tiếng Việt | `index.vi.html` | [Darhol koʻrish](https://adminmrobo.github.io/ai_text_read_ability/index.vi.html) |
<!-- /i18n:langtable -->

## Bir sonda nimalar bor

1. **Savol** — grammatika toʻgʻri, lekin nega ikki marta oʻqishga toʻgʻri keladi?
2. **Usul** — matn yigʻish, gap tahlili, odam matni asosi, qaytib tarjima, modellarni solishtirish, harf jarimasi tajribasi
3. **Oltita odat** — that tushib qolgan nisbiy gap, otni feʼl qilish, jonsiz narsa odamdek, otlar poyezdi, juft masofasi, birinchi marta koʻrilgan soʻz juftligi
4. **Qaytib tarjima** — model bir xil maʼnoli boshqa iborani qoʻyib "tanlagani" isboti
5. **Model farqi** — oʻqitish bosqichlari qoʻshilgan sari kattalashadi va tuzatsa ham boʻladi
6. **Harf jarimasi laboratoriyasi** — λ va β ni oʻzgartirib, maqolaning (2) formulasini oʻzingiz hisoblang
7. **Bellashuv** — shartsiz qisqa (AbaBot) vs kontekstga qarab (Meva pashshasi tadqiqotchisi)
8. **Koreyscha qayta oʻqish** — qisqa band·maʼmuriy otlar·tarjima uslubi bilan taqqoslash, tekshiruv roʻyxati
9. **Bilimlar indeksi va toʻplam** — qidiriladigan indeks, JSON-LD·Turtle·CSV·BibTeX·RIS yuklab olish

## Raqamlar bilan

| Band | Qiymat |
|---|---|
| Tahlil qilingan model | 14 ta (eng yangi va yangiga yaqin 9 + kichik ochiq 5) |
| Suhbat sahnasidagi model javoblari | 1,428 ta (120 suhbat) |
| Esse | AI 980 ta : talaba 2,934 ta |
| Odam matnidan koʻp jonsiz narsa subyekti·birinchi marta koʻrilgan soʻz juftligini ishlatgan eng yangi modellar | 9 / 9 |
| Opus 5.5 Opus 5 dan past chiqqan taqqoslashlar | 19 / 21 |
| Faqat harf jarimasi berilganda (β=0) qisqa tomon tanlangan ulush | 98% dan koʻp |

## Diqqat

- Maqola faqat inglizcha matnni tahlil qilgan. Koreyscha misollar tushuntirish uchun va oʻlchangan natija emas.
- Bellashuvdagi oʻqish vaqti modeli va baʼzi rasmlar tushuntirish modeli. Sahifa ichida sariq muhr bilan belgilangan.

## Repozitoriy tuzilishi

| Fayllar | Mazmun |
|---|---|
| `index.html` | Mundarija (muqova + qism kartalari) |
| `07_ai_text_readability.html` | Tushuntirish sahifasi (rasmlar, bilimlar indeksi va toʻplam ichiga joylangan) |
| `*.en.html` va hokazo | 6 ta xorijiy til nashri (en·zh·ja·uz·ru·vi) |
| `cover_07.webp` · `thumb_07.webp` · `og_07.jpg` · `bg_07.webp` | Muqova, mundarija kartalari, ulashish koʻrinishi, fon rasmlari |
| `docs/` | Ishlab chiqarish hujjatlari: muqova koʻrsatmasi, rasm spetsifikatsiyasi, tushuncha ID reyestri |

## Manba

Clark, T. H., Martin, M. B., & Mahowald, K. (2026). Why is AI-generated language so hard to understand? arXiv preprint arXiv:2610.29162v1. https://arxiv.org/abs/2610.29162 (CC BY 4.0)

## Muallif va litsenziya

Matn · Ahn Sangsun (M-Robo kompaniyasi rahbari). Qahramon rasmlari uchun [fruitfly-lab-expressions](https://adminmrobo.github.io/fruitfly-lab-expressions/) asosiy toʻplamidan foydalanildi.

Bu sahifa [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.en) ostida ochiq. Taʼlim·tadqiqot maqsadida foydalanishni mamnuniyat bilan qabul qilamiz.

---

<a id="ru"></a>

# Почему текст, написанный ИИ, читается тяжело — манера, рождённая штрафом за длину

Панель-пояснение «AI-лаборатория» выпуск 07 · обзор статьи **Ahn Sangsun** · оригинальная статья Clark, Martin & Mahowald (2026)

Мы собрали диалоги, ответы по программированию и эссе, написанные 14 новейшими моделями ИИ, и заново объяснили для читателей на русском статью, которая измерила, сколько в них выражений, трудных для чтения людям. Это интерактивное пояснение в одном HTML-файле, которое ведут Доктор · ассистент (Хару) · Исследователь-дрозофила · АбаБот.

- Публичный адрес: https://adminmrobo.github.io/ai_text_read_ability/index.ru.html
- Оглавление: [index.html](index.ru.html) · Сразу открыть пояснение: [07_ai_text_readability.html](07_ai_text_readability.ru.html)

![Обложка](cover_07.webp)

## Языки

Эту серию можно смотреть в корейском оригинале и 6 переводах.

- Как выбрать: в списке 🌐 в верхнем меню экрана или на баннере 🌐 справа внизу. Выбранный язык запоминается в браузере.
- Автопереключение: при первом заходе на корейскую страницу, если язык браузера поддерживается, открывается версия на этом языке. Если зайти по адресу переведённой версии, она открывается как есть.
- Если добавить в конец адреса `?lang=en`, страница сразу откроется на этом языке.
- Файлы языковых версий имеют вид `имя.код_языка.html`.

<!-- i18n:langtable -->
| Языки | Имя файла | Открыть |
|---|---|---|
| 한국어 | `index.html` | [Открыть](https://adminmrobo.github.io/ai_text_read_ability/index.html) |
| English | `index.en.html` | [Открыть](https://adminmrobo.github.io/ai_text_read_ability/index.en.html) |
| 中文 | `index.zh.html` | [Открыть](https://adminmrobo.github.io/ai_text_read_ability/index.zh.html) |
| 日本語 | `index.ja.html` | [Открыть](https://adminmrobo.github.io/ai_text_read_ability/index.ja.html) |
| Oʻzbekcha | `index.uz.html` | [Открыть](https://adminmrobo.github.io/ai_text_read_ability/index.uz.html) |
| Русский | `index.ru.html` | [Открыть](https://adminmrobo.github.io/ai_text_read_ability/index.ru.html) |
| Tiếng Việt | `index.vi.html` | [Открыть](https://adminmrobo.github.io/ai_text_read_ability/index.vi.html) |
<!-- /i18n:langtable -->

## Что входит в выпуск

1. **Вопрос** — грамматика верна, так почему приходится читать дважды?
2. **Метод** — сбор текстов, разбор предложений, эталон человеческих текстов, двойной перевод, сравнение моделей, эксперимент со штрафом за длину
3. **Шесть привычек** — придаточное без that, существительное как глагол, вещь как человек, поезд существительных, дистанция пары, невиданная пара слов
4. **Двойной перевод** — доказательство того, что модель «выбрала» другое выражение с тем же смыслом
5. **Разница моделей** — растёт с накоплением этапов обучения, но это можно исправить
6. **Лаборатория штрафа за длину** — меняя λ и β, самим вычислить формулу (2) статьи
7. **Поединок** — всегда коротко (АбаБот) vs по контексту (Исследователь-дрозофила)
8. **Перечитаем по-корейски** — сравнение с тезисным стилем, канцелярскими существительными и калькой, чек-лист
9. **Указатель знаний и пакет** — поисковый указатель, скачивание JSON-LD·Turtle·CSV·BibTeX·RIS

## В числах

| Пункт | Значение |
|---|---|
| Проанализировано моделей | 14 (9 новейших и почти новейших + 5 малых открытых) |
| Ответы моделей в диалогах | 1,428 (120 диалогов) |
| Эссе | ИИ 980 : студенты 2,934 |
| Новейшие модели, у которых неодушевлённых подлежащих и необычных пар слов больше, чем в текстах людей | 9 / 9 |
| Сравнения, где у Opus 5.5 ниже, чем у Opus 5 | 19 / 21 |
| Доля выбора короткого при одном штрафе за длину (β=0) | более 98% |

## Внимание

- Статья анализировала только английские тексты. Корейские примеры учебные, не измеренный результат.
- Модель времени чтения в поединке и некоторые рисунки — учебные модели. Они отмечены на странице жёлтым штампом.

## Структура репозитория

| Файлы | Содержание |
|---|---|
| `index.html` | Оглавление (обложка + карточки выпусков) |
| `07_ai_text_readability.html` | Страница пояснения (рисунки, указатель знаний и пакет встроены) |
| `*.en.html` и т. д. | 6 версий на иностранных языках (en·zh·ja·uz·ru·vi) |
| `cover_07.webp` · `thumb_07.webp` · `og_07.jpg` · `bg_07.webp` | Обложка, карточки оглавления, превью для публикации, фоновые рисунки |
| `docs/` | Производственные документы: инструкция к обложке, спецификация изображений, реестр ID понятий |

## Источник

Clark, T. H., Martin, M. B., & Mahowald, K. (2026). Why is AI-generated language so hard to understand? arXiv preprint arXiv:2610.29162v1. https://arxiv.org/abs/2610.29162 (CC BY 4.0)

## Авторы и лицензия

Текст · Ahn Sangsun (генеральный директор M-Robo). Рисунки персонажей взяты из базового набора [fruitfly-lab-expressions](https://adminmrobo.github.io/fruitfly-lab-expressions/).

Эта страница опубликована под лицензией [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.ru). Использование в образовательных и исследовательских целях приветствуется.

---

<a id="vi"></a>

# Vì sao văn bản do AI viết khó đọc — giọng văn do phạt độ dài tạo ra

Bảng giải thích Phòng thí nghiệm AI Số 07 · Đánh giá bài báo **Ahn Sangsun** · Bài báo gốc Clark, Martin & Mahowald (2026)

Bài báo thu thập hội thoại, câu trả lời lập trình và tiểu luận do 14 mô hình AI mới nhất viết, rồi đo xem những cách diễn đạt được biết là khó đọc xuất hiện nhiều đến mức nào. Ở đây nó được diễn giải lại cho độc giả Hàn Quốc. Đây là bản giải thích tương tác trong một tệp HTML do Tiến sĩ · Trợ lý (Haru) · Nhà nghiên cứu Ruồi giấm · AbaBot dẫn dắt.

- Địa chỉ công khai: https://adminmrobo.github.io/ai_text_read_ability/index.vi.html
- Mục lục: [index.html](index.vi.html) · Mở thẳng bản giải thích: [07_ai_text_readability.html](07_ai_text_readability.vi.html)

![Bìa](cover_07.webp)

## Ngôn ngữ

Loạt bài này có thể xem bằng bản gốc tiếng Hàn và 6 bản tiếng nước ngoài.

- Cách chọn: chọn ở hộp chọn ngôn ngữ 🌐 trên thanh menu ở đầu màn hình hoặc ở biểu ngữ 🌐 góc dưới bên phải. Ngôn ngữ đã chọn sẽ được trình duyệt ghi nhớ.
- Tự động chuyển: khi lần đầu vào trang tiếng Hàn, nếu ngôn ngữ trình duyệt là ngôn ngữ được hỗ trợ thì sẽ chuyển sang bản ngôn ngữ đó. Nếu vào bằng địa chỉ bản dịch thì mở nguyên như vậy.
- Thêm `?lang=en` vào cuối địa chỉ thì mở thẳng bằng ngôn ngữ đó.
- Tệp của bản ngôn ngữ có dạng `tên.mã_ngôn_ngữ.html`.

<!-- i18n:langtable -->
| Ngôn ngữ | Tên tệp | Xem ngay |
|---|---|---|
| 한국어 | `index.html` | [Xem ngay](https://adminmrobo.github.io/ai_text_read_ability/index.html) |
| English | `index.en.html` | [Xem ngay](https://adminmrobo.github.io/ai_text_read_ability/index.en.html) |
| 中文 | `index.zh.html` | [Xem ngay](https://adminmrobo.github.io/ai_text_read_ability/index.zh.html) |
| 日本語 | `index.ja.html` | [Xem ngay](https://adminmrobo.github.io/ai_text_read_ability/index.ja.html) |
| Oʻzbekcha | `index.uz.html` | [Xem ngay](https://adminmrobo.github.io/ai_text_read_ability/index.uz.html) |
| Русский | `index.ru.html` | [Xem ngay](https://adminmrobo.github.io/ai_text_read_ability/index.ru.html) |
| Tiếng Việt | `index.vi.html` | [Xem ngay](https://adminmrobo.github.io/ai_text_read_ability/index.vi.html) |
<!-- /i18n:langtable -->

## Nội dung có trong một số

1. **Câu hỏi** — ngữ pháp đúng mà sao phải đọc hai lần?
2. **Phương pháp** — thu thập văn bản, mổ xẻ câu, mốc văn người, dịch khứ hồi, so các mô hình với nhau, thí nghiệm phạt độ dài
3. **Sáu thói quen** — mệnh đề quan hệ bỏ that, danh từ thành động từ, vật như người, đoàn tàu danh từ, khoảng cách cặp, cặp từ chưa từng thấy
4. **Dịch khứ hồi** — bằng chứng cho thấy mô hình đã "chọn" dù có cách diễn đạt khác cùng nghĩa
5. **Khác biệt giữa các mô hình** — càng chồng nhiều giai đoạn huấn luyện càng lớn, và cũng có thể sửa được
6. **Phòng thực nghiệm phạt độ dài** — đổi λ và β rồi tự tính công thức (2) của bài báo
7. **Đối đầu** — cứ ngắn là được (AbaBot) vs theo ngữ cảnh (Nhà nghiên cứu Ruồi giấm)
8. **Đọc lại bằng tiếng Hàn** — đối chiếu với văn gạch đầu dòng·danh từ hành chính·lối dịch, cùng bảng kiểm
9. **Chỉ mục tri thức và gói tải về** — chỉ mục tìm kiếm được, tải JSON-LD·Turtle·CSV·BibTeX·RIS

## Xem bằng con số

| Mục | Giá trị |
|---|---|
| Mô hình được phân tích | 14 (9 mới và gần mới + 5 nhỏ công khai) |
| Câu trả lời của mô hình trong cảnh hội thoại | 1,428 (120 hội thoại) |
| Tiểu luận | AI 980 bài : sinh viên 2,934 bài |
| Mô hình mới dùng chủ ngữ là vật·cặp từ lạ nhiều hơn văn người | 9 / 9 |
| Số phép so sánh Opus 5.5 thấp hơn Opus 5 | 19 / 21 |
| Tỷ lệ chọn vế ngắn khi chỉ phạt độ dài (β=0) | Trên 98% |

## Lưu ý

- Bài báo chỉ phân tích văn tiếng Anh. Các câu ví dụ tiếng Hàn chỉ để minh họa và không phải kết quả đã đo.
- Mô hình thời gian đọc trong phần đối đầu và một số hình là mô hình minh họa. Chúng được đánh dấu bằng dấu vàng trong trang.

## Cấu trúc kho lưu trữ

| Tệp | Nội dung |
|---|---|
| `index.html` | Mục lục (bìa + thẻ các tập) |
| `07_ai_text_readability.html` | Trang giải thích (tích hợp hình, chỉ mục tri thức và gói tải về) |
| `*.en.html` v.v. | 6 bản ngoại ngữ (en·zh·ja·uz·ru·vi) |
| `cover_07.webp` · `thumb_07.webp` · `og_07.jpg` · `bg_07.webp` | Bìa, thẻ mục lục, ảnh xem trước khi chia sẻ, hình nền |
| `docs/` | Tài liệu sản xuất: chỉ dẫn bìa, bản mô tả hình ảnh, sổ đăng ký ID khái niệm |

## Nguồn

Clark, T. H., Martin, M. B., & Mahowald, K. (2026). Why is AI-generated language so hard to understand? arXiv preprint arXiv:2610.29162v1. https://arxiv.org/abs/2610.29162 (CC BY 4.0)

## Tác giả và giấy phép

Viết bởi Ahn Sangsun (Giám đốc điều hành M-Robo). Hình nhân vật dùng gói cơ bản [fruitfly-lab-expressions](https://adminmrobo.github.io/fruitfly-lab-expressions/).

Trang này được công khai theo [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.vi). Chúng tôi hoan nghênh việc sử dụng cho mục đích giáo dục·nghiên cứu.
