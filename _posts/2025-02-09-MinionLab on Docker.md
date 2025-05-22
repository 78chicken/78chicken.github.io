---
title: "MinionLab on Docker"
date: 2025-02-09
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣, 空投]
description: "透過 Docker 掛機 MinionLab（前稱 StreamAi），僅需提供帳密即可自動化執行，轉換閒置資源為收益。"
image: /assets/images/bot/minionlab/banner.webp
written_by: "機掰雞"
lang: zh-TW
---

![MinionLab 封面圖](/assets/images/bot/minionlab/banner.webp)

**MinionLab**（前稱 **Stream AI**）是一個結合 AI 與區塊鏈的去中心化自主代理平台，透過裝置資源貢獻與自動化任務完成，讓用戶輕鬆賺取 MINAI 積分，進一步參與 Web3 資訊經濟網絡。

---

## 🌟 核心特色

### 🤖 自主 AI 代理（Minions）

- Minions 是運行於使用者裝置上的 AI 代理，能夠自動完成網站導航、高階數據提取等多步驟任務。
- 用戶貢獻帶寬與算力，即可成為 MinionLab 網絡節點並獲得積分獎勵。
- 形成去中心化、可持續的合作生態系統。

---

### 🌐 去中心化 Agent 運行環境

- 全球首個專為 AI 代理打造的去中心化執行框架。
- 支援如 Playwright 的瀏覽器操作框架，實現廣泛自動化任務執行。
- 上線三日即吸引 1500+ 內測節點參與。

---

### 📊 Stream AI 數據產品

- MinionLab 的 Stream AI 模組可從 Google、Amazon、Store 等多個平台即時抓取數據。
- 透過分散式節點進行數據清洗與優化，確保 AI 模型獲取精準資訊。

---

## 📝 註冊帳號

👉 [立即註冊 MinionLab](https://invite.minionlab.io/?referralCode=EanPSszy)

🎉 使用此推薦連結，**機掰雞可獲得額外雞飼料**，**不影響你的收益**。

---

## 🔗 連結

- 🌐 官方網站：[Minionlab.ai](https://www.minionlab.ai/)
- 🐳 Docker image：[78chicken/minionlab](https://hub.docker.com/r/78chicken/minionlab)

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
    "Email": "你的Email",
    "Password": "你的密碼"
  }
]
```
---

## 🐳 Docker 執行指令
```bash
# -v /opt/minionlab/accounts.json 請改成你自己的檔案路徑
docker run -d --restart always --replace -m 50M \
-v /opt/minionlab/accounts.json:/app/minionlab/accounts.json \
--name MinionLab \
78chicken/minionlab:latest
```
