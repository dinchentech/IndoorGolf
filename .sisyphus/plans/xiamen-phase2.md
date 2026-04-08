# ONEPPP 廈門項目第二階段：協議 + 小程序規格 + 招商影片

## TL;DR

> **Quick Summary**: 為 ONEPPP.TECH 廈門室內高爾夫+射擊模擬器加盟項目產出三份核心文件：設備租賃合作協議範本（簡中，完整可用）、基於納客系統的微信小程序配置規格書、60 秒招商短影片腳本（現有素材剪輯）。
> 
> **Deliverables**:
> - `deliverables/partnership-agreement.md` — 合作協議範本（簡體中文，完整合約）
> - `deliverables/mini-program-spec.md` — 自助小程序需求規格（納客系統配置文件）
> - `deliverables/video-script.md` — 60 秒招商影片腳本
> 
> **Estimated Effort**: Medium
> **Parallel Execution**: YES - 2 waves (3 parallel writing tasks + 1 verification)
> **Critical Path**: Task 1/2/3 (parallel) → Task 4 (consistency check)

---

## Context

### Original Request
用戶（ONEPPP.TECH 廠商，Annie Chen）在完成廈門加盟規劃方案 v1.1 後，選擇三個延伸方向繼續推進：合作協議範本、自助小程序需求規格、設備體驗影片腳本。這三項對應方案中「Phase 0：準備」的 P0 行動項目。

### Interview Summary
**Key Discussions**:
- 協議：簡中、2 年期、提前 1 月通知、違約金即押金、完整可用合約
- 小程序：基於納客現有模組配置、無年齡限制、時間+套餐計費
- 影片：60 秒、現有視頻剪輯、招商受眾

**Research Findings**:
- 現有方案 `.sisyphus/plans/xiamen-franchise-plan.md`（562 行）包含所有商業細節
- 招商簡介 `.sisyphus/plans/partner-pitch.md`（141 行）包含招商語言和賣點
- 納客系統（買斷 ¥10,000-15,000）已有小程序模組：預約、掃碼付款、會員、智能設備控制
- DTG3+ShootSim 保護器不能同時使用，影響預約邏輯設計
- 設備押金 ¥20,000/單元，合約結束設備無損全額退還
- ONEPPP 負擔巡店/客服/清潔

### Metis Review
**Identified Gaps** (addressed):
- 合約期限差異：方案寫 12 個月測試期 vs 用戶確認 2 年合約 → 合約以用戶確認的 2 年為準，方案的 12 個月是市場驗證指標期
- 合約需含法律免責聲明 → 已納入要求
- 小程序規格不應成為開發需求文件 → 明確限定為「配置規格」
- 影片腳本不應包含新拍攝指示 → 明確限定為「現有素材剪輯」
- 爭議解決條款需指定仲裁機構 → 默認廈門仲裁委員會
- 需處理邊界情況：加機、設備過時、轉讓、臨時客戶、超時等 → 已納入各任務要求

---

## Work Objectives

### Core Objective
產出三份完整的中文文件，支撐 ONEPPP 在廈門的合夥人招募和門店運營準備。

### Concrete Deliverables
- `deliverables/partnership-agreement.md` — 設備租賃合作協議範本
- `deliverables/mini-program-spec.md` — 納客小程序配置規格
- `deliverables/video-script.md` — 60 秒招商影片腳本

### Definition of Done
- [ ] 三份文件全部為簡體中文
- [ ] 協議包含完整合約條款（甲乙方、標的、期限、費用、責任、終止、違約、爭議解決、不可抗力）
- [ ] 小程序規格為納客系統配置文件（非開發需求文件）
- [ ] 影片腳本時間碼合計 = 60 秒
- [ ] 三份文件中的財務數字完全一致

### Must Have
- 所有財務數字必須與 `xiamen-franchise-plan.md` 一致
- 協議必須包含法律審閱免責聲明
- 小程序規格必須反映 DTG3+ShootSim 不能同時使用的預約限制
- 影片腳本必須包含明確的 CTA（行動呼籲）

### Must NOT Have (Guardrails)
- ❌ 協議中不得包含運營 SOP（只寫合約條款，不寫操作流程）
- ❌ 小程序規格不得包含線框圖、用戶故事、API 規格（只寫配置決策）
- ❌ 影片腳本不得包含新拍攝指示（只寫現有素材剪輯指令）
- ❌ 不得自創方案文件中未出現的商業條款
- ❌ 協議不得包含財務預測/損益模型
- ❌ 影片中不得提及競爭對手

---

## Verification Strategy (MANDATORY)

> **ZERO HUMAN INTERVENTION** - ALL verification is agent-executed. No exceptions.

### Test Decision
- **Infrastructure exists**: N/A（文件撰寫任務，非代碼）
- **Automated tests**: None（無代碼）
- **Framework**: N/A

### QA Policy
每個任務必須包含 agent-executed QA 場景。
Evidence saved to `.sisyphus/evidence/task-{N}-{scenario-slug}.{ext}`.

- **文件類任務**: Use Bash (grep/wc) - 搜索關鍵詞、統計字數、驗證結構
- **一致性驗證**: Use Bash (diff/grep) - 跨文件比對數字和術語

---

## Execution Strategy

### Parallel Execution Waves

```
Wave 1 (Start Immediately — ALL THREE IN PARALLEL):
├── Task 1: 合作協議範本 [ultrabrain]
├── Task 2: 小程序配置規格 [unspecified-high]
└── Task 3: 招商影片腳本 [writing]

Wave 2 (After Wave 1 — verification):
└── Task 4: 跨文件一致性驗證 [quick]

Wave FINAL (After ALL tasks):
├── Task F1: Plan compliance audit (oracle)
├── Task F2: Content quality review (unspecified-high)
├── Task F3: Cross-document QA (unspecified-high)
└── Task F4: Scope fidelity check (deep)
-> Present results -> Get explicit user okay

Critical Path: Task 1/2/3 (parallel) → Task 4 → F1-F4 → user okay
Parallel Speedup: ~60% faster than sequential
Max Concurrent: 3 (Wave 1)
```

### Dependency Matrix

| Task | Depends On | Blocks | Wave |
|------|-----------|--------|------|
| 1 (協議) | — | 4, F1-F4 | 1 |
| 2 (小程序) | — | 4, F1-F4 | 1 |
| 3 (影片) | — | 4, F1-F4 | 1 |
| 4 (一致性) | 1, 2, 3 | F1-F4 | 2 |
| F1-F4 | 4 | — | FINAL |

### Agent Dispatch Summary

- **Wave 1**: **3 tasks** — T1 → `ultrabrain`, T2 → `unspecified-high`, T3 → `writing`
- **Wave 2**: **1 task** — T4 → `quick`
- **FINAL**: **4 tasks** — F1 → `oracle`, F2 → `unspecified-high`, F3 → `unspecified-high`, F4 → `deep`

---

## TODOs

- [x] 1. 合作協議範本（設備租賃合作協議）

  **What to do**:
  - 撰寫一份完整可用的設備租賃合作協議，簡體中文
  - 合約結構需符合中國大陸設備租賃合同慣例
  - **必備章節**：
    1. 協議雙方（甲方 ONEPPP / 乙方 合夥人，含【填寫】欄位）
    2. 合作標的（DTG3 高爾夫模擬器 + ShootSim 射擊模擬器，含規格描述和保護器互斥限制）
    3. 合作期限：**2 年**，自設備安裝驗收之日起算
    4. 設備押金：**¥20,000/單元**，合約期滿且設備無損全額退還；退還時限 30 日
    5. 設備月租：**¥1,000-1,500/單元/月**（具體金額填寫欄位）
    6. 甲方責任：提供設備、首次安裝調試、遠端技術支援、**巡店員、遠端客服、清潔服務**
    7. 乙方責任：場地、裝修、電腦/投影機/螢幕機台等周邊設備（¥12,500/單元）、納客系統、證照辦理、水電網路、日常營運、行銷
    8. 設備維護：正常損耗甲方負責，人為損壞乙方承擔
    9. 提前終止：任一方提前 **1 個月** 書面通知；違約方沒收/雙倍返還押金
    10. 區域保護：同一社區 1km 內不設第二家
    11. 知識產權：設備及軟體知識產權歸甲方，乙方不得拆解/複製/反向工程
    12. 保密條款：雙方對商業信息保密
    13. 保險與責任：顧客人身安全由乙方負責（建議購買公眾責任險）；設備財產險由甲方負責
    14. 不可抗力條款
    15. 爭議解決：**廈門仲裁委員會** 仲裁
    16. 附件清單：設備清單、驗收確認書
    17. 簽章頁
  - 邊界情況處理：
    - 增加單元：需簽訂補充協議
    - 設備升級：甲方有義務提供同等或更優設備
    - 合約轉讓：未經甲方書面同意不得轉讓
    - 逾期付款：超過 15 日可加收滯納金；超過 60 日甲方有權終止
    - 部分退還單元：需雙方協商簽訂補充協議
    - 續約：到期前 60 日雙方協商續約條件
  - **文件開頭加入法律免責聲明**：「本協議範本僅供參考，建議在簽署前諮詢專業法律人士審閱。」

  **Must NOT do**:
  - ❌ 不得包含運營 SOP（操作流程、響應時間 SLA、排班表等）
  - ❌ 不得包含財務預測或損益模型
  - ❌ 不得使用繁體中文
  - ❌ 不得自創方案文件中未出現的商業條款

  **Recommended Agent Profile**:
  - **Category**: `ultrabrain`
    - Reason: 法律合同撰寫需要嚴謹的邏輯推理、精確的語言表達、和對 PRC 合同法慣例的深度理解
  - **Skills**: []
    - 無適用技能（寫文件，非代碼/瀏覽器/Git 任務）

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 1 (with Tasks 2, 3)
  - **Blocks**: Task 4 (一致性驗證)
  - **Blocked By**: None (can start immediately)

  **References** (CRITICAL):

  **Pattern References** (existing documents to follow):
  - `.sisyphus/plans/xiamen-franchise-plan.md:86-107` — 商業模式和合作條款（角色分工表、合作模式表），**合約的核心商業條款全部從這裡提取**
  - `.sisyphus/plans/xiamen-franchise-plan.md:234-265` — 成本結構（ONEPPP 設備投入表、合夥人投入明細表），**設備清單和金額**
  - `.sisyphus/plans/xiamen-franchise-plan.md:218-231` — 人力配置（ONEPPP 負擔的巡店/客服/清潔），**甲方服務責任**
  - `.sisyphus/plans/xiamen-franchise-plan.md:20-57` — 產品規格（DTG3 和 ShootSim 完整規格 + 保護器互斥限制），**設備描述條款**
  - `.sisyphus/plans/xiamen-franchise-plan.md:327-337` — 證照與法規，**乙方義務參考**

  **WHY Each Reference Matters**:
  - 行 86-107：合約的甲乙方權利義務、月租金額、押金金額、維修分工、退出條件全部來自這裡
  - 行 234-265：合夥人投入明細表列出了周邊設備金額（電腦 ¥4,500、投影機 ¥4,500、螢幕機台 ¥3,500），需要在合約的「乙方責任」條款中引用
  - 行 218-231：ONEPPP 負擔巡店/客服/清潔的具體內容和成本，用於甲方責任條款
  - 行 20-57：DTG3 和 ShootSim 的完整規格，用於合約「合作標的」條款中的設備描述
  - 行 327-337：法規要求，乙方需辦理的證照清單

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 合約結構完整性驗證
    Tool: Bash (grep)
    Preconditions: deliverables/partnership-agreement.md 已生成
    Steps:
      1. grep -c "第.*条" deliverables/partnership-agreement.md — 統計條款數量
      2. grep "甲方" deliverables/partnership-agreement.md — 確認甲方出現
      3. grep "乙方" deliverables/partnership-agreement.md — 確認乙方出現
      4. grep "20,000\|20000\|两万\|贰万" deliverables/partnership-agreement.md — 確認押金金額
      5. grep "仲裁" deliverables/partnership-agreement.md — 確認爭議解決條款
      6. grep "不可抗力" deliverables/partnership-agreement.md — 確認不可抗力條款
      7. grep "仅供参考\|咨询.*法律" deliverables/partnership-agreement.md — 確認法律免責聲明
    Expected Result: 條款數量 ≥ 15；甲方/乙方均出現多次；押金金額出現；仲裁/不可抗力/免責聲明均存在
    Failure Indicators: 任一關鍵詞未找到；條款數量 < 15
    Evidence: .sisyphus/evidence/task-1-agreement-structure.txt

  Scenario: 禁止內容驗證（反面測試）
    Tool: Bash (grep)
    Preconditions: deliverables/partnership-agreement.md 已生成
    Steps:
      1. grep -i "SOP\|排班\|轮班\|响应时间\|SLA" deliverables/partnership-agreement.md — 不應出現運營 SOP
      2. grep -i "月利润\|回本\|IRR\|NPV\|投资回报" deliverables/partnership-agreement.md — 不應出現財務預測
      3. python3 -c "import sys; text=open('deliverables/partnership-agreement.md').read(); tc=[c for c in text if '\u4e00'<=c<='\u9fff']; print('OK' if all(ord(c)<0xF900 for c in tc) else 'FAIL')" — 檢查無繁體特有字
    Expected Result: 步驟 1-2 無匹配結果；步驟 3 輸出 OK
    Failure Indicators: 任一搜索返回匹配結果
    Evidence: .sisyphus/evidence/task-1-agreement-forbidden.txt
  ```

  **Commit**: YES
  - Message: `docs(agreement): add partnership agreement template (合作協議範本)`
  - Files: `deliverables/partnership-agreement.md`

- [x] 2. 自助小程序需求規格（納客系統配置文件）

  **What to do**:
  - 撰寫一份基於納客管理系統的微信小程序配置規格書，簡體中文
  - 這是「配置規格」，不是「軟體開發需求」— 基於納客現有功能模組進行客製化配置
  - **必備章節**：
    1. 概述：項目背景、小程序定位、目標用戶
    2. 預約模塊配置：
       - 時段設置：每 30 分鐘一個時段，營業時間 08:00-24:00
       - 單元選擇：顯示可用單元、已預約狀態
       - 模式選擇：高爾夫 / 射擊 / 套餐（1.5 小時高爾夫+射擊組合）
       - **關鍵限制**：同一單元同一時段只能選一種模式（DTG3 和 ShootSim 保護器不能同時使用）
       - 臨時客戶（Walk-in）處理：到店掃碼，顯示當前可用時段，即時預約即時使用
       - 超時處理：時間結束前 5 分鐘推送提醒，可在線續費延時
    3. 計費配置：
       - 按時間計費：工作日 ¥60-80/小時（高爾夫）、¥30-50/30分鐘（射擊）；週末 ¥80-100/小時、¥40-60/30分鐘
       - 套餐計費：高爾夫+射擊套餐 ¥100-150/1.5小時
       - 會員卡：10 次卡 ¥500-600、月卡 ¥800-1,200
       - 儲值優惠：充 500 送 50、充 1000 送 150
       - 包場/團建：¥200-300/2小時/單元
       - 工作日/週末自動切換定價
    4. 付款配置：微信支付（必須）、支付寶（如納客支持）、儲值卡扣款
    5. 會員管理配置：
       - 等級：普通/銀卡/金卡
       - 積分規則
       - 優惠券/折扣設置
    6. 智能設備控制配置：
       - 門鎖：預約到點自動開鎖，離店自動上鎖
       - 燈光：開台自動亮燈，結束自動關燈
       - 冷氣：開台自動開，結束自動關
    7. 老闆助手 APP 配置：遠端監控營收/會員/預約
    8. 待確認項（需與納客銷售確認的功能）

  **Must NOT do**:
  - ❌ 不得包含線框圖、UI 設計稿、用戶故事
  - ❌ 不得包含 API 規格、資料庫結構、技術架構圖
  - ❌ 不得重新設計納客的 UX 流程
  - ❌ 不得包含需要從零開發的自定義功能

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
    - Reason: 產品配置規格需要清晰的結構、領域知識理解、和對納客系統能力邊界的把控，但不需要超高推理
  - **Skills**: []
    - 無適用技能（配置文件撰寫，非代碼/瀏覽器/Git 任務）

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 1 (with Tasks 1, 3)
  - **Blocks**: Task 4 (一致性驗證)
  - **Blocked By**: None (can start immediately)

  **References** (CRITICAL):

  **Pattern References**:
  - `.sisyphus/plans/xiamen-franchise-plan.md:189-216` — 納客管理系統功能表 + 顧客完整流程（7 步），**小程序配置的功能範圍和流程依據**
  - `.sisyphus/plans/xiamen-franchise-plan.md:269-279` — 定價策略（所有價格和套餐），**計費配置的數字來源**
  - `.sisyphus/plans/xiamen-franchise-plan.md:52-56` — DTG3+ShootSim 保護器互斥限制，**預約邏輯的關鍵技術約束**
  - `.sisyphus/plans/xiamen-franchise-plan.md:112-118` — 標準單元規格和配置，**單元描述**

  **WHY Each Reference Matters**:
  - 行 189-216：納客系統的完整功能列表（預約/付款/計時/門鎖/燈光/冷氣/遠端監控/小程序），7 步顧客流程是配置的骨架
  - 行 269-279：所有定價（散客/套餐/次卡/月卡/儲值/包場），直接對應計費配置
  - 行 52-56：「保護器不能同時插在電腦上」的技術限制，決定了預約模塊必須限制同一單元同一時段只能選一種模式
  - 行 112-118：每個單元的設備配置（共用一台電腦/投影機/布幕），影響單元顯示邏輯

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 配置完整性驗證
    Tool: Bash (grep)
    Preconditions: deliverables/mini-program-spec.md 已生成
    Steps:
      1. grep -c "预约\|預約" deliverables/mini-program-spec.md — 預約模塊被提及
      2. grep "60.*80\|80.*100" deliverables/mini-program-spec.md — 工作日/週末定價出現
      3. grep "门锁\|灯光\|冷气\|空调" deliverables/mini-program-spec.md — 智能設備控制
      4. grep -i "保护器\|dongle\|互斥\|不能同时" deliverables/mini-program-spec.md — DTG3+ShootSim 限制
      5. grep "微信支付\|微信Pay\|WeChat Pay" deliverables/mini-program-spec.md — 付款方式
      6. grep "储值\|充.*送" deliverables/mini-program-spec.md — 儲值優惠
    Expected Result: 所有搜索均有匹配結果
    Failure Indicators: 任一搜索無匹配
    Evidence: .sisyphus/evidence/task-2-miniprogram-completeness.txt

  Scenario: 禁止內容驗證（反面測試）
    Tool: Bash (grep)
    Preconditions: deliverables/mini-program-spec.md 已生成
    Steps:
      1. grep -i "wireframe\|线框\|UI.*设计\|用户故事\|user story" deliverables/mini-program-spec.md — 不應出現 UI 設計
      2. grep -i "API\|endpoint\|数据库\|database\|schema\|REST\|GraphQL" deliverables/mini-program-spec.md — 不應出現技術架構
    Expected Result: 步驟 1-2 無匹配結果
    Failure Indicators: 任一搜索返回匹配結果
    Evidence: .sisyphus/evidence/task-2-miniprogram-forbidden.txt
  ```

  **Commit**: YES
  - Message: `docs(mini-program): add NaKe mini-program config spec (小程序需求規格)`
  - Files: `deliverables/mini-program-spec.md`

- [x] 3. 招商影片腳本（60 秒設備體驗短影片）

  **What to do**:
  - 撰寫一份 60 秒招商短影片的剪輯腳本，簡體中文
  - **素材**：僅使用現有視頻素材（不拍新片）
  - **受眾**：潛在合夥人（招商，非終端消費者）
  - **平台**：抖音 + 微信視頻號
  - **格式建議**：9:16 竖屏（抖音/視頻號原生格式）
  - **腳本結構**（每段標注時間碼 + 畫面描述 + 字幕/文字疊層 + 音效/背景音樂指示）：
    1. 開場吸引（0:00-0:08）：痛點切入 — 「你有沒有想過開一家不用僱人的店？」
    2. 設備展示（0:08-0:25）：DTG3 高爾夫 + ShootSim 射擊的體驗畫面
    3. 商業亮點（0:25-0:42）：半無人經營、低成本、高回報的核心數字
    4. 合作模式（0:42-0:52）：設備月租、不用買設備、人力全包
    5. CTA 行動呼籲（0:52-0:60）：聯繫方式（微信 dinchen-annie）+ 「掃碼了解合作詳情」
  - **核心賣點**（從 partner-pitch.md 提取）：
    - 廈門首家高爾夫+射擊複合體驗店
    - 半無人自助經營，人力全包
    - 設備不用買，月租 ¥1,000-1,500
    - 損益平衡僅需日均 2.4 小時/單元
    - 8-13 個月回本
  - **語調**：商務專業但不沉悶，有吸引力，適合潛在投資者
  - 腳本需包含：每段的素材類型建議（如「使用高爾夫揮桿慢動作畫面」「使用射擊激光追蹤畫面」），以及當某類素材不可用時的替代方案（文字卡、動畫疊層）

  **Must NOT do**:
  - ❌ 不得包含新拍攝指示（燈光設置、拍攝角度、演員選角等）
  - ❌ 不得提及競爭對手
  - ❌ 不得使用消費者行銷語調（這是 B2B 招商，不是 C 端推廣）
  - ❌ 腳本總時長不得超過 60 秒

  **Recommended Agent Profile**:
  - **Category**: `writing`
    - Reason: 創意內容撰寫，需要精準的文案功力和影片節奏把控
  - **Skills**: []
    - 無適用技能（影片腳本，非代碼/瀏覽器/Git 任務）

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 1 (with Tasks 1, 2)
  - **Blocks**: Task 4 (一致性驗證)
  - **Blocked By**: None (can start immediately)

  **References** (CRITICAL):

  **Pattern References**:
  - `.sisyphus/plans/partner-pitch.md:1-141` — **整份招商簡介**，影片腳本的核心內容來源（賣點、數字、合作條件）
  - `.sisyphus/plans/xiamen-franchise-plan.md:73-83` — 市場機會和品牌成本對比，**「為什麼是這個生意」的數據支撐**
  - `.sisyphus/plans/xiamen-franchise-plan.md:546-551` — 給合夥人的關鍵數字（損益平衡 2.4 小時、回本 8-13 個月等），**影片中的核心數字**
  - `.sisyphus/plans/xiamen-franchise-plan.md:555-562` — 聯絡資訊（Annie Chen、微信 dinchen-annie），**CTA 的聯絡方式**

  **WHY Each Reference Matters**:
  - partner-pitch.md：整份文件就是為招商設計的，包含所有賣點和合作條件，影片腳本的文案直接從這裡提煉
  - 行 73-83：市場數據（廈門唯一、複合業態空白、CG3D 免年費優勢），用於「商業亮點」段
  - 行 546-551：損益平衡 2.4 小時、回本 8-13 個月、人力零負擔等，這些是最有說服力的數字
  - 行 555-562：Annie Chen 的微信/Email/Line 聯繫方式，用於 CTA 段

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 腳本時長和結構驗證
    Tool: Bash (grep + python)
    Preconditions: deliverables/video-script.md 已生成
    Steps:
      1. grep -E "0:[0-5][0-9]" deliverables/video-script.md — 確認有時間碼標記
      2. grep "0:00\|0:52\|0:60\|1:00" deliverables/video-script.md — 確認有開頭和結尾時間碼
      3. grep -i "dinchen-annie\|微信" deliverables/video-script.md — 確認 CTA 包含聯繫方式
      4. grep "2.4\|两小时\|2小时" deliverables/video-script.md — 確認核心數字出現
      5. grep -c "素材\|画面\|镜头\|剪辑\|叠" deliverables/video-script.md — 確認有素材/剪輯指示
    Expected Result: 所有搜索均有匹配結果；素材指示出現次數 ≥ 5
    Failure Indicators: 時間碼缺失；CTA 聯繫方式缺失；無剪輯指示
    Evidence: .sisyphus/evidence/task-3-video-structure.txt

  Scenario: 禁止內容驗證（反面測試）
    Tool: Bash (grep)
    Preconditions: deliverables/video-script.md 已生成
    Steps:
      1. grep -i "拍摄\|拍攝\|灯光设置\|布光\|摄影师\|演员\|选角" deliverables/video-script.md — 不應出現新拍攝指示
      2. grep -i "胖达\|如歌\|GOLFZON\|竞品\|竞争" deliverables/video-script.md — 不應出現競爭對手
    Expected Result: 步驟 1-2 無匹配結果
    Failure Indicators: 任一搜索返回匹配結果
    Evidence: .sisyphus/evidence/task-3-video-forbidden.txt
  ```

  **Commit**: YES
  - Message: `docs(video): add 60s recruitment video script (招商影片腳本)`
  - Files: `deliverables/video-script.md`

- [x] 4. 跨文件一致性驗證

  **What to do**:
  - 讀取三份已完成的交付物，逐項驗證一致性：
    1. **財務數字**：押金 ¥20,000/單元、月租 ¥1,000-1,500、周邊設備 ¥12,500、所有定價
    2. **設備描述**：DTG3 和 ShootSim 的名稱、規格、保護器限制
    3. **責任分工**：甲方（ONEPPP）和乙方（合夥人）的責任不矛盾
    4. **術語一致**：同一概念使用相同中文術語
  - 發現差異 → 直接修正 → 記錄修正內容
  - 生成一致性報告 `deliverables/consistency-check.md`

  **Must NOT do**:
  - ❌ 不得修改任何商業條款內容（只修正不一致的數字/術語）
  - ❌ 不得添加新內容

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: 比對和驗證任務，邏輯簡單但需要仔細
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: NO (Sequential)
  - **Parallel Group**: Wave 2
  - **Blocks**: F1-F4
  - **Blocked By**: Tasks 1, 2, 3

  **References**:

  **Source of Truth**:
  - `.sisyphus/plans/xiamen-franchise-plan.md` — 所有數字的最終權威來源
  - `deliverables/partnership-agreement.md` — 待驗證文件 1
  - `deliverables/mini-program-spec.md` — 待驗證文件 2
  - `deliverables/video-script.md` — 待驗證文件 3

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 一致性報告存在且完整
    Tool: Bash (grep)
    Preconditions: deliverables/consistency-check.md 已生成
    Steps:
      1. test -f deliverables/consistency-check.md && echo "EXISTS" || echo "MISSING"
      2. grep -c "20,000\|20000" deliverables/consistency-check.md — 押金數字被檢查
      3. grep "一致\|PASS\|通过\|OK" deliverables/consistency-check.md — 有驗證結果
    Expected Result: 文件存在；押金數字被提及；有通過/一致性判定
    Failure Indicators: 文件不存在；無驗證結果記錄
    Evidence: .sisyphus/evidence/task-4-consistency.txt
  ```

  **Commit**: YES (if corrections made)
  - Message: `docs: fix cross-document inconsistencies`
  - Files: affected deliverable files + `deliverables/consistency-check.md`

---

## Final Verification Wave (MANDATORY — after ALL implementation tasks)

> 4 review agents run in PARALLEL. ALL must APPROVE. Present consolidated results to user and get explicit "okay" before completing.

- [x] F1. **Plan Compliance Audit** — `oracle`
  Read the plan end-to-end. For each "Must Have": verify implementation exists (read file, grep content). For each "Must NOT Have": search deliverables for forbidden patterns — reject with file:line if found. Check evidence files exist in .sisyphus/evidence/. Compare deliverables against plan.
  Output: `Must Have [N/N] | Must NOT Have [N/N] | Tasks [N/N] | VERDICT: APPROVE/REJECT`

- [x] F2. **Content Quality Review** — `unspecified-high`
  Review all three deliverables for: language quality (Simplified Chinese, no Traditional characters), logical consistency, completeness per acceptance criteria, professional tone. Check for AI slop: excessive filler, repetitive phrasing, vague language.
  Output: `Agreement [PASS/FAIL] | MiniProgram [PASS/FAIL] | VideoScript [PASS/FAIL] | VERDICT`

- [x] F3. **Cross-Document QA** — `unspecified-high`
  Verify every financial figure (¥20,000 deposit, ¥1,000-1,500 monthly rent, ¥12,500 peripherals, etc.) appears identically across all documents that reference it. Verify equipment descriptions are consistent. Verify party responsibilities don't contradict. Save comparison matrix to `.sisyphus/evidence/final-qa/consistency-matrix.md`.
  Output: `Figures [N/N consistent] | Terms [N/N consistent] | Responsibilities [MATCH/CONFLICT] | VERDICT`

- [x] F4. **Scope Fidelity Check** — `deep`
  For each task: read acceptance criteria, read actual deliverable. Verify 1:1 — everything in spec was built (no missing), nothing beyond spec was built (no creep). Check "Must NOT do" compliance. Flag: operations SOP in agreement, wireframes in mini-program spec, new-shoot instructions in video script.
  Output: `Tasks [N/N compliant] | Scope Creep [CLEAN/N issues] | VERDICT`

---

## Commit Strategy

- **Wave 1** (3 atomic commits, one per deliverable):
  - `docs(agreement): add partnership agreement template (合作協議範本)` — `deliverables/partnership-agreement.md`
  - `docs(mini-program): add NaKe mini-program config spec (小程序需求規格)` — `deliverables/mini-program-spec.md`
  - `docs(video): add 60s recruitment video script (招商影片腳本)` — `deliverables/video-script.md`
- **Wave 2** (if corrections made):
  - `docs: fix cross-document inconsistencies` — affected files

---

## Success Criteria

### Final Checklist
- [ ] 三份文件全部為簡體中文
- [ ] 協議包含所有 PRC 租賃合同必備條款
- [ ] 協議合約期限 = 2 年
- [ ] 小程序規格為納客配置文件（非開發需求）
- [ ] 小程序規格包含 DTG3+ShootSim 互斥預約規則
- [ ] 影片腳本時間碼合計 = 60 秒
- [ ] 三份文件財務數字完全一致
- [ ] 所有 "Must Have" 已交付
- [ ] 所有 "Must NOT Have" 未出現
