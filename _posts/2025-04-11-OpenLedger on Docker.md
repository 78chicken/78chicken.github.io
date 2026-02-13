---
title: "OpenLedger Docker 掛機實測(已終止)"
date: 2025-09-09
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 區塊鏈, AI, 被動收入, OpenLedger, AI 挖礦, 歸因證明, 資格門檻]
description: "OpenLedger 是一個去中心化 AI 平台，主打 AI 挖礦與資料貢獻。本教學提供完整的 Docker 掛機部署指令，教你如何獲取 Address 與 Token。內含機掰雞真實實測心得（擼了個寂寞），並深度解析項目資格門檻與可驗證 AI 收益模式的潛在風險。"
image: /assets/images/bot/openledger/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![OpenLedger 封面圖](/assets/images/bot/openledger/banner.webp)

> 📢 **【更新通知】**
>
> You're not eligible.
> 真是搞笑，又擼了個寂寞。看來很多人都是這樣。

**OpenLedger** 是新一代專為人工智慧（AI）打造的去中心化區塊鏈平台，提供完整的經濟基礎設施，讓你可以**貢獻數據、微調模型，並賺取 AI 模型代幣**，實現真正的「掛機挖 AI」新模式。

---

## 🧠 核心功能與特色

### 📦 可支付的 AI 模型（Payable AI Models）
- 引入「**歸因證明（Proof of Attribution）**」機制
- 貢獻數據即可獲得公平報酬
- 模型開發者可追蹤數據來源並調整模型效能

### 🌐 數據網絡（Datanets）
- 建立高品質資料池
- 訓練特定領域的語言模型（SLMs）
- 保證模型的專業準確度與產業相關性

### 🏭 模型工廠（Model Factory）
- 提供透明的微調與歸因平台
- 確保模型貢獻者獲得獎勵
- 支援可驗證、可追溯的模型開發

### 🚀 初始 AI 發行（Initial AI Offering）
- 模型資產化、代幣化上鏈
- 可在平台交易與社群治理
- 強化模型的流動性與去中心化

---

## 📝 註冊帳號

👉 [立即註冊 OpenLedger](https://testnet.openledger.xyz/?referral_code=gqp3ei3aci)

🎉 使用機掰雞的邀請連結可獲得額外「雞飼料」，你也會收到點數獎勵，不會影響自身收益！

---

## 🔗 連結

- 🌐 官方網站：[OpenLedger](https://www.openledger.xyz)
- 🐳 Docker image：[78chicken/openledger](https://hub.docker.com/r/78chicken/openledger)
> **功能：** 自動登入、資料貢獻與模型互動

---

{% include warning.md %}

---

## 📁 運行前準備

請建立 `accounts.json` 檔案，內容格式如下：

```json
[
  {
    "Address": "0xf43D43...E67315F3Cf4f",
    "Token": "eyJhbG....NTMxWrRizAD7U0"
  }
]
```

## 🔑 Access Token 取得方式：
Chrome → 打開 OpenLedger Dashboard → F12 → Network → 搜尋 me → 找到你的 Token
![OpenLedger token](/assets/images/bot/openledger/img_1.webp)

---

## 🐳 Docker 執行指令
請根據你的實際檔案路徑替換 /opt/openledger/accounts.json：

```bash
#/opt/openledger/accounts.json 請改成你自己的路徑
docker run -d --restart always -m 50M \
-v /opt/openledger/accounts.json:/app/openledger/accounts.json \
--name OpenLedger \
docker.io/78chicken/openledger:latest
```
