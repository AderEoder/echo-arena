# 開發流程指引

本專案採用三層分支策略：
- **main**：穩定版本，正式發佈用
- **dev**：日常開發整合
- **feat/***：功能開發分支

---

## 分支流程圖

```mermaid
flowchart LR
    subgraph 功能開發
    A[feat/功能分支] -->|PR| B(dev)
    end

    subgraph 整合測試
    B(dev) -->|PR| C(main)
    end

    C -->|同步更新| B
