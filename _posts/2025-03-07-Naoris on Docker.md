---
title: "Naoris Protocol on Docker"
date: 2025-03-07
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣, 空投]
description: "透過 Docker 掛機 Naoris Protocol，參與去中心化資安網絡並賺取點數，只需錢包與裝置資訊即可輕鬆啟動。"
image: /assets/images/naoris/banner.png
written_by: "機掰雞"
lang: zh-TW
---

![Naoris 封面圖](/assets/images/naoris/banner.png)

**Naoris Protocol** 是一個致力於打造去中心化資安網路的項目，用戶可透過貢獻裝置資源來強化整體網路安全，並獲得獎勵。只需註冊帳號、錢包與瀏覽器擴充套件，即可參與。

---

## 🌟 Naoris 平台核心特色

### 🔐 分散式資安網路（DINA）
- 打造全球最大規模的分散式資安網絡。
- 每個裝置同時是節點也是驗證者，協助檢測與減緩資安風險。

### 🤝 社群驅動安全模型
- 每個用戶都是「信任單元」，形成去中心化的信任架構。
- 利用裝置訊號與網路活動評估信任狀態，提升整體網路安全性。

### 💰 獎勵機制與點數系統
- 參與裝置連線與驗證貢獻，可累積點數，未來可兌換代幣與獎勵。
- 推薦好友可獲得額外獎勵。

### 🛠️ 開源工具與擴充應用
- 提供 Chrome 擴充套件與錢包，無需額外安裝應用。
- 使用 Docker 快速啟動掛機流程，簡單方便。

---

## ⚠️ 注意事項

> - 此工具為非官方版本，使用上請自行評估資安與帳號風險。
> - Chrome Extension 的「Protection 開關」若開啟，會影響某些網站瀏覽，請善用白名單功能。
> - 本專案 Docker 映像僅為機掰雞自行封裝，非 Naoris 官方開發。

---

## 📝 註冊帳號與安裝工具

1. 註冊帳號：👉 [立即註冊 Naoris](https://naorisprotocol.network/testnet)
2. 安裝錢包與插件：
  - Naoris Wallet（瀏覽器錢包擴充套件）
  - Naoris Chrome Extension
3. 使用推薦碼：`6AmjMBS9DIJuT1CB`（機掰雞可獲得雞飼料，不影響你收益）

---

## 📄 準備 `accounts.json`

> 建立 `accounts.json` 檔案，內容格式如下：

```json
[
  {
    "Address": "0x7919fb7e......207b9",
    "deviceHash": "60.....32"
  }
]
```
--- 

## 🔍 如何取得 deviceHash
1. 安裝 Naoris Wallet 與 Chrome Extension。
2. 進入 Dashboard 頁面，按下 F12。
3. 前往 Application → ExtensionStorage → Naoris Protocol Wallet。
4. 找到 Local → deviceHash 欄位並複製。
![Naoris hash](/assets/images/naoris/img_1.png)
---

## 🐳 Docker 執行指令
```bash
# -v /opt/naoris/accounts.json 請改成你自己的檔案路徑
docker run -d --restart always --replace -m 50M \
-v /opt/naoris/accounts.json:/app/naoris/accounts.json \
--name Naoris \
docker.io/78chicken/naoris:latest
```
