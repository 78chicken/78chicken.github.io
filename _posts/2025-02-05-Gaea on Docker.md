---
title: "Gaea on Docker"
date: 2025-02-05
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣, 空投]
description: "透過 Docker 掛機 Gaea，轉換瀏覽器資源為收益，快速啟動僅需提供 token 與 browser_id。"
image: /assets/images/gaea/banner.png
written_by: "機掰雞"
lang: zh-TW
---

![Gaea 封面圖](/assets/images/gaea/banner.png)

**Gaea** 是一個透過瀏覽器資源參與的平台，用戶可提交 browser_id 與 token 掛機換取回饋。本文介紹如何以 Docker 快速部署自動化版本。

---

## 🌟 核心特色

### 🛡️ 快速啟動，自由掌控
- 僅需提供 browser_id 與 token。
- 可自行控制執行環境與更新頻率。

### 💰 輕鬆掛機，資源換取回報
- 適用於閒置設備，低資源消耗。
- Token 每 7 天更新一次，使用者可自行維護。

---

## 📝 註冊帳號

👉 [立即註冊 Gaea](https://app.aigaea.net/register?ref=ga4XkSb1MLw506)

🎉 使用此推薦連結，**機掰雞可獲得額外雞飼料**，**不影響你的收益**。

---

## 🔗 連結

- 🌐 官方網站：[https://aigaea.net/](https://aigaea.net/)
- 🐳 Docker Hub：[78chicken/gaea](https://hub.docker.com/r/78chicken/gaea)

---

## ⚠️ 注意事項

> ❗ **此為非官方工具**，使用上請自行評估資安與帳號風險。
>
> 程式非機掰雞開發，僅加工為 Docker 映像以方便掛機部署。

---

## 📄 準備 `accounts.json`

> 建立 `accounts.json` 檔案，內容如下格式（支援多組帳號）：
> 
> ⚠️ 建議一個 IP 僅對應一個帳號，降低封號風險。
```json
[
  {
    "Browser_ID": "前八碼",
    "Token": "你的 Token"
  }
]
```
---

## 🔍 如何取得 Browser_ID 與 Token？
1. 使用 Chrome 登入 Gaea。
2. 按下 F12 → 前往 Application。
3. 點選左側 Local Storage。
4. 找到 browser_id 與 gaea_token。
5. Browser_ID 取前八碼，Token 複製整段。
![Gaea token](/assets/images/gaea/img_1.png)

---

## 📁 Docker 執行方式
```bash
# -v /opt/gaea/accounts.json 請改成你自己的檔案路徑
docker run -d --restart always --replace -m 50M \
-v /opt/gaea/accounts.json:/app/gaea/accounts.json \
--name Gaea \
78chicken/gaea:latest
```
