---
title: "CryplexAi on Docker"
date: 2025-05-02
updated: 2025-07-16
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, depin, 虛擬貨幣, airdrop, 空投, 被動收入]
description: "使用 Docker 掛機方式部署 CryplexAi，享受 Depin 類型專案帶來的自動化收益與空投獎勵，無需 KYC 或高效能機器即可參與。"
image: /assets/images/bot/cryplexai/banner.webp
written_by: 機掰雞
lang: zh-TW
---
![CryplexAi 封面圖](/assets/images/bot/cryplexai/banner.webp)
> 📢 **【更新通知】**
>
> 映像檔更新


--- 
Cryplex 是一個去中心化儲存與 AI 訓練資料供應平台，讓用戶可將閒置的儲存空間轉化為數位資產。

## 📌 核心功能與特點

- 利用 **分散式儲存技術**，聚合用戶的閒置硬碟空間
- 透過 **AES-256 加密** 與 **零知識證明**，確保數據的隱私與安全
- 使用 **區塊鏈與智能合約** 管理獎勵與儲存貢獻，發放 `Cryplex` 代幣
- 為 **AI 模型訓練** 提供安全、高效、可擴展的儲存解決方案
- **去中心化架構**，無單點故障，具抗審查能力

---

## 🎯 使用者價值

- 一般用戶可「**出租硬碟空間**」賺取代幣
- 開發者與企業可**安全儲存與取用 AI 訓練資料**
- 整體生態系統鼓勵 **社群參與** 與 **技術創新**

---
## 📝 註冊帳號

👉 [立即註冊 CryplexAi](https://app.cryplex.ai/dashboard?ref=nvvxu)

🎉 使用機掰雞的邀請連結可以獲得額外的「雞飼料」，你也會收到一些點數，不會影響自身收益！

---
## 🔗 連結

- 🌐 官方網站：[Cryplex.ai](https://cryplex.ai/)
- 🐳 Docker image：[78chicken/cryplexai](https://hub.docker.com/r/78chicken/cryplexai)

--- 

{% include warning.md %}

---

## 📁 運行前準備
請準備好 `tokens.txt`，取得方式如下：
>   1. 登入 Dashboard 頁面
>   2. 按下 `F12` 進入開發者工具
>   3. 擷取並儲存 `tokens.txt`

![CryplexAi token](/assets/images/bot/cryplexai/img.webp)


## 🐳 Docker 執行方式

請根據你的實際檔案路徑替換 `/opt/stobix/accounts.txt`：
```bash
docker run -d --restart always -m 50M \  
  -v /opt/cryplexai/tokens.txt:/app/cryplexai/tokens.txt \
  --name CryplexAi \
  docker.io/78chicken/cryplexai:latest
```

