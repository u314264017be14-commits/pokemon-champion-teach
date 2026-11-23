# AGENTS.md — 寶可夢 VGC 雙打對戰新手教學知識庫

本專案依照 Karpathy 的 LLM Wiki 構想運作：人類把原始資料放進 `raw/`，LLM 負責把資料整理、交叉連結、維護成 `wiki/` 中的知識庫。本文件是 LLM 維護這個 wiki 時必須遵守的規範。

---

## 1. 目標讀者與內容深度

- **讀者**：準備參加 VGC（線上或實體）比賽的新手。已經玩過寶可夢，但對雙打對戰的規則、組隊與實戰觀念還不熟。
- **深度**：要講到**數值計算**。每個機制都要交代：
  1. 是什麼（定義）
  2. 為什麼重要（在雙打中的戰術意義）
  3. 數值細節（倍率、疊乘順序、速度線、計算範例）
  4. 實戰怎麼用、常見誤區
- 只要 raw 資料沒有提到的數值或計算，都用 LLM 自身的遊戲知識補充。所有補充內容都要寫成 `（補充，非 raw 來源）`，並遵守第 6 節的矛盾處理規則。

---

## 2. 目錄結構

```
raw/                     # 原始資料。唯讀：LLM 不得修改、改名或刪除
wiki/
├── index.md             # 總目錄：列出所有頁面與一句話摘要
├── log.md               # 更新紀錄：每次 ingest / lint / 修正都要追加
├── concepts/            # 核心機制與概念頁
│                        #   賽制規則、控速、優先度、守住、掩護、群體招式、
│                        #   輪替、天氣、場地、道具、寶可夢單卡
└── archetypes/          # 隊伍體系頁（雨天、重空間……）
AGENTS.md                # 本文件
```

- 檔名一律用**英文 kebab-case**，例如 `concepts/trick-room.md`、`archetypes/rain.md`。
- 寶可夢單卡也放在 `concepts/`，檔名加上 `pokemon-` 前綴，例如 `concepts/pokemon-incineroar.md`。
- 拆頁原則：一個獨立機制、一隻寶可夢或一個隊伍體系就是一頁。若一個機制必須在多頁重複解釋，就把它拆成獨立頁面，再用連結引用。

---

## 3. 語言與術語

- 內文一律使用**繁體中文**。
- 專有名詞（招式、特性、道具、寶可夢、天氣、場地、規則名稱）**在每一頁第一次出現時**都要附英文，格式為 `戲法空間（Trick Room）`。同一頁後面再出現時只寫中文。
  - 「第一次出現」從 H1 標題下方的第一個 `##` 章節開始算。以下兩處**不算**，可以直接寫中文：
    - 開頭的 `> 一句話摘要`
    - 頁尾的「相關頁面」清單
  - 粗體小標題（例如 `- **守住拖延**：`）也算正文。如果小標題就是第一次出現，英文可以補在同一行的說明裡第一次提到它的地方。
- 譯名必須全站統一。新譯名出現時，先在下方「術語對照表」登記再使用；如果和 raw 的用語不同，以對照表為準，並在 log.md 記錄。

### 術語對照表

| 中文 | English |
|---|---|
| 順風 | Tailwind |
| 戲法空間 | Trick Room |
| 優先度 / 先制招式 | Priority / Priority move |
| 守住 | Protect |
| 看我嘛 | Follow Me |
| 憤怒粉 | Rage Powder |
| 群體招式 | Spread move |
| 擊掌奇襲 | Fake Out |
| 拋下狠話 | Parting Shot |
| 威嚇 | Intimidate |
| 大晴天 / 下雨 / 沙暴 / 雪天 | Sun / Rain / Sandstorm / Snow |
| 電氣場地 / 青草場地 / 精神場地 / 薄霧場地 | Electric / Grassy / Psychic / Misty Terrain |
| 道具不重複條款 | Item Clause |
| 物種不重複條款 | Species Clause |
| 報名隊伍 / 隊伍登記 | Team Sheet / Team Check |
| 公開隊伍表 | Open Team Sheet |
| 隊伍預覽 | Team Preview |
| 雙打對戰 | Double Battle |
| 種族值 / 個體值 / 努力值 / 性格 | Base Stats / IV / EV / Nature |
| 比賽無效 / 判敗 | Void / Game Loss |
| 控速 | Speed Control |
| 同速 | Speed tie |
| 能力階級 | Stat Stage |
| 麻痺 | Paralysis |
| 神速 | Extreme Speed |
| 影子偷襲 | Shadow Sneak |
| 突襲 | Sucker Punch |
| 真空波 | Vacuum Wave |
| 電光一閃 | Quick Attack |
| 冰凍之風 | Icy Wind |
| 電網 | Electroweb |
| 挑釁 | Taunt |
| 掩護招式 | Redirection |
| 輪替 | Switching |
| 佯攻 | Feint |
| 熱風 | Heat Wave |
| 岩崩 | Rock Slide |
| 魔法閃耀 | Dazzling Gleam |
| 月亮之力 | Moonblast |
| 地震 | Earthquake |
| 畏縮 | Flinch |
| 精神力 | Inner Focus |
| 防塵 | Overcoat |
| 飄浮 | Levitate |
| 防塵護目鏡 | Safety Goggles |
| 密探斗篷 | Covert Cloak |
| 擊中要害 | Critical hit |
| 本系加成 | STAB |
| 灼傷 | Burn |
| 天氣 / 場地 | Weather / Terrain |
| 異常狀態 | Status condition |
| 降雨 | Drizzle |
| 精神製造者 | Psychic Surge |
| 古代活性 | Protosynthesis |
| 驅勁能量 | Booster Energy |
| 蘑菇孢子 | Spore |
| 暗影球 | Shadow Ball |
| 噴射拳 | Jet Punch |
| 波動衝 | Wave Crash |
| 全能變身 | Zero to Hero |
| 廣域防守 | Wide Guard |
| 快速防守 | Quick Guard |
| 混亂 | Confusion |
| 講究頭帶 / 講究眼鏡 / 講究圍巾 | Choice Band / Choice Specs / Choice Scarf |
| 突擊背心 | Assault Vest |
| 生命寶珠 | Life Orb |
| 氣勢披帶 | Focus Sash |
| 振翼髮 | Flutter Mane |
| 熾焰咆哮虎 | Incineroar |
| 大嘴鷗 | Pelipper |
| 海豚俠 | Palafin |
| 愛管侍 | Indeedee |
| 敗露球菇 | Amoonguss |

---

## 4. 頁面範本

每頁開頭都用 YAML frontmatter，正文依類型套用下列範本。**範本裡的每個章節都必須存在**；如果暫時沒有內容，就寫 `（待補）`。

### 4.1 概念頁（`concepts/*.md`）

```markdown
---
title: 戲法空間（Trick Room）
type: concept
tags: [控速]
updated: YYYY-MM-DD
---

# 戲法空間（Trick Room）

> 一句話摘要。

## 定義
## 為什麼重要
## 數值與計算
## 實戰應用
## 常見誤區
## 相關頁面
- [[concepts/priority]]

---
**來源**
- raw/speed-control-and-priority.md
```

### 4.2 寶可夢單卡頁（`concepts/pokemon-*.md`）

```markdown
---
title: 熾焰咆哮虎（Incineroar）
type: pokemon
tags: [輔助, 火, 惡]
updated: YYYY-MM-DD
---

# 熾焰咆哮虎（Incineroar）

> 一句話定位。

## 基本資料          （屬性、特性、種族值表格與總和）
## 數值分析          （Lv.50 實數值範例、關鍵速度線）
## 定位與常見招式
## 常見搭配與體系
## 如何應對
## 相關頁面

---
**來源**
- raw/...
```

### 4.3 隊伍體系頁（`archetypes/*.md`）

```markdown
---
title: 雨天體系（Rain Team）
type: archetype
tags: [天氣]
updated: YYYY-MM-DD
---

# 雨天體系（Rain Team）

> 一句話說明這個體系怎麼贏。

## 核心組合
## 運作邏輯
## 數值與計算        （例如雨天加成 × 群體修正的實際傷害疊乘）
## 開局與選角思路
## 弱點與反制
## 相關頁面

---
**來源**
- raw/...
```

### 4.4 連結規則

- 內部連結使用 wiki 連結語法 `[[資料夾/檔名]]`，不加 `.md`。
- 每頁的「相關頁面」至少要有 1 個連結，而且每頁至少要被 1 個其他頁面或 `index.md` 連到。

---

## 5. 引用出處

- **只在頁尾**的「**來源**」區塊列出這一頁參考的 raw 檔案路徑，內文不逐段標註。
- 用 LLM 自身知識補充的內容，在內文寫上 `（補充，非 raw 來源）`；頁尾的來源區塊不需要另外列出。

---

## 6. 矛盾與待查證處理

遇到下列情況時，**不得擅自改寫或刪除任何一方的說法**：

- 兩份 raw 資料之間互相矛盾
- raw 內容與 LLM 已知的遊戲機制或版本不符（例如招式效果在不同世代有改動）
- wiki 現有頁面與新 ingest 的資料互相矛盾

處理方式：

1. 在相關頁面中加入以下區塊，列出各方說法與來源：

   ```markdown
   > [!WARNING] ⚠️ 矛盾／待查證
   > - 說法 A：……（來源：raw/xxx.md）
   > - 說法 B：……（來源：LLM 補充 / raw/yyy.md）
   > - 狀態：待查證
   ```

2. 在 `log.md` 記錄這筆矛盾。
3. 經使用者裁定後，更新內文並把狀態改為 `已解決：採用說法 X（YYYY-MM-DD）`，同時寫入 log。

---

## 7. 工作流程

### 7.1 Ingest（一次一篇，逐篇確認）

1. 使用者指定一篇 `raw/` 檔案；如果沒有指定，就挑選尚未在 `log.md` 出現過的下一篇。
2. 讀完全文，列出這篇涉及的概念、寶可夢與體系。
3. 新建或更新對應的 wiki 頁面：
   - 新頁面要套用第 4 節的範本。
   - 既有頁面要合併新資訊，而不是覆蓋舊內容，並更新 `updated` 日期與頁尾來源。
   - 遇到矛盾時依第 6 節處理。
4. 更新 `index.md`。
5. 在 `log.md` 追加紀錄。
6. **向使用者回報**本次新增或修改的頁面清單和發現的矛盾，然後**停下來等待確認**，再處理下一篇。

### 7.2 Query（回答問題）

- 先讀 `index.md` 找出相關頁面，再根據 wiki 內容回答，並註明引用了哪些頁面。
- 如果回答產生值得保存的新整理內容（例如比較表或計算範例），詢問使用者是否要存成新頁面。

### 7.3 Lint（健康檢查）

執行時逐項檢查，輸出問題清單後**先回報、不自動修正**，等使用者同意再修：

**A. 連結與目錄完整性**
- 指向不存在頁面的壞連結
- 孤兒頁：沒有被任何頁面或 `index.md` 連到的頁面
- `index.md` 漏列的頁面，或列出了已不存在的頁面

**B. 來源與 log 一致**
- 頁尾缺少「來源」區塊
- 來源列出的 raw 檔案不存在
- `raw/` 中尚未 ingest 的檔案
- 有頁面變更但 `log.md` 缺少對應紀錄

**C. 事實一致與矛盾**
- 不同頁面對同一數值（倍率、種族值、速度等）的說法不一致
- 尚未解決的「⚠️ 矛盾／待查證」區塊

**D. 格式與術語規範**
- frontmatter 或範本章節缺漏
- 專有名詞在該頁第一次出現時沒有附英文（不算摘要句和「相關頁面」清單，見第 3 節）
- 譯名與術語對照表不一致
- 檔名不是英文 kebab-case

Lint 結果要寫入 `log.md`。

---

## 8. index.md 與 log.md 格式

### index.md

依資料夾分區，每行一頁：

```markdown
- [[concepts/trick-room]] — 倒轉出手順序的核心控速手段
```

### log.md

只追加、不改寫歷史紀錄，最新的放在最下面：

```markdown
## [YYYY-MM-DD] ingest | raw/xxx.md
- 新增：concepts/a, concepts/b
- 更新：archetypes/c
- 矛盾：……（或「無」）
```

類型標籤可用：`init`、`ingest`、`lint`、`fix`、`resolve`。
