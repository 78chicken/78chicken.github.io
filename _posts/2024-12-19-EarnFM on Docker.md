---
title: "Earn.fm on Docker"
date: 2024-12-19
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入]
description: "使用 Docker 部署 Earn.fm，分享閒置網路頻寬賺取被動收入，支援多平台運行，註冊即享推薦獎勵。"
image: /assets/images/earnfm/banner.png
written_by: 機掰雞
lang: zh-TW
---

![Earn.fm 封面圖](/assets/images/earnfm/banner.png)

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

> 🔔 **提醒：**  
> 建議每個帳號僅綁定一台設備，以避免帳號風險。  
> 適合部署在 VDS、VPS、小型主機或 Raspberry Pi 等長時間掛機設備上。


## 🐳 Docker 執行指令

請先到 [Earn.fm 註冊後的儀表板](https://earn.fm/ref/YAMAZTYC) 找到你的 `API Token`，並用以下指令替換。

```bash
docker run -d --restart=always --replace -m 64M \
-e EARNFM_TOKEN=你的API_KEY \
--name EarnFm \
earnfm/earnfm-client
```
