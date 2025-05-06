---
title: "NodePay on Docker"
date: 2024-12-22
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 虛擬貨幣, 空投, 被動收入]
description: "使用 Docker 快速部署 NodePay 自動任務腳本，每週更新 token 即可掛機賺點數，支援自動完成平台任務。"
image: /assets/images/nodepay/banner.png
written_by: 機掰雞
lang: zh-TW
---
![NodePay 封面圖](/assets/images/nodepay/banner.png)

NodePay 是一個虛擬貨幣相關的自動任務平台，透過每日完成指定任務來累積積分，最終可兌換為實際代幣。**無需 KYC、低門檻、支援掛機**，適合尋求被動收入的新手與進階用戶。

## 🌟 核心特色

### 🪙 積分獎勵制度
- 每日任務完成即可賺取 NodePay Points
- 積分可轉換為代幣或兌換獎品
- 可設定多帳戶掛機(目前1帳戶可掛三台,不同IP)

### 🤖 自動化任務處理
- Docker 掛機版支援全自動執行
- 支援 token 更新，約每週更換一次
- **無需手動點擊，每日自動簽到與任務**

### 🛠 改良版掛機邏輯
- **token 過期時 CPU 不會飆升**
- 優化資源使用，避免佔用系統效能

---

## 📝 註冊帳號

👉 [立即註冊 NodePay](https://app.nodepay.ai/register?ref=TCVqK77JRJcYTVG)

🎉 使用機掰雞的邀請連結註冊可以讓我獲得 **100 NodePay Points**，也謝謝你的支持！

---

## 🔗 連結

- 🌐 官網：[https://nodepay.ai/](https://nodepay.ai/)
- 🐳 Docker Hub：[78chicken/nodepay](https://hub.docker.com/r/78chicken/nodepay)
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
![NodePay token](/assets/images/nodepay/img_1.png)
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
