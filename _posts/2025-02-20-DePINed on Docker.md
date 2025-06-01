---
title: "DePINed on Docker"
date: 2025-02-20
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, depin, 去中心化, 空投]
description: "使用 Docker 快速部署 DePINed 節點，參與去中心化任務平台，自動化獲取代幣與空投獎勵，無需 KYC 或高效能設備即可加入。"
image: /assets/images/bot/depined/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![DePINed 封面圖](/assets/images/bot/depined/banner.webp)
> 📢 **【2025-06-01 更新通知】**
>
> 映像檔更新

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

請準備好 `accounts.json` 檔案，其內容格式如下（可支援多組帳號但建議每個 IP 只運行一組帳號）：
```json
[
    {
        "Email": "你的EMAIL",
        "Password": "你的密碼"
    }
]
```
## 🐳 Docker 執行方式
請根據你的實際檔案路徑替換 /opt/depined/accounts.json：

```bash
docker run -d --restart always -m 50M \
--name DePINed \
-v /opt/depined/accounts.json:/app/depined/accounts.json \
docker.io/78chicken/depined:latest
```
