---
title: "Earn.fm Docker 掛機教學：一鍵部署節點，輕鬆分享頻寬賺取被動收入"
date: 2024-12-19
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 頻寬分享, Earn.fm, API Token]
description: "Earn.fm 是一個入門級的頻寬分享平台。本教學提供完整的 Docker 掛機指令，教你如何獲取 API Token 並一鍵部署 Earn.fm 節點，將閒置網路頻寬轉換為自動化被動收入。輕鬆在多平台實現 24/7 掛機賺錢。"
image: /assets/images/bot/earnfm/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![Earn.fm 封面圖](/assets/images/bot/earnfm/banner.webp)

Earn.fm 是一個讓用戶透過分享閒置網路頻寬來賺取被動收入的平台。只需安裝客戶端並保持網路連線，即可自動獲得報酬，適合部署在閒置設備上。

---

## 📝 註冊帳號

👉 [立即註冊 Earn.fm](https://earn.fm/ref/YAMAZTYC)

🎉 使用機掰雞的邀請連結註冊後，**我將獲得你收益的 10% 作為飼料費**（不影響你的收益）。

---

## 🔗 連結

- 🌐 官方網站：[Earn.fm](https://earn.fm/en/)
- 🐳 Docker image：[earnfm/earnfm-client](https://hub.docker.com/r/earnfm/earnfm-client)
> **功能：** 分享閒置網路頻寬，賺取被動收入

---

{% include warning.md %}

---  

## 🐳 Docker 執行指令

請先到 [Earn.fm 註冊後的儀表板](https://earn.fm/ref/YAMAZTYC) 找到你的 `API Token`，並用以下指令替換。

```bash
docker run -d --restart=always -m 64M \
-e EARNFM_TOKEN=你的API_KEY \
--name EarnFm \
earnfm/earnfm-client
```
