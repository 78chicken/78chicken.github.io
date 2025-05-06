---
title: "Solix on Docker"
date: 2025-04-23
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, depin, 被動收入, 頻寬共享]
description: "使用 Docker 部署 Solix DePIN 頻寬共享平台，自動化賺取 SLIX 代幣，無痛掛機獲得被動收益。"
image: /assets/images/solix/banner.png
written_by: 機掰雞
lang: zh-TW
---

![Solix 封面圖](/assets/images/solix/banner.png)

Solix DePIN 是一個去中心化的實體基礎設施網絡（DePIN）平台，讓用戶分享並貨幣化其 **閒置網路頻寬**。透過 **瀏覽器擴充功能**，你可以在不影響自身使用的情況下，賺取名為 **SLIX** 的代幣，實現真正的 **被動收入**！

## 🌐 核心特色

### 🧠 MCP 智能協議
- 採用 **Model Context Protocol（MCP）**
- 結合 AI 與即時網路狀況
- 智慧化分配頻寬，提升效率與隱私保護

### 🌍 去中心化架構
- **點對點（P2P）網絡**
- 高抗審查性、穩定性高
- 覆蓋 **63 個國家**，每日處理超過 **275TB** 數據

### 🪙 自動獲得 SLIX 代幣
- 安裝插件後自動運行
- 閒置頻寬也能賺錢
- 適合長期掛機、無痛挖礦

---

## 📝 註冊帳號

👉 [立即註冊 Solix](https://dashboard.solixdepin.net/sign-up?ref=PtjNL563)

🎉 使用機掰雞的邀請連結可獲得額外「雞飼料」，你也會收到點數獎勵，不會影響自身收益！

---

## 🔗 連結

- 🌐 官網：[https://solixdepin.net](https://solixdepin.net)
- 🐳 Docker Hub：[78chicken/solix](https://hub.docker.com/r/78chicken/solix)
> **功能：** 自動登入與頻寬分享任務掛機

---

## ⚠️ 注意事項

> ❗ **非官方開發版本**，請謹慎使用，使用前請自行評估風險：
> - 有被封號或資安風險
> - 此程式非由機掰雞撰寫，僅轉製為 Docker 版本

---

## 📁 運行前準備

請建立 `accounts.json` 檔案，內容格式如下：

```json
[
  {
    "Email": "abcd@gmail.com",
    "Password": "123456"
  }
]
```

## 🐳 Docker 執行指令
請根據你的實際檔案路徑替換 /opt/solix/accounts.json：

```bash
#/opt/solix/accounts.json 請改成你自己的路徑
docker run -d --restart always --replace -m 50M \
-v /opt/solix/accounts.json:/app/solix/accounts.json \
--name Solix \
docker.io/78chicken/solix:latest
```
