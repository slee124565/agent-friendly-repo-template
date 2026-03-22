# Agent-Friendly Repository By Example

`A publishable walkthrough based on my real workspace, myBrainFood.`

這份文件不是模板，而是一份公開版案例導讀。

如果你是第一次接觸 agent-friendly repo，建議不要先急著讀 `templates/`。先看這份 guide，理解 `myBrainFood` 怎麼把真實工作流拆成入口文件、結構抽象層、local guides 與實際內容區；之後再回頭看 starter kit，你會更容易知道每份文件為什麼要這樣設計。

對外部讀者來說，這是一份案例導讀。

對想打造自己 repo 的新手來說，這也是一份「先理解，再動手」的橋接文件。

這份 guide 服務兩種讀者：

- 想理解 agent-friendly repo 為什麼需要這樣分工的人
- 想從真實案例出發，再打造自己簡易版 repo 的新手

閱讀時也先記得一點：這裡出現的目錄名稱，例如 `_ideas/`、`_todos/`、`archive/`、`docs/`、`prompts/`，都是 `myBrainFood` 的實際命名，用來幫助你理解結構角色；它們不是硬性規格。若你要在自己的 repo 採用這套設計，可以依團隊語言、工作流與既有慣例，自行調整名稱，只要底層角色分工仍然清楚即可。

## 先看哪四份 root 文件

在 `myBrainFood` 裡，root 層目前拆成四種不同角色：

- `README.md`
  給人與 agent 的 repo overview，回答這個 workspace 大致有哪些區塊
- `AGENTS.md`
  給 agent 的入口檔，回答先讀哪裡、遇到哪類任務去哪裡找規則
- `ARCHITECTURE.md`
  給結構判斷使用，回答內容怎麼流轉、哪裡是 source-of-truth、什麼該升格
- `docs/README.md`
  給 `docs/` 自己使用，回答什麼該進 `docs/`

這四份文件共同構成這個 publish repo 的理解起點。也就是說，這組 starter templates 不是先從抽象欄位長出來，而是先從這四種真實分工倒推出來的。

這也是這個案例最想分享的核心經驗：當 repo 同時承接工作流、研究、輸出與 agent 協作時，單一 root README 很快就會超載。

## `myBrainFood` 的真實分區長什麼樣

如果把 `myBrainFood` 當成一個工作系統，而不是檔案倉庫，幾個高頻區塊很容易看出不同角色：

- `_ideas/`
  接住還在定義問題、整理假設、還沒決定是否要長期追蹤的主題
- `_todos/`
  承接 active context，也就是目前正在推進的任務、研究與規劃
- `archive/`
  保存已完成、已退役但仍值得回看的歷史任務；在 `myBrainFood` 裡，completed task 現在預設改成 repo 內 thin pointer + GitHub release snapshot，而不是保留完整 historical tree
- `docs/`
  沉澱穩定規則、方法論與 workflow
- `prompts/`
  保存可跨任務重用的 prompt
- `tools/`
  保存可執行工具
- `publishes/`
  保存已發表專案的 subtree 鏡像與索引，不預設是 active workspace 的 source-of-truth

這就是這套設計反覆出現幾個概念的來源：

- workflow state
- active context vs historical context
- reusable assets
- stable docs
- external sync boundary

它們不是理論先行，而是為了解釋這些真實目錄長期共存時的不同角色。

## 一個最重要的結構判斷：active context 與 historical context

`myBrainFood` 最核心的結構判斷，不是副檔名，也不是內容主題，而是內容目前處在哪個工作狀態。

最典型的例子就是：

- `_todos/` 是 active context
- `archive/` 是 historical context

對 completed task，`myBrainFood` 又再往前走一步：主 workspace 只保留 thin pointer，完整歷史樹改由 Git tag + GitHub release snapshot 承擔。這能降低 historical materials 和 active tool / prompt 發生關鍵字碰撞的機率。

這個判斷不是口號，而是直接影響接手與 re-entry 的真實閱讀順序。若你要知道「現在正在做什麼」，應該先看 active context，而不是先翻 archive 或執行產物。

這也是為什麼一個 agent-friendly repo 不只是把檔案分類好，而是要讓 source-of-truth 順序可預測。

## 為什麼需要 `ARCHITECTURE.md`

只靠 `README.md`，你通常能知道 repo 有哪些區塊；但你不一定能判斷：

- 一份內容應該放 `_ideas/` 還是 `_todos/`
- 一份 task 結果什麼時候該沉澱到 `docs/`
- `prompts/` 與 task 內的一次性 prompt 草稿怎麼分
- `publishes/` 為什麼不是預設 active source-of-truth

這些問題在真實 workspace 裡都很實際，所以 `ARCHITECTURE.md` 在這裡不是補充說明，而是結構抽象層。它的工作是把分區模型、內容生命週期與 source-of-truth 邊界講清楚。

## 什麼時候不是寫進 `docs/`

很多 repo 的 `docs/` 會變成「不知道放哪裡就先丟進去」的區域，但 `myBrainFood` 刻意避免這件事。

真實分工是：

- 若內容仍依賴單一 task 脈絡，先留在 task 區
- 若內容只是單一 prompt 草稿，先留在任務脈絡，而不是直接升到共用區
- 若內容主要是工具，應進 `tools/`
- 只有當內容已成為 repo-level 長期規則、方法論或 workflow，才沉澱到 `docs/`

這也是為什麼這個 publish repo 沒把 `docs/README.md` 當成最小必備，而是放成 optional template。對第一次打造 agent-friendly repo 的新手來說，先把 root 三件套分工做好，比先長出一個空的 `docs/` 更重要。

## 真實案例怎麼幫助理解 starter kit

如果你只看模板，很容易把它們當成語句樣板。

這份 guide 的目的，是把 starter kit 背後的結構判斷綁回真實案例。它想幫你看到：

- 為什麼 root `README.md` 與 `AGENTS.md` 不該混成一份 giant instruction file
- 為什麼 `ARCHITECTURE.md` 應該獨立存在，而不是只當 README 的附錄
- 為什麼 active context / historical context 的界線能直接降低接手成本
- 為什麼 completed task 的歷史不一定要繼續以完整可搜尋樹留在主 workspace
- 為什麼 `docs/` 與 local guides 應該在 repo 成熟後再出現

換句話說，這些模板的價值不只是「可以複製」，而是「每一份文件都有明確理由存在」。

## 這套設計實際能支撐什麼提示詞

如果你想快速理解 agent-friendly repo 到底有什麼實際價值，最好的方式不是先讀抽象原則，而是直接看幾種真實提問。

下面這些 prompt，代表 reader 或 agent 在實際工作中很可能會提出的問題。這些問題之所以能被穩定回答，前提就是 repo 已經把入口、source-of-truth、workflow pointer 與 local guide 設計清楚。

### 1. 初次進 repo

```text
你是第一次進入這個 repo。請告訴我這個 repo 是做什麼用的，有哪些主要工作區域，以及我如果要找目前進行中的任務應該去哪裡看。
```

這個例子在驗證：

- root 入口是否可預測
- `AGENTS.md` 與 `README.md` 是否分工清楚
- reader 是否能被正確導向 active context，而不是歷史區或 execution artifacts

### 2. 找目前的權威來源

```text
幫我找出這個主題目前的執行狀態與下一步待做事項。
```

這個例子在驗證：

- repo 是否有清楚的 active context
- `archive/` 是否不會被誤當成當前 source-of-truth
- task 目錄內是否已有足夠的 state artifact 可供接手

### 3. 只找長期有效規則

```text
幫我整理這個 repo 目前有哪些長期有效的規則與方法論文件，以及它們分別在哪裡。
```

這個例子在驗證：

- `docs/` 是否真的承接長期規則
- execution artifacts 是否能被 lazy access
- root 文件是否有把 reader 正確導向 `docs/`

### 4. 進入特定主題工作區

```text
幫我找出這個 repo 裡關於某個特定工作流的資料，以及目前狀態。
```

這個例子在驗證：

- reader 是否會先從 root 入口找方向
- 進入子目錄後，是否能跟著 local `README.md` / `AGENTS.md`
- repo 是否有足夠的次級入口，避免深入後迷路

### 5. 判斷哪些規則只是慣例，哪些有強制力

```text
這個 repo 裡哪些規則是被強制執行的，哪些只是文件治理慣例？
```

這個例子在驗證：

- repo 的 guardrail 狀態是否可見
- 文件是否有把「正式 enforcement」和「治理慣例」分清楚
- agent 是否能如實回報，而不是自行腦補不存在的機制

### 6. 接手長任務並留下可恢復狀態

```text
幫我整理這個月某個主題的執行進度摘要，包含已完成、進行中、待啟動，以及下一步建議。這份摘要需要能被下一次的 session 繼續使用。
```

這個例子在驗證：

- repo 是否支援長任務狀態管理
- task contract 是否足夠清楚
- agent 是否不只回答問題，還知道把 state 留回正確的 task 位置

### 7. 跟隨 workflow pointer 執行工作

```text
我有一篇新聞連結要分析，請告訴我應該用什麼流程處理，並幫我開始執行。
```

這個例子在驗證：

- root `AGENTS.md` 是否真的提供 workflow pointer
- `docs/` 是否有對應流程文件
- agent 是否會先找既有流程，而不是每次重新發明做法

如果一個 repo 能穩定支撐這些提問，就代表它不只是「有很多說明文件」，而是已經具備可預測入口、可操作的 source-of-truth、可跟隨的流程入口，以及可接續的任務狀態設計。

## 如果你想打造自己的簡易版

如果你不想照搬整個 `myBrainFood`，最小可以先採用：

- 一份 root `README.md`
- 一份 root `AGENTS.md`
- 一份 root `ARCHITECTURE.md`

這三份文件已經足夠建立：

- overview
- navigation
- structure and source-of-truth rules

之後再依你的 repo 成長情況，補上：

- `docs/`
- `docs/README.md`
- `docs/archive-release-policy.md`
- deeper local guides
- workflow docs
- task contracts

這也是這個 publish repo 裡 `templates/` 的定位：不是把 `myBrainFood` 全部複製出去，而是提供一組讓新手能先動手做出簡易版的 starter kit。

## 建議閱讀順序

如果你想真正用這個 repo 開始動手，建議這樣讀：

1. 先讀這份 guide，理解真實案例與設計理由
2. 再看 `templates/ROOT-README.md`
3. 再看 `templates/AGENTS.md`
4. 再看 `templates/ARCHITECTURE.md`
5. 若你的 repo 已開始累積穩定 workflow，再看 `templates/docs-README.optional.md`
6. 若 completed task 的歷史已開始干擾 active 導航，再看 `templates/archive-release-policy.optional.md`

## 這份 publish guide 的核心主張

這個 repo 想分享的，不是「我有幾個模板檔」，而是：

- 一個 agent-friendly repo 應該先把入口與邊界講清楚
- 最小可行版本不需要一開始就複製整個複雜 workspace
- 真正有用的模板，應該能回到真實 workspace 中解釋自己為什麼存在

先有真實案例，再有 starter kit；這就是這個 publish repo 的核心設計。

## 靈感來源

這份 guide 與 starter kit 的方向，受到 OpenAI 文章 `Harness engineering: leveraging Codex in an agent-first world` 的啟發。

這裡借用的核心概念很簡單：把 `AGENTS.md` 視為 map，而不是 encyclopedia，並讓結構化的 repository knowledge 成為真正的 system of record。

官方原始連結：

- OpenAI, `Harness engineering: leveraging Codex in an agent-first world`
  https://openai.com/index/harness-engineering/
