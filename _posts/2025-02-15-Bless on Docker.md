---
title: "Bless DePIN 節點 Docker 教學：成功兌現空投，運行 AI 計算節點賺取代幣！"
date: 2025-09-24
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, DePIN, 虛擬貨幣, airdrop, 空投成功, 被動收入, Bless, AI 計算]
description: "Bless 是一個由 Binance Labs 校友創立的分散式 AI 計算平台。本教學提供完整的 Docker 掛機部署指令，教你如何獲取 Auth Token 與 PubKey，自動運行 Bless 節點。實測空投已成功兌現（機掰雞約 40U），是穩定參與 DePIN AI 基礎設施賺取代幣的優質選擇。"
image: /assets/images/bot/bless/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![Bless 封面圖](/assets/images/bot/bless/banner.webp)
> 📢 **【更新通知】**
>
> 可以領空投了，有資格的朋友趕快去領吧。機掰雞2帳號換到40U左右。


Bless 是一個由 Binance Labs 與 Akash Network 校友創立的分散式邊緣運算平台，旨在利用全球閒置的計算資源，打造去中心化的 AI 計算基礎設施。透過 Docker 部署，您可以輕鬆參與並獲取代幣獎勵。

## 📌 核心功能與特點

- **分散式邊緣運算**：利用個人設備的閒置計算能力，提供 AI 推理、資料處理等服務。
- **動態任務分配**：系統根據節點性能與地理位置，自動分配工作負載，確保高效運作。
- **WASM 安全執行環境**：採用 WebAssembly 技術，確保執行代碼的安全性與隔離性。
- **代幣經濟模型**：節點運營商可透過提供資源獲得 Bless 代幣，平台將用戶支付的代幣的 90% 分配給節點運營商。
- **無需專業設備**：任何人皆可參與，無需高效能機器或專業知識。

---

## 🎯 使用者價值

- **被動收入**：透過掛機貢獻計算資源，獲取 Bless 代幣。
- **參與未來基礎設施**：成為去中心化 AI 計算網絡的一部分。
- **促進資源共享**：有效利用閒置資源，降低整體計算成本。

---

## 📝 註冊帳號

👉 [立即註冊 Bless](https://bless.network/dashboard?ref=LK4GIH)

🎉 使用機掰雞的邀請連結可以獲得額外的「雞飼料」，你也會收到一些點數，不會影響自身收益！

---

## 🔗 連結

- 🌐 官方網站：[Bless Network](https://bless.network/dashboard)
- 🐳 Docker image：[78chicken/bless](https://hub.docker.com/r/78chicken/bless)
> **功能：** 自動啟動節點並連接至 Bless 網路，掛機賺取代幣

---

{% include warning.md %}

---

## 📁 運行前準備

請準備好 `accounts.json`，內容如下：
```json
[
  {
    "B7S_AUTH_TOKEN": "eyJhbG......Q9gcS4",
    "Nodes": [
      {
        "PubKey": "12D.....oCJ9PV",
        "HardwareId": "67a6....115c"
      }
    ]
  }
]
```
## 🔑 如何取得這些資訊？

1. 安裝 Chrome extension 並登入 Bless 帳號，系統會自動建立一個 Node
2. 在DashBoard -> 點選F12 -> Application -> Local Storage-> B7S_AUTH_TOKEN
![Bless img1](/assets/images/bot/bless/img_1.webp)
3. PubKey = Your Node ID
4. HardwareId 你可以自取一個唯一值

> ❗ **轉換小技巧**，保留上一份的設定,直接把Token = B7S_AUTH_TOKEN  
> PubKey沿用;若你有更舊的版本應該也有HardwareId,也可以拿來使用

---
   
## 🐳 Docker 執行方式
請根據你的實際檔案路徑替換 /opt/bless/accounts.json：

```bash
docker run -d --restart always -m 50M \
-v /opt/bless/accounts.json:/app/bless/accounts.json \
--name Bless \
docker.io/78chicken/bless:latest
```
