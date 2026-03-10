---
title: "DeltaHash 掛機解析：AI 算力共享平台是新機會還是新礦坑？"
date: 2026-03-10
categories: [bot]
tags: [網路賺錢, 掛機, 被動收入, DeltaHash, DePIN, AI算力]
description: "DeltaHash 是一個主打 AI 分散式算力的 DePIN 平台，允許使用者貢獻 CPU / GPU / RAM 來獲得 $DTH 代幣。本篇整理其運作模式、特色與潛在風險，並分析是否值得掛機。"
image: /assets/images/bot/deltahash/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![DeltaHash 封面圖](/assets/images/bot/deltahash/banner.webp)


DeltaHash 是一個主打 **AI 分散式算力（Decentralized Compute）** 的平台，  
允許使用者把電腦或手機的閒置資源（CPU、GPU、RAM）提供給網路使用，並獲得平台代幣 **$DTH** 作為回報。

這類模式其實和 **DePIN（Decentralized Physical Infrastructure Network）** 概念相似，例如：

- AI 算力共享
- GPU / RAM 分散式運算
- 分散式雲端運算

簡單說，就是把全球用戶的裝置組成一個 **大型 AI 計算網路**。
  
DeltaHash 是近期在 X / Telegram 上開始宣傳的 DePIN 專案。    
目前仍在早期階段，資訊並不算完整，建議抱持 **測試與觀望心態**。低成本測試，不要投入資金。

---

## 🧠 DeltaHash 是怎麼運作的？（How It Works）

根據官方說明，DeltaHash 的基本流程如下：

1. 使用者註冊帳號並連接設備
2. 設備開始貢獻 CPU / GPU / RAM 資源
3. 這些算力被用於 AI 基礎設施運算
4. 系統依據設備穩定度與貢獻度分配 $DTH 代幣
5. 未來預計在 TGE（Token Generation Event）後可以交易

官方宣稱：

- 任何設備都可以參與（PC 或手機）
- 算力貢獻越穩定收益越高
- 每個 Epoch（約 5 分鐘）計算一次獎勵

---


### 💰 代幣挖礦機制

平台代幣為 **$DTH**

目前資訊：

- 總供應量：1,000,000,000
- 預計 TGE：2026 Q2
- 挖礦收益：0.1 – 0.3 $DTH / 分鐘（官方宣稱）

實際價值仍未知。

---

### 🤝 推薦獎勵

官方提供推薦機制：

- 推薦獎勵約 **20%**
- 推薦新用戶可獲得額外 $DTH

這也是目前社群推廣的主要方式。

---

{% include warning.md %}

---


## ⚠️ DeltaHash 的缺點與風險

### 1️⃣ 專案非常新

DeltaHash 的網域 **2026 年 2 月才建立**。 

代表：

- 歷史非常短
- 幾乎沒有長期用戶回饋

---

### 2️⃣ 團隊資訊不透明

目前公開資訊中：

- 團隊成員不明
- 公司註冊資訊不明
- Whitepaper 不完整

WHOIS 資訊也被隱藏。 

這在 Web3 專案中是 **風險指標之一**。

---

### 3️⃣ 網站信任度偏低

部分網站風險評估：

- 信任分數約 **14.7 / 100**
- 被標記為 **高風險網站** 

主要原因：

- 網站太新
- 身分資訊隱藏
- 流量非常低

---

### 4️⃣ 收益尚未驗證

目前：

- $DTH 還沒上市
- 收益只是帳面數字
- 沒有實際出金案例

所以要當作 **測試型項目**。

---
## 📝 註冊帳號

👉 [立即註冊 DelteHash](https://portal.deltahash.ai?ref=DELTA-834D10)  
**機掰雞可獲得額外雞飼料**，**不影響你的收益**。

---

## 🔗 連結
- 🌐 官方網站：[DeltaHash](https://deltahash.ai/)
- 🐳 Docker image：[78chicken/deltahash](https://hub.docker.com/r/78chicken/deltahash)
- 使用 X / Google 帳號登入使用 
- 🐦 X：https://x.com/deltahash_ai
- 📢 Telegram：https://t.me/deltahash_ai 
---

## 📄 準備 `cookies.txt`

> 內容就一行, Header -> Cookie -> 擷取以下資訊 (最後的;可有可無)
> ```txt
> connect.sid=s%3APiPPxM0ayK...........agvOYzR2aY;
> ```
---

## 🔑 如何取得 Cookies？

1. Chrome 點選F12。
2. CTRL+R重刷DashBoard頁面。
3. 找到me -> Header -> Cookie -> 找到connect.sid。  
   ![DeltaHash Cookies](/assets/images/bot/deltahash/img_1.webp)

---
## 🐳 Docker 執行指令

```bash
# -v /opt/deltahash/cookies.txt 請換成你自己的路徑
docker run -d --restart always -m 50M \
--name DeltaHash \
-v /opt/deltahash/cookies.txt:/app/deltahash/cookies.txt \
docker.io/78chicken/deltahash:latest
```
