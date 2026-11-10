# 員林好吃好玩 LLM Wiki

本專案參考 Karpathy 的 LLM Wiki 概念，建立屬於員林在地美食與景點的 LLM 增量知識庫。

## 目錄結構

```text
yuanlin-wiki/
├── AGENTS.md                   # Agent 維護規範與工作流程
├── README.md                   # 專案說明
├── raw/                        # 原始資料（唯讀，食記、剪藏、筆記）
│   ├── food/
│   ├── attractions/
│   └── assets/
└── wiki/                       # LLM 增量維護區
    ├── index.md               # 分類索引
    ├── log.md                 # 變更日誌
    ├── entities/              # 實體頁面 (店家、景點)
    ├── topics/                # 主題彙整
    └── syntheses/             # 綜合規劃與評比
```
