---
title: "Grass Docker 掛機教學：分享頻寬，參與 Solana AI 網路賺取 GRASS 代幣空投"
date: 2026-06-17
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣, Grass, Solana, AI 資料]
description: "Grass 是一個基於 Solana 區塊鏈的去中心化 AI 數據網絡。本教學提供完整的 Docker 掛機部署指令與步驟，教你如何安全分享閒置頻寬，輕鬆累積 Grass Points，把握未來 GRASS 代幣空投的被動收入機會。"
image: /assets/images/bot/grass/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![Grass 封面圖](/assets/images/bot/grass/banner.webp)
> 📢 **【更新通知】**  
> 更新版本,記得VNC重新登入
 

Grass 是一個透過分享你閒置的計算資源來賺取報酬的服務，適合用來部署在家中的閒置裝置，賺取被動收入。

---

## 📌 核心功能與特點

- **去中心化資料抓取**：利用用戶共享的閒置頻寬，從公共網絡中抓取非結構化資料，轉換為可用於 AI 訓練的結構化資料集。
- **隱私與安全**：僅使用用戶的 IP 位址路由網絡流量，不會存取用戶個人資料，並通過零知識證明確保資料完整性。
- **獎勵機制**：用戶通過貢獻帶寬獲得 Grass Points，未來可兌換為 GRASS 代幣，參與網絡治理與收益分配。
- **高擴展性**：基於 Solana 區塊鏈，處理速度快，支持大量用戶同時參與。
- **龐大用戶基礎**：全球已有超過 250 萬活躍節點，為 AI 模型提供大量資料支持。:contentReference[oaicite:14]{index=14}

## 🎯 使用者價值

- **被動收入**：:contentReference[oaicite:16]{index=16}
- **參與 AI 發展**：:contentReference[oaicite:19]{index=19}
- **資料主權**：:contentReference[oaicite:22]{index=22}:contentReference[oaicite:24]{index=24}

---

## 📝 註冊帳號

👉 [立即註冊 Grass](https://app.getgrass.io/register/?referralCode=3vuJ8ZYTeL4CNju)

🎉 使用機掰雞的邀請連結註冊後，**我將獲得你收益的 10% 作為飼料費**（不影響你的收益）。

---

## 🔗 連結

- 🌐 官方網站：[Grass](https://grass.io/)
- 🐳 Docker image：[trangoul/grass-desktop](https://hub.docker.com/r/trangoul/grass-desktop)
> **功能：** 分享閒置計算資源，賺取被動收入

---

{% include warning.md %}

---

## 🐳 Docker 執行指令

請替換以下資訊：
- `你的VNC密碼`：設置 VNC 密碼
- `你的帳號`：你的 Grass 帳號
- `你的密碼`：你的 Grass 密碼

```bash
docker run -d --restart always -p 5900:5900 -m 256M \
-e VNC_PASSWORD="你的VNC密碼" -e GRASS_USERNAME="你的帳號" -e GRASS_PASSWORD="你的密碼" \
--name Grass \
trangoul/grass-desktop:latest
```
