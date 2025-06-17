---
title: "Honeygain Auto-Claim on Docker"
date: 2024-06-07
categories: [tool]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 自動化, JWT]
description: "使用 Docker 部署 Honeygain 每日自動領獎腳本，支援 JWT 登入，獲取完獎勵即退出，適合多帳號與無頭裝置使用。"
image: /assets/images/tool/honeygain_claim/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![Honeygain 自動領獎封面圖](/assets/images/tool/honeygain_claim/banner.webp)

這是一個 Honeygain 每日獎勵自動獲取的機器人，當你有多個帳號時會特別有幫助。市面上有許多類似的版本，有的是使用帳號/密碼登入，有的則是使用 Token 登入。  
機掰雞使用的是 **JWT Token 登入方式**。

原因在於使用帳號密碼登入時，CPU 負擔較大，有些腳本會一直執行等 24 小時再自動領獎，這樣對使用者來說並沒有比較方便。  
而這款推薦的版本，在領完每日獎勵後就會自動結束，非常適合搭配排程來使用。

---

## 🔗 參考資料

- 🌐 GitHub：[MrLoLf/HoneygainAutoClaim](https://github.com/MrLoLf/HoneygainAutoClaim)
- 🐳 Docker image：[mrlolf/honeygainautoclaim](https://hub.docker.com/r/mrlolf/honeygainautoclaim)

---

## 🔐 如何取得 JWT Token

1. 使用 Chrome 瀏覽器登入 [Honeygain 官網](https://dashboard.honeygain.com/)
2. 按下 `F12` 打開開發者工具
3. 點選 `Application` 分頁
4. 找到左側的 `Storage → Local Storage → https://dashboard.honeygain.com`
5. 搜尋 `dashboard_` 開頭的項目，並找到 `JWT` 欄位，即為你的 Token
![Honeygain jwt](/assets/images/tool/honeygain_claim/img_1.webp)
---

## 🐳 Docker 執行指令

```bash
docker run -d --rm -m 256m \
-e JWT_TOKEN="你的JWT Token" \
mrlolf/honeygainautoclaim
```
