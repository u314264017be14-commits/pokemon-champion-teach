# 寶可夢 VGC 雙打對戰新手教學知識庫 — 總目錄

給準備參賽的新手：從賽制規則、控速、場地天氣到隊伍體系，循序建立雙打對戰的完整觀念。維護規範見 `AGENTS.md`。

## 核心機制（concepts/）

### 賽制與規則
- [[concepts/vgc-format]] — VGC 雙打賽制：2 對 2、帶 6 選 4、Lv.50、每回合 45 秒
- [[concepts/team-rules]] — 隊伍構築限制：道具不重複、物種不重複、登記後鎖定
- [[concepts/tournament-conduct]] — 賽場規範：禁止預印筆記、對局中筆記、斷線判定

### 數值基礎
- [[concepts/stat-calculation]] — Lv.50 能力值公式、努力值 4+8n 原則、速度速查表

### 控速與出手順序
- [[concepts/turn-order]] — 出手判定順序、實際速度計算、能力階級倍率
- [[concepts/tailwind]] — 順風：我方速度 ×2，持續 4 回合
- [[concepts/trick-room]] — 戲法空間：倒轉速度順序，持續 5 回合，優先度 −7
- [[concepts/priority]] — 招式優先度：比速度和戲法空間先判定、常見招式優先度表

### 雙打博弈
- [[concepts/protect]] — 守住：擋下攻擊、躲集火、拖回合；連續使用成功率 1/3 遞減；廣域防守擋群體招式、快速防守擋先制招式
- [[concepts/redirection]] — 掩護招式：看我嘛、憤怒粉吸引單體攻擊，吸不走群體招式
- [[concepts/spread-moves]] — 群體招式：雙打傷害 ×0.75、傷害公式與修正順序
- [[concepts/switching]] — 輪替：換人先於所有招式，攻擊由新上場的寶可夢承受
- [[concepts/fake-out]] — 擊掌奇襲：優先度 +3、讓目標畏縮、只限上場第一回合

### 環境控制與道具
- [[concepts/weather]] — 天氣：晴天和雨天的火／水 ×1.5／×0.5、沙暴岩石特防 ×1.5、雪天
- [[concepts/terrain]] — 場地：地面上的寶可夢對應屬性 ×1.3、精神場地擋先制招式、薄霧場地防異常與混亂（沒有增傷）
- [[concepts/items]] — 常見道具：講究系、突擊背心、生命寶珠、氣勢披帶與計算範例

### 寶可夢單卡
- [[concepts/pokemon-flutter-mane]] — 振翼髮：幽靈／妖精的高速特攻輸出手，附暗影球傷害計算
- [[concepts/pokemon-incineroar]] — 熾焰咆哮虎：火／惡的輪轉輔助，威嚇 + 擊掌奇襲 + 拋下狠話

## 隊伍體系（archetypes/）

- [[archetypes/rain]] — 雨天體系：大嘴鷗 + 海豚俠，水系招式 ×1.5；海豚俠要先換下一次才會變身
- [[archetypes/hard-trick-room]] — 重空間體系：愛管侍的精神場地 + 敗露球菇在戲法空間下用孢子控場
