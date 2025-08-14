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
開發步驟
1. 建立功能分支
git checkout dev
git pull origin dev
git checkout -b feat/功能名稱

2. 開發 & Commit
git add .
git commit -m "feat: 新增 XXX 功能"
git push origin feat/功能名稱

3. 建立 PR

feat → dev

Base branch：dev

Compare branch：feat/功能名稱

Code Review 後合併，刪除該功能分支

4. dev → main 發佈流程

Base branch：main

Compare branch：dev

必須經過 PR & Review 才能合併

5. 合併後同步
git checkout dev
git pull origin dev
git merge main
git push origin dev


💡 重點：

永遠不要直接推到 main

所有功能修改都必須走 PR 流程

PR 合併後記得同步分支，避免衝突
