---
title: "DePINed Docker 掛機教學：免 KYC 參與去中心化任務，自動獲取代幣空投！"
date: 2025-06-16
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, DePIN, 去中心化, 空投, Web3, 任務平台, 免KYC]
description: "DePINed 是一個低門檻、免 KYC 的去中心化任務平台。本教學提供完整的 Docker 掛機部署指令，教你如何快速建立 DePINed 節點，自動化完成 Web3 任務，輕鬆賺取代幣與空投獎勵，打造穩定的被動收入來源。"
image: /assets/images/bot/depined/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![DePINed 封面圖](/assets/images/bot/depined/banner.webp)
> 📢 **【更新通知】**
>
> 映像檔更新,設定方式及名稱更新

DePINed 是一個結合區塊鏈與現實任務的去中心化任務平台，讓用戶能透過簡單的行動參與分潤與獎勵，打造人人都能參與的 Web3 去中心化經濟。

## 📌 核心功能與特點

- 📡 任務導向：透過完成各式任務（例如訓練模型、設備連線等）來獲得點數與代幣
- 🔒 隱私優先：強調數據保護與用戶匿名性，避免中心化風險
- 📈 去中心化經濟模型：任何人都能參與並貢獻，打造共識式社群平台
- ⚙️ 自動化節點掛機：透過設備持續連線來獲取空投及獎勵
- 🤖 無需高效能硬體或技術背景即可加入，適合所有人參與

---

## 🎯 使用者價值

- 一般用戶可透過「**掛機任務平台**」賺取代幣與空投
- 項目方與社群可透過 DePINed 平台獲取匿名化的參與數據
- 系統獎勵透明，基於區塊鏈發放回報，參與門檻低、潛力高

---

## 📝 註冊帳號

👉 [立即註冊 DePINed](https://app.depined.org/onboarding?ref=DE0qk2WAisJcGC)

🎉 使用機掰雞的介紹碼「`DE0qk2WAisJcGC`」可獲得額外的「雞飼料」，你的收益不會因此被扣減！

---

## 🔗 連結

- 🌐 官方網站：[DePINed](https://www.depined.org/)
- 🐳 Docker image：[78chicken/depined](https://hub.docker.com/r/78chicken/depined)

---

{% include warning.md %}

---

## 📁 運行前準備

請準備好 `tokens.json` 檔案，其內容格式如下（可支援多組帳號但建議每個 IP 只運行一組帳號）：
```json
[
    {
        "Email": "Your EMAIL",
        "accessToken": "eyJhbGciOiJIUzI1N........TFTMzaXuKZc"
    }
]
```
## 🐳 Docker 執行方式
請根據你的實際檔案路徑替換 /opt/depined/tokens.json：

```bash
docker run -d --restart always -m 50M \
--name DePINed \
-v /opt/depined/tokens.json:/app/depined/tokens.json \
docker.io/78chicken/depined:latest
```
