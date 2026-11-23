# 更新紀錄

## [2026-11-23] init | 建立知識庫結構
- 新增：AGENTS.md、wiki/index.md、wiki/log.md、wiki/concepts/、wiki/archetypes/
- 待 ingest：raw/vgc-rules.md、raw/speed-control-and-priority.md、raw/protect-redirection-spread-switching.md、raw/weather-terrain-items.md、raw/team-archetypes-and-key-pokemon.md

## [2026-11-23] ingest | raw/vgc-rules.md
- 新增：concepts/vgc-format, concepts/stat-calculation, concepts/team-rules, concepts/tournament-conduct
- 更新：index.md；AGENTS.md 術語對照表新增 8 組譯名（Species Clause、Team Sheet/Team Check、Open Team Sheet、Team Preview、Double Battle、Base Stats/IV/EV/Nature、Void/Game Loss）
- 補充（非 raw 來源）：帶 6 選 4、隊伍預覽 90 秒／個人剩餘時間 7 分鐘／單局總時間 20 分鐘、物種不重複條款、公開隊伍表、Lv.50 能力值公式與速度速查表
- 矛盾：
  - concepts/tournament-conduct：「只能在回合開始時」做筆記的時間限制，與 LLM 認知不符 → 待查證
  - concepts/tournament-conduct：斷線「超過兩回合」的具體門檻無法確認 → 待查證

## [2026-11-23] resolve | concepts/tournament-conduct
- 筆記時機：採用說法 B（使用者確認）。官方允許對局中做筆記，沒有時間限制；raw/vgc-rules.md 的「只能在回合開始時」不採用
- 斷線判定：採用說法 B（使用者確認）。官方規則沒有「兩回合」門檻，由裁判審視戰局判定；raw/vgc-rules.md 的「超過兩回合」不採用
- 更新：concepts/tournament-conduct（摘要、定義、常見誤區、矛盾區塊狀態）、index.md 摘要

## [2026-11-23] ingest | raw/speed-control-and-priority.md
- 新增：concepts/turn-order, concepts/tailwind, concepts/trick-room, concepts/priority
- 更新：concepts/stat-calculation（相關頁面加入 turn-order、trick-room；補上「戲法空間」首次出現時的英文）、index.md；AGENTS.md 術語對照表新增 11 組譯名
- 補充（非 raw 來源）：回合內判定順序、實際速度公式與能力階級倍率、第八世代以後速度即時變動、順風 ×2／4 回合、戲法空間 5 回合／優先度 −7／再次使用會解除、常見招式優先度表、影子偷襲的成功條件
- 矛盾：
  - concepts/priority：raw 寫「神速」是優先度 +1；LLM 認知是 +2 → 待查證

## [2026-11-23] fix | concepts/priority
- 神速優先度的矛盾區塊加入說法 C：使用者表示是 +3。與 LLM 認知（+2）衝突，狀態維持待查證

## [2026-11-23] resolve | concepts/priority
- 神速優先度：採用說法 B（+2），使用者已上網確認；使用者撤回說法 C（+3）；raw/speed-control-and-priority.md 的「+1」不採用
- 更新：concepts/priority（定義段改為「神速（+2）、影子偷襲（+1）」、矛盾區塊狀態）、index.md 摘要

## [2026-11-23] ingest | raw/protect-redirection-spread-switching.md
- 新增：concepts/protect, concepts/redirection, concepts/spread-moves, concepts/switching, concepts/fake-out
- 更新：concepts/turn-order、concepts/priority、concepts/trick-room、concepts/tailwind（相關頁面加入新頁連結）、index.md（新增「雙打博弈」區）；AGENTS.md 術語對照表新增 17 組譯名
- 補充（非 raw 來源）：守住優先度 +4 與連續使用成功率、佯攻、掩護招式優先度 +2 與憤怒粉的無效條件、招式威力與有效威力表、Lv.50 傷害公式與修正順序、群體修正判定時機、地震誤傷隊友、擊掌奇襲的數據／限制／無效條件
- 矛盾：無

## [2026-11-23] ingest | raw/weather-terrain-items.md
- 新增：concepts/weather, concepts/terrain, concepts/items
- 更新：concepts/team-rules、concepts/fake-out、concepts/priority（把「尚未 ingest」的 raw 引用改成連結到新頁）、concepts/spread-moves（相關頁面）、index.md（新增「環境控制與道具」區）；AGENTS.md 術語對照表新增 2 組譯名
- 補充（非 raw 來源）：沙暴扣血、雪天冰屬性防禦 ×1.5、天氣與場地持續 5／8 回合、天氣之戰、「位於地面上」的定義、電氣／青草／薄霧場地的附加效果、場地加成屬於修正威力、講究系鎖招、突擊背心不能用變化招式、生命寶珠反傷、氣勢披帶失效條件、各道具計算範例
- 矛盾：無

## [2026-11-23] ingest | raw/team-archetypes-and-key-pokemon.md
- 新增：archetypes/rain, archetypes/hard-trick-room, concepts/pokemon-flutter-mane, concepts/pokemon-incineroar
- 更新：concepts/fake-out、concepts/switching、concepts/terrain、concepts/trick-room、concepts/weather（把「尚未 ingest」的 raw 引用改成連結到新頁）、index.md（新增「寶可夢單卡」與「隊伍體系」）；AGENTS.md 術語對照表新增 9 組譯名
- 補充（非 raw 來源）：大嘴鷗、海豚俠、愛管侍、敗露球菇的屬性與種族值；海豚俠的變身條件；噴射拳和波動衝；古代活性的效果；各寶可夢的速度線；振翼髮對愛管侍的暗影球傷害計算；威嚇的減傷計算；拋下狠話；蘑菇孢子的無效條件
- 未建頁：大嘴鷗、海豚俠、愛管侍、敗露球菇的資料只寫在體系頁裡，沒有獨立單卡頁（raw 只有提到名字）
- 矛盾：
  - archetypes/rain：raw 寫海豚俠「在開局」就能施加巨大輸出壓力；LLM 認知是海豚俠必須先換下場一次才會變身 → 待查證

## [2026-11-23] fix | 譯名更正
- 「影子偷襲」的英文從 Sucker Punch 更正為 **Shadow Sneak**（幽靈屬性，優先度 +1）；Sucker Punch 的中文是「突襲」，另外登記進術語對照表
- 更新：AGENTS.md 術語對照表、concepts/priority（說法 B 的英文、優先度表、判定範例、「突襲的條件」那一條）、concepts/terrain、concepts/pokemon-flutter-mane（應對方式改寫：振翼髮怕幽靈和鋼屬性，惡屬性只是普通效果）
- 優先度數值不受影響（兩招都是 +1）；raw 原文「影子偷襲 +1」本身正確

## [2026-11-23] resolve | archetypes/rain
- 海豚俠開局施壓：採用說法 B（使用者確認）。海豚俠必須先換下場一次才會變成 Hero 形態，首發第一回合打不出高傷害；raw/team-archetypes-and-key-pokemon.md 的「在開局造成巨大輸出壓力」不採用
- 譯名：Zero to Hero 的中文確定為「全能變身」（使用者提供）
- 更新：archetypes/rain（核心組合表、運作邏輯、矛盾區塊狀態）、AGENTS.md 術語對照表、index.md 摘要

## [2026-11-23] lint | 全站健康檢查（20 頁：concepts 18、archetypes 2）
- A 連結與目錄：通過。0 個壞連結、0 個孤兒頁，index.md 和實際頁面完全一致。備註：pokemon-flutter-mane 只被 1 頁連入，連結偏弱
- B 來源與 log：通過。每頁都有頁尾來源、來源檔都存在，5 篇 raw 都已 ingest，每頁在 log 都有紀錄
- C 事實一致：通過。關鍵數值（速度線、回合數、優先度、各種倍率）在各頁一致；4 項矛盾都已解決
- D 格式與術語：frontmatter、範本章節、檔名都通過；「專有名詞第一次出現要附英文」約 45 處不合規（另有 2～3 處是腳本誤判）：
  - 開頭摘要句先用了專有名詞，英文到「定義」段才出現：weather、terrain、redirection、priority、archetypes/rain、archetypes/hard-trick-room、pokemon-flutter-mane、pokemon-incineroar
  - 專有名詞第一次只出現在「相關頁面」清單的說明裡：tailwind（守住）、spread-moves（生命寶珠）、vgc-format（道具不重複條款）
  - 內文其他地方漏附英文：items、team-rules、stat-calculation、turn-order、tournament-conduct、vgc-format、spread-moves、priority、pokemon-incineroar、archetypes/rain、archetypes/hard-trick-room
  - 譯名小差異：team-rules 用「隊伍完成登記（Team Check）」，術語表寫的是「隊伍登記」
- 狀態：只回報、尚未修正，等使用者決定處理方式

## [2026-11-23] fix | 處理 lint D 類問題
- 規則修訂（AGENTS.md §3、§7.3 D）：「第一次出現」從 H1 下方第一個 ## 章節開始算；開頭摘要句和「相關頁面」清單不算第一次出現。粗體小標題算正文，英文可以補在同一行
- 補英文（24 處，分布在 13 頁）：items、pokemon-flutter-mane、pokemon-incineroar、priority、stat-calculation、team-rules、tournament-conduct、turn-order、vgc-format、archetypes/hard-trick-room、archetypes/rain
- 譯名統一：team-rules「隊伍完成登記」→「隊伍登記（Team Check）完成後」；vgc-format「隊伍預覽選角」→「隊伍預覽（Team Preview）選角」
- 連結補強：turn-order 和 spread-moves 加上連到 pokemon-flutter-mane（連入從 1 頁增加到 3 頁），turn-order 也加上連到 pokemon-incineroar
- 複查結果：術語檢查 0 個問題，0 個壞連結

## [2026-11-23] fix | 使用者提供的機制補充（參考：神奇寶貝百科 wiki.52poke.com）
- concepts/terrain：薄霧場地
  - 補上「不會陷入混亂」。
  - 寫明薄霧場地**沒有**任何屬性增傷，不會提升妖精屬性招式。
  - 「增傷」一句改成只有電氣、青草、精神場地。
  - 常見誤區新增一條。
- concepts/protect：
  - 新增守住類團隊防禦招式：廣域防守（擋我方場地的群體招式）、快速防守（擋我方場地的先制招式）。
  - 新增守住類比較表、實戰用法。
  - 常見誤區「守住能保護隊友」補充改用廣域防守或快速防守。
- 連帶更新：
  - concepts/priority：優先度表 +3 加入兩招；防禦手段加上快速防守。
  - concepts/fake-out：無效情況與應對方式加上快速防守。
  - concepts/spread-moves：常見誤區加上廣域防守。
  - index.md 摘要。
  - AGENTS.md 術語對照表新增 3 組（廣域防守、快速防守、混亂）。
- 備註：廣域防守和快速防守的優先度 +3 是 LLM 補充，不是使用者提供的資訊。
- 影響簡報：deck.html 使用的證據卡 card-09（protect）、card-15（terrain）、card-13（fake-out）、card-08（priority）、card-11（spread-moves）已經過時，需要重跑 make-slides 才會反映

## [2026-11-23] fix | concepts/protect 說法統一
- 定義段補上「佯攻（Feint）除外，它能打破守住」。
- 比較表「幾乎所有對自己的攻擊」改成「對自己的攻擊（佯攻除外）」，讓定義段、比較表、實戰應用三處說法一致。
- 影響簡報：card-09 只寫「完全擋下」，沒有佯攻的例外；簡報目前沒有提到佯攻，所以內容沒有錯誤，下次重跑 make-slides 時 card-09 會一併更新。
