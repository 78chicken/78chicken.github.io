---
title: "Dawn Docker (停止掛機,避免封號)"
date: 2026-01-30
categories: [bot]
tags: [Docker, 掛機, 被動收入, 網路賺錢, 分享頻寬, Dawn, 去中心化網路, Web3]
description: "如何用 Docker 輕鬆掛機 Dawn 節點？本完整教學帶您快速部署 Dawn，分享閒置頻寬賺取積分與未來代幣（Points），參與 Web3 去中心化網路建設。內含最新的 Docker 運行指令與 Token 獲取步驟，打造穩定的被動收入來源。"
image: /assets/images/bot/dawn/banner.webp
written_by: "機掰雞"
lang: zh-TW
---

![Dawn 封面圖](/assets/images/bot/dawn/banner.webp)
> 📢 **【更新通知】**  
> 1.30 機掰雞的帳號被封到剩兩個,避免免費幫人打工,決定不掛Docker;剩下的乖乖掛Chrome
> 12.26 24號更新有點問題,還是10.02的版本,煩請再次更新一次,謝謝  
> 12.24 映像檔更新  
> 10.02 映像檔更新  
> 9.30 映像檔更新  

--- 

Dawn 是一個致力於打造去中心化無線網路的創新平台，讓用戶透過分享閒置的網路頻寬獲得被動收入，同時推動更公平、開放的網路生態系。以下是 Dawn 的主要特色：

---

## 🌐 Dawn 平台簡介與核心特色

### 🔗 去中心化頻寬分享

- Dawn 允許用戶將家中未使用的網路頻寬分享給他人，並可獲得 Dawn Points 作為回饋。
- 這種模式打破傳統網路服務商的壟斷，讓每個人都能參與成為網路供應的一環。

### 💡 簡易參與方式

- 使用者只需安裝 Dawn 的瀏覽器擴充功能、註冊帳號並提供必要資訊，即可開始分享頻寬並賺取點數。
- 整個流程簡單直覺，適合所有技術程度的使用者。

### 🏗️ 建立社區驅動的網路基礎設施

- Dawn 的願景是打造由社群共同維護的網路架構，並透過區塊鏈技術確保透明與安全。
- 這樣的模式能有效活用網路資源，並鼓勵更多人參與建設與維護。

### 💰 被動收入機會

- 分享頻寬可累積 Dawn Points，未來有機會兌換成代幣或其他獎勵形式。
- 推薦朋友加入平台還可獲得額外獎勵，擴大收入來源。

---

{% include warning.md %}

---

## 📝 註冊帳號

👉 [立即註冊 Dawn](https://dashboard.dawninternet.com/signup)

🎉 使用推薦碼 `0qt0wd9n`，**機掰雞可獲得額外雞飼料**，**不影響你的收益**。

📌 註冊後請安裝 Chrome 擴充套件並取得 Token（教學如下）。

---

## 🔗 連結

- 🌐 官方網站：[Dawn](https://www.dawninternet.com/)
- 🐳 Docker image：[78chicken/dawn](https://hub.docker.com/r/78chicken/dawn)

---

## 📄 準備 `tokens.json`

> 建立 `tokens.json` 檔案，內含你的 Email 與 Token（可支援多組帳號）：
>
> ```json
> [
>   {
>     "email": "你的email",
>     "userId": "User ID",
>     "sessionToken": "Session token" 
>   }
> ]
> ```

---

## 🔑 如何取得 Token？

1. 安裝 Chrome 擴充功能後，打開 `chrome://extensions/`。
2. 開啟「開發人員模式」。
3. 點選 Dawn 擴充圖示右鍵 →「檢查彈出視窗」。  
![Dawn token1](/assets/images/bot/dawn/img_1.webp)
4. 在 Application->Extension storage-> Local中找到userId與sessionToken。
![Dawn token2](/assets/images/bot/dawn/img_2.webp)
6. 若有多帳號，重複上述操作切換帳號擷取。

---

## 🐳 Docker 執行指令

```bash
# -v /opt/dawn/accounts.json 請換成你自己的路徑
docker run -d --restart always -m 50M \
--name Dawn \
-v /opt/dawn/tokens.json:/app/dawn/tokens.json \
docker.io/78chicken/dawn:latest
```
