# 員林好吃好玩 LLM Wiki Agent 規範指令 (AGENTS.md)

本檔案為「員林好吃好玩 LLM Wiki」的架構規範與維護指令（Schema）。作為 Agent，你必須嚴格遵守以下原則，維護 `wiki/` 目錄下的所有 Markdown 檔案。

---

## 1. 核心維護哲學 (Core Philosophy)

1. **增量編譯 (Incremental Compilation)**：當新資料傳入時，不要只是做簡單的片段檢索（RAG），而是將新資訊消化後提煉並整合進現有的實體（Entities）、主題（Topics）與索引中。
2. **唯讀原始資料 (Immutable Raw Sources)**：`raw/` 資料夾內的任何檔案均為權威來源，僅可讀取，絕對不可更動或刪除。
3. **Agent 獨佔 Wiki 寫入 (Agent Ownership)**：`wiki/` 資料夾內的內容完全由你維護。每次新增或更動資料，均須自動更新交叉連結、索引 `wiki/index.md` 及日誌 `wiki/log.md`。
4. **知識連鎖效應 (Compounding Knowledge)**：優質的查詢結果（如行程規劃、特色比較表）應自動歸檔至 `wiki/syntheses/`，讓歷史查詢成為未來知識庫的一部分。

---

## 2. Frontmatter 與標籤規範 (Frontmatter & Metadata Schema)

所有在 `wiki/entities/` 與 `wiki/topics/` 建立的 Markdown 檔案，必須在頂部包含標準 YAML Frontmatter。

---

## 3. 三大核心工作流程 (Workflows)

### 3.1 導入資料流程 (Ingest Workflow)
當使用者在 `raw/` 放遞新檔案或在對話中提供新的店家/景點筆記時，執行以下步驟：
1. **讀取與分析**：擷取關鍵實體、地址、營業時間、特色必點、評語與價格。
2. **建立/更新實體頁面 (`wiki/entities/`)**：補充或建立實體檔，使用 `[[檔名]]` 雙向連結。
3. **更新主題頁面 (`wiki/topics/`)**：歸類至對應主題。
4. **更新索引 (`wiki/index.md`)**：於目錄新增或更新摘要。
5. **寫入日誌 (`wiki/log.md`)**：追加紀錄。

### 3.2 查詢與增量歸檔流程 (Query & Synthesis Workflow)
### 3.3 知識庫健康檢查流程 (Lint Workflow)
