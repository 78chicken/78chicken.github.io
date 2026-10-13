---
title: "Teneo Docker 掛機教學：運行 AI 節點，賺取 Teneo Points 等待代幣空投！"
date: 2026-10-13
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣, Teneo, AI 節點, 社交媒體數據, TGE]
description: "Teneo 是一個去中心化社交媒體數據解鎖平台。本教學提供 Teneo 完整的 Docker 掛機指令，教你如何部署 AI 節點、獲取 accessToken，自動賺取 Teneo Points，把握 TGE 代幣轉換的空投機會，輕鬆打造 Web3 被動收入。"
image: /assets/images/bot/teneo/banner.webp
written_by: "機掰雞"
lang: zh-TW
---

![Teneo 封面圖](/assets/images/bot/teneo/banner.webp)
> 📢 **【更新通知】**
> 10.13 2026 Q4 空投資訊,首先要做的三件事 (https://teneo-protocol.ai/blog/the-first-step-towards-future-teneo-rewards)  
  1.連接錢包  
  2.綁定X帳號  
  3.運行Beacon至少72小時  


**Teneo** 是一個去中心化的社交媒體數據解鎖平台，旨在讓用戶透過運行瀏覽器端的 AI 節點（Community Node），貢獻計算資源以解鎖公開的社交媒體數據，並獲得回報。該平台強調用戶隱私，僅處理公開數據，並以去中心化的方式運作，讓數據回歸用戶所有。

---

## 🌟 核心特色

### 🔐 去中心化數據解鎖
- **Teneo Community Node**：用戶可在瀏覽器中運行 AI 節點，貢獻計算資源以解鎖公開的社交媒體數據。
- **隱私保護**：僅處理公開數據，保障用戶隱私。

### 💰 獎勳機制
- **Teneo Points**：用戶透過運行節點、邀請他人、保持節點在線等方式獲得 Teneo Points。
- **未來代幣化**：Teneo Points 將在未來的 Token Generation Event（TGE）中轉換為 Teneo Tokens。

### 📊 用戶儀表板
- **Teneo Dashboard**：提供用戶管理活動、追蹤獎勳、查看進度等功能。
- **功能豐富**：包括連接錢包、查看推薦人數、獎勳歷史等。

### 📈 社群與成長
- **快速增長**：截至 2025 年 1 月，Teneo 的社群節點數量已超過 370 萬，覆蓋 191 國。

---

## 📝 註冊帳號

👉 [立即註冊 Teneo](https://dashboard.teneo.pro/auth/signup)

🎉 推薦碼：`1J15s`
- 你可獲得 **1,000 Teneo Point**
- 機掰雞將獲得額外雞飼料，但**不影響你的收益**

---

## 🔗 連結

- 🌐 官方網站：[https://teneo.pro/](https://teneo.pro/)
- 🐳 Docker image：[78chicken/teneo](https://hub.docker.com/r/78chicken/teneo)

---

{% include warning.md %}

---

### 📄 準備 `tokens.json`

建立一份 `tokens.json` 檔案，內容如下，每行一個帳號的 Token：

```txt
# 建議每帳號搭配一個獨立 IP 運行，避免封號
[
    {
        "Email": "Your Email",
        "accessToken": "eyJhbGciOiJ..........klKsADlIlm8M"
    }
]
```

## 🔍 如何取得 Token？
1. 使用 Chrome 瀏覽器登入 Teneo Dashboard
2. 按下 F12 開啟開發者工具
3. 前往 Application → Storage → Local Storage
4. 複製 accessToken- 對應的值
5. 貼入 tokens.json

![Teneo token](/assets/images/bot/teneo/img_1.webp)

## 🐳 Docker 執行指令
```bash
# -v /opt/teneo/tokens.txt 請改成你自己的檔案路徑
docker run -d --restart always -m 50M \
-v /opt/teneo/tokens.json:/app/teneo/tokens.json \
--name Teneo \
docker.io/78chicken/teneo:latest
```
