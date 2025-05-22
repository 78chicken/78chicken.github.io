---
title: "Flow3 on Docker"
date: 2025-03-21
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣, 分享頻寬]
description: "透過 Docker 掛機 Flow3，分享閒置頻寬賺取 Flow3 Points，快速啟動僅需提供 token。"
image: /assets/images/bot/flow3/banner.webp
written_by: "機掰雞"
lang: zh-TW
---

![Flow3 封面圖](/assets/images/bot/flow3/banner.webp)

Flow3 是一個去中心化無線網路（DeWi）平台，讓使用者可以透過分享未使用的網路頻寬和 CPU 算力來賺取被動收入。

---

## 🌟 Flow3 平台簡介與核心特色

### 🔧 資源共享與收益機制

- 使用者可以透過分享頻寬與 CPU 算力來賺取積分（Flow3 Points），這些積分可轉換為代幣。
- 自動掛機運行後每日可賺取積分，並享有推薦獎勵（例如推薦下線額外 10% 積分）。

### 🌐 支援 AI 與去中心化應用

- Flow3 網路支援 AI 數據處理與創新應用，是一個支援 Web3 與人工智慧的共享平台。

### 👥 多角色參與與收益分配

- 日常使用者與節點驗證者皆可參與，依角色不同享有不同獎勵結構與貢獻方式。

### 🧩 Flow3 生態系統組件

- **Flow3 Chain**：負責去中心化資料儲存。
- **Flow3 Gateway**：將多餘頻寬與算力轉為可變現資源。
- **Flow3 Marketplace**：交易頻寬、算力、AI 數據集等資源。

---

## ⚠️ 注意事項

> ❗ **非官方掛機方式**，可能存在被封號或資安風險，請自行評估是否使用。
>
> - 有被封號或資安風險
> - 程式非機掰雞開發，僅加工為 Docker 映像以方便掛機部署。

---

## 📝 註冊帳號

👉 [立即註冊 Flow3](https://dashboard.flow3.tech?ref=TVVEN1heu)

🎉 使用此推薦連結，**機掰雞可獲得額外雞飼料**，**不影響你的收益**。

📌 建議使用 [Phantom 錢包](https://phantom.app/) 綁定，網站略慢，請多點耐心。

---

## 🔗 連結

- 🌐 官方網站：[Flow3](https://flow3.tech)
- 🐳 Docker image：[78chicken/flow3](https://hub.docker.com/r/78chicken/flow3)

---

## 📄 準備 `tokens.txt`

> 建立 `tokens.txt` 檔案，一行一組token（支援多組 refresh token）：
>
> - ⚠️ 建議每個 IP 僅對應一組 token。
> - 取得 refresh_token 方式如下。

![Flow3 token1](/assets/images/bot/flow3/img_1.webp)
![Flow3 token2](/assets/images/bot/flow3/img_2.webp)

---

## 🐳 Docker 執行指令
```bash
# /opt/flow3/tokens.txt 請換成你自己放置的路徑
docker run -d -m 50M --restart always --replace \
-v /opt/flow3/tokens.txt:/app/flow3/tokens.txt \
--name Flow3 \
docker.io/78chicken/flow3:latest
```
