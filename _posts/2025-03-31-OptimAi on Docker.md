---
title: "OptimAI on Docker"
date: 2025-03-31
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, AI, 去中心化]
description: "透過 Docker 掛機 OptimAI，只需提供帳號與 Token，即可參與 OP-Stack 上的 AI 計算網絡並獲得收益。"
image: /assets/images/bot/optimai/banner.png
written_by: "機掰雞"
lang: zh-TW
---

![OptimAI 封面圖](/assets/images/bot/optimai/banner.png)

[OptimAI Network](https://optimai.network/) 是一個基於 OP-Stack 的 Layer2 區塊鏈平台，專為生成式 AI（GenAI）代理提供支持，結合了去中心化物理基礎設施網絡（DePIN）與強化學習（RLHF）技術，致力於推動 AI 的下一波創新。

---

## 🚀 核心特色

### 1. EVM 相容的 Layer2 區塊鏈

- 基於 OP-Stack 架構，提供快速、低成本的交易體驗。
- 支援即時最終性（Instant Finality）與跨鏈互操作性。

### 2. 去中心化物理基礎設施網絡（DePIN）

- 建立一個去中心化的節點網絡，提供無限的頻寬、可擴展性與跨平台的運算能力。
- 用戶可透過貢獻計算資源與頻寬參與網絡，並獲得 OPI 代幣獎勵。

### 3. 數據挖掘與驗證

- 從群眾數據收集到可行的智慧，進行數據的標註與驗證，確保 AI 模型的高品質訓練資料。
- 社群共同參與數據的收集與驗證，提升資料的準確性與多樣性。

### 4. 強化學習與人類反饋（RLHF）

- 採用強化學習與人類反饋的方式，讓 AI 代理能夠從多樣化的數據中學習並適應新情境。
- 支援領域適應（Domain Adaptation）、遷移學習（Transfer Learning）、協同學習（Collaborative Learning）與聯邦學習（Federated Learning）。

### 5. 生成式 AI 代理（GenAI Agents）

- 推動個性化與無限可能的超級智慧時代，讓 AI 代理能夠自主學習與執行任務。
- 結合去中心化的數據與計算資源，實現真正的 AI 去中心化。

---

## 💡 如何參與

### 成為 OptimAI 節點

- 下載並運行 OptimAI 節點，貢獻你的設備資源，參與數據挖掘、驗證與強化學習。
- 節點類型包括：Lite Node、Core Node、Edge Node，支援多平台安裝（Chrome、Firefox、Opera 等）。

### 賺取 OPI 代幣

- 透過貢獻計算資源、頻寬與反饋，獲得 OPI 代幣獎勵。
- OPI 代幣可用於參與網絡治理、支付服務費用等。

---

## 📝 註冊帳號

👉 [立即註冊 OptimAI](https://node.optimai.network/register?ref=97E28114)

🎉 使用此推薦連結，**機掰雞可獲得額外雞飼料**，**不影響你的收益**。

---

## 🔗 連結

- 🌐 官方網站：[Optimai network](https://optimai.network/)
- 🐳 Docker image：[78chicken/optimai](https://hub.docker.com/r/78chicken/optimai)

---

## 📄 準備 `accounts.json`

> 建立 `accounts.json` 檔案，格式如下（支援多組帳號）：

```json
[
    {
        "refreshToken": "your_refresh_token_1",
        "registerPayload": "your_register_payload_1",
        "uptimePayload": "your_uptime_payload_1"
    }
]
```
--- 

## 🧪 Token 與 Payload 取得方式
1. refreshToken : Chrome → Dashboard → F12 → Application → Local Storage → opai_refresh_token
![OptimAI 封面圖](/assets/images/bot/optimai/img_1.png)
2. 取得 User ID 與 Device ID : Chrome → Dashboard → F12 → Network
   >- 找 me → Response → 取得 User ID
   >- 找 devices → Response → 取得 Device ID 
   
![OptimAI 封面圖](/assets/images/bot/optimai/img_2.png)
3. 產生 registerPayload 與 uptimePayload:  
Container 裡已含有 JS 腳本，但不含 NodeJS 執行環境，請依下列步驟將 JS 檔拷貝出來使用
```bash
# 啟動一個臨時 container（會自動結束）
docker run --rm --name temp docker.io/78chicken/optimai:latest

# 將 generate_payload.js 複製出來
docker cp temp:/app/optimai/generate_payload.js .

# 在本地執行（需先安裝 Node.js）
node generate_payload.js
```
執行後輸入 User ID 與 Device ID，會輸出兩組 Payload。  
Register Payload → 對應 registerPayload  
Uptime Payload → 對應 uptimePayload
![OptimAI 封面圖](/assets/images/bot/optimai/img_4.png)
---

## 🐳 Docker 執行指令
```bash
# 請將 /opt/optimai/accounts.json 改為你本機的 JSON 檔案路徑
docker run -d --restart always --replace  -m 50M \
-v /opt/optimai/accounts.json:/app/optimai/accounts.json \
--name OptimAi \
docker.io/78chicken/optimai:latest

```
