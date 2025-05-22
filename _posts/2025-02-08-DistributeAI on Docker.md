---
title: "Distribute.AI on Docker"
date: 2025-02-08
updated: 2025-05-22
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, AI, 去中心化]
description: "透過 Docker 掛機 Distribute.AI（前稱 Oasis），只需提供帳號與 Token，即可參與去中心化 AI 計算資源網絡並獲得收益。"
image: /assets/images/bot/distributeai/banner.webp
written_by: "機掰雞"
lang: zh-TW
---

![Distribute.AI 封面圖](/assets/images/bot/distributeai/banner.webp)

> 📢 **【2025-05-22】**
>
> [領取空投](https://claim.distribute.ai/)，錢包須至少有0.02SOL
> 機掰雞剩一組帳號有領取資格,有總比沒有好



--- 

**Distribute.AI**（前稱 **Oasis**）是一個結合 AI 模型訓練與推論的去中心化運算平台，用戶可透過貢獻算力與網路資源參與節點運行，並以最小化配置自動掛機賺取收益。支援 Docker 快速部署，讓你低門檻參與 Web3 分散式 AI 網絡。

---

## 🌟 核心特色

### 🧠 去中心化 AI 推論平台

- Distribute.AI 提供 AI 訓練與推理任務，節點可分攤執行任務，協助訓練大型 AI 模型。
- 所有資源貢獻皆以 Token 記錄並可獲得積分獎勵。
- 對使用者而言，就是閒置電腦的變現方式。

---

### 🐳 Docker 掛機支持

- 可在 Linux、VPS 或本地機器上以 Docker 形式運行。
- 支援多帳號 JSON 結構，一機一帳建議可降低風險。
- 可選擇新建或延用現有節點。

---

## 📝 註冊帳號

👉 [立即註冊 Distribute.AI](https://r.distribute.ai/jyhfeng0209)

🎉 使用此推薦連結，**機掰雞可獲得額外雞飼料**，**不影響你的收益**。

---

## 🔗 連結

- 🌐 官方網站：[Distribute.ai](https://www.distribute.ai/)
- 🐳 Docker image：[78chicken/distributeai](https://hub.docker.com/r/78chicken/distributeai)

---

## ⚠️ 注意事項

> ❗ **此為非官方工具**，使用請自行評估帳號安全與資安風險。
>
> - 有被封號或資安風險
> - 程式非機掰雞撰寫，僅封裝成 Docker 映像以利掛機部署

---

## 📄 準備 `accounts.json`

> 建立 `accounts.json` 檔案，格式如下（支援多組帳號）：
>
> ⚠️ 機掰雞建議一 IP 對應一帳號，以降低封號風險。
```json
[
  {
    "Email": "你的EMAIL",
    "Providers": [
      "Your Token"
    ]
  }
]
```
若你尚未取得 Token，可先建立空的 accounts.json：

```json
[
  {
    "Email": "你的EMAIL",
    "Providers": []
  }
]
```
---

## 🧪 Token 取得方式（需 Python 環境）
執行container, 並進入到該container的console, 然後將setup.py複製到你的機器上(需要可以執行python的環境),執行後會產生新的accounts.json
```bash
# 請將路徑與 container 名稱替換為你的設定
docker run --rm -m 50M -v /opt/distributeai/accounts.json:/app/distributeai/accounts.json --name DistributeAi docker.io/78chicken/distributeai:latest
docker exec -it xxxx sh
```
<span style="color: red;">Copy setup.py to your local disk, then run "python setup.py"</span>

## 🐳 Docker 執行指令
重新啟動一次你的Container,並記得套用新的accounts.json
```bash
docker run -d --restart always --replace -m 50M \
-v /opt/distributeai/accounts.json:/app/distributeai/accounts.json \
--name DistributeAi \
docker.io/78chicken/distributeai:latest
```

