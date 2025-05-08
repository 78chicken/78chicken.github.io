---
title: "NodePay on Docker"
date: 2024-12-22
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 虛擬貨幣, 空投, 被動收入]
description: "使用 Docker 快速部署 NodePay 自動任務腳本，每週更新 token 即可掛機賺點數，支援自動完成平台任務。"
image: /assets/images/bot/nodepay/banner.png
written_by: 機掰雞
lang: zh-TW
---
![NodePay 封面圖](/assets/images/bot/nodepay/banner.png)

Nodepay 提供了一個低門檻的方式，讓用戶可以在無需高性能設備的情況下，參與到區塊鏈生態中，並支持 AI 和數據密集型需求。

## 🌟 核心特色

### 🔗 去中心化 AI 訓練平台

- **使命**：Nodepay 致力於建立一個去中心化的 AI 訓練與開發生態系統，讓用戶能夠擁有並訪問實時數據智能。
- **運作方式**：用戶可透過分享閒置的網路頻寬與數據，參與 AI 模型訓練，並獲得代幣獎勳。

### 📡 資源貢獻與獎勳機制

- **頻寬分享**：將未使用的網路頻寬提供給平台，賺取被動收入。
- **實時數據擷取**：協助進行實時數據爬取，提升 AI 模型的輸出品質。
- **強化學習**：透過反饋與訓練，改善 AI 模型，並獲得相應的獎勳。
- **人類驗證**：完成驗證任務，解鎖額外獎勳，增強 AI 的可靠性。

### 🌍 全球去中心化網絡

- **節點分佈**：Nodepay 擁有來自 180 多個國家的超過 1.8 百萬個節點。
- **合作夥伴**：與 21 家以上的企業合作，共同推動 AI 去中心化發展。

### 🔐 資料保護與安全性

- **資料隱私**：Nodepay 保證用戶的個人資料受到保護，無法被第三方訪問。
- **控制權**：用戶可完全控制何時使用其閒置頻寬，確保資料安全。

### 🎮 互動與遊戲化元素

- **Node Wars**：參與人類驗證遊戲，增加獎勳。
- **Node Agents**：獲得限量 NFT，解鎖特殊權益。
- **Node Validators**：成為驗證者，提升網絡安全性，增加收益。
- **Node Data**：擁有數據集，提升 AI 模型輸出。
- **Node Collect**：貢獻頻寬，協助實時數據擷取。
- **Node Force**：訓練專屬 AI 模型，參與強化學習。

---

## 📝 註冊帳號

👉 [立即註冊 NodePay](https://app.nodepay.ai/register?ref=TCVqK77JRJcYTVG)

🎉 使用機掰雞的邀請連結註冊可以讓我獲得 **100 NodePay Points**，也謝謝你的支持！

---

## 🔗 連結

- 🌐 官方網站：[Nodepay.ai](https://nodepay.ai/)
- 🐳 Docker image：[78chicken/nodepay](https://hub.docker.com/r/78chicken/nodepay)
> **功能：** 自動簽到、執行每日任務、支援多帳號

---

## ⚠️ 注意事項

> ❗ **非官方開發版本**，請謹慎使用, 使用前請自行評估風險：
> - 有被封號或資安風險
> - 程式非機掰雞開發，僅加工為 Docker 映像以方便掛機部署。

---

## 📁 運行前準備

請建立 `tokens.txt` 檔案，裡面放置你的登入 token（通常每週需要更新一次）

📌 取得 token 的方式如下:
![NodePay token](/assets/images/bot/nodepay/img_1.png)
---

## 🐳 Docker 執行指令

請根據你的實際檔案路徑替換 `/opt/nodepay/tokens.txt`：

```bash
#/opt/nodepay/tokens.txt 請換成你的實際路徑
docker run -d --restart always --replace -m 50M \
-v /opt/nodepay/tokens.txt:/app/nodepay/tokens.txt \
--name Nodepay \
docker.io/78chicken/nodepay:latest
```
