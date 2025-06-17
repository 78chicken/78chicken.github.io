---
title: "Monami on Docker"
date: 2025-06-17
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, depin, 虛擬貨幣, airdrop, 被動收入]
description: "Monami 是一個基於 Monad 架構的 DePIN 項目，允許用戶利用閒置頻寬和計算資源，參與去中心化 AI 網絡並獲得 MONAMI 代幣獎勵。"
image: /assets/images/bot/monami/banner.webp
written_by: 機掰雞
published: false
lang: zh-TW
---

![Monami 封面圖](/assets/images/bot/monami/banner.webp)


## Monami Network 簡介

**Monami Network** 是一個基於 Monad 的 DePIN 項目，旨在提供去中心化的高效能基礎設施服務。它允許用戶共享閒置頻寬與計算能力，將普通設備變為 AI 網絡節點，並以透明信任機制獲得 MONAMI 代幣獎勵。

---

## 核心特色

- **超快共識，秒速確認**  
  採用 MonadBFT 技術，區塊最快 1 秒內確認，交易即時生效。

- **非同步並行，極速處理**  
  共識與執行解耦，支援大量交易平行處理，系統高效不卡頓。

- **低門檻去中心化**  
  普通設備即可參與節點，人人可掛機賺取代幣。

- **共享資源即收益**  
  貢獻閒置頻寬與算力，即可轉換為 MONAMI 代幣獎勵。

---

## 📝 註冊與節點設置

👉 [立即註冊 Monami](https://monami.network/signup?refcode=8HG60F)

🎉 使用機掰雞的邀請連結註冊後，**我將獲得你收益的一點點雞飼料作為回饋**（不影響你的收益）。

---

## 🔗 連結

- 🌐 官方網站：[https://monami.network/](https://monami.network/)
- 🐳 Docker image：[78chicken/monami](https://hub.docker.com/r/78chicken/monami)

---

{% include warning.md %}

---

## 📁 運行前準備

新增檔案`accounts.json`。

```json
  [
      {
          "Email": "your_email_address_1",
          "Password": "your_password_1"
      }
  ]   
```
🐳 Docker 執行方式
請根據您的實際檔案路徑替換 /opt/monami/accounts.json：

```bash
docker run -d --restart always -m 50M \
  -v /opt/monami/accounts.json:/app/monami/accounts.json \
  --name Monami \
  docker.io/78chicken/monami:latest
```
