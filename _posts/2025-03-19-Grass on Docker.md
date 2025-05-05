---
title: "Grass on Docker"
date: 2025-03-19
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣]
description: "使用 Docker 或瀏覽器擴充功能部署 Grass，分享閒置網路頻寬賺取被動收入，支援無頭裝置運行。"
image: /assets/images/grass/banner.png
author: 機掰雞
lang: zh-TW
---

![Grass 封面圖](/assets/images/grass/banner.png)

Grass 是一個透過分享你閒置的計算資源來賺取報酬的服務，適合用來部署在家中的閒置裝置，賺取被動收入。

---
## 🚀 Grass 主要特點

- ✅ **低資源佔用**：最多只使用 0.3% 的頻寬，幾乎不影響日常上網。
- 🔒 **隱私保護**：不會收集你的個人資料，只抓取公開的網站資訊。
- 💰 **點數獎勵**：分享頻寬可獲得 GRASS 點數，參與未來空投與質押。
- 👥 **推薦制度**：多層級推薦獎勵，最高可獲下線收益的 20%。

---

## 📝 註冊帳號

👉 [立即註冊 Grass](https://app.getgrass.io/register/?referralCode=3vuJ8ZYTeL4CNju)

🎉 使用機掰雞的邀請連結註冊後，**我將獲得你收益的 10% 作為飼料費**（不影響你的收益）。

---

## 🔗 連結

- 🌐 官網：[https://www.getgrass.io/](https://www.getgrass.io/)
- 🐳 Docker Hub：[trangoul/grass-desktop](https://hub.docker.com/r/trangoul/grass-desktop)
> **功能：** 分享閒置計算資源，賺取被動收入

---

## 🐳 Docker 執行指令

請替換以下資訊：
- `你的VNC密碼`：設置 VNC 密碼
- `你的帳號`：你的 Grass 帳號
- `你的密碼`：你的 Grass 密碼

```bash
docker run -d --restart always --replace -p 5900:5900 -m 256M \
-e VNC_PASSWORD="你的VNC密碼" -e GRASS_USERNAME="你的帳號" -e GRASS_PASSWORD="你的密碼" \
--name Grass \
trangoul/grass-desktop:latest
```
