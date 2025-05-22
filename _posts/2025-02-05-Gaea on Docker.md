---
title: "Gaea on Docker"
date: 2025-02-05
updated: 2025-05-11
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣, 空投]
description: "透過 Docker 掛機 Gaea，轉換瀏覽器資源為收益，快速啟動僅需提供 token 與 browser_id。"
image: /assets/images/bot/gaea/banner.webp
written_by: "機掰雞"
lang: zh-TW
---

![Gaea 封面圖](/assets/images/bot/gaea/banner.webp)
> 📢 **【2025-05-11 更新通知】**
>
> 版本更新,設定檔變更,Docker image已更新
> 設定檔變更請參照下方JSON檔案  
> 
> 才剛更新完沒多就，機掰雞發現自己的三個帳號都被封了，真是無語問蒼天  
> 既然被封，維持機掰雞一貫作風，捨棄該項目不玩了 

**Gaea** 是一個基於瀏覽器的去中心化資源共享平台，用戶可以透過提交瀏覽器資源（如瀏覽行為模擬、網路請求等），來參與資料處理與流量任務，並獲得對應獎勵。無需下載應用，登入即可掛機。

---

## 🌟 Gaea 平台核心特色

### 🧠 去中心化 AI 資源共享
- Gaea 是一個去中心化的 AI 初創項目，致力於為開源 AI 提供可訪問的公共網絡數據資源。
- 用戶可透過貢獻瀏覽器資源，參與平台的資源共享，支持 AI 訓練與發展。

### 💻 無需插件，輕鬆掛機挖礦
- 無需下載任何插件，透過瀏覽器即可進行掛機挖礦。
- 系統自動完成連接配置，幫助用戶快速進入掛機狀態。

### 🎯 多元任務，積分獎勵
- **每日簽到**：每日登錄後完成簽到，可獲得積分獎勵。
- **社交任務**：完成關注官方社交帳號、分享推廣資訊等任務，獲得額外積分。
- **邀請好友**：透過邀請碼邀請好友註冊，雙方皆可獲得獎勵積分。

### 🎁 積分兌換空投與獎勵
- 用戶累積的積分可用於兌換 Gaea 項目的主網空投權益。
- 積分亦可用於兌換平台內的特殊道具或未來項目的升級獎勵。

---

## ⚠️ 注意事項

> - 平台非完全開源，請自行評估使用風險。
> - 建議每個帳號搭配獨立 IP，以降低封號風險。
> - 程式資源可能使用 CPU 或網路，建議監控用量。

---

## 📝 註冊帳號

👉 [立即註冊 Gaea](https://app.aigaea.net/register?ref=ga4XkSb1MLw506)

🎉 使用此推薦連結，**機掰雞可獲得額外雞飼料**，**不影響你的收益**。

---

## 🔗 連結

- 🌐 官方網站：[https://aigaea.net/](https://aigaea.net/)
- 🐳 Docker image：[78chicken/gaea](https://hub.docker.com/r/78chicken/gaea)

---

## ⚠️ 注意事項

> ❗ **此為非官方工具**，使用上請自行評估資安與帳號風險。
> 
> - 有被封號或資安風險   
> - 程式非機掰雞開發，僅加工為 Docker 映像以方便掛機部署。

---

## 📄 準備 `accounts.json`

> 建立 `accounts.json` 檔案，內容如下格式（支援多組帳號）：
> 
> - ⚠️ 建議一個 IP 僅對應一個帳號，降低封號風險。
> - Token大約7天需更新一次
```json
[
    {
      "browserId": "前八碼",
      "gaeaToken": "你的 Token"
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
![Gaea token](/assets/images/bot/gaea/img_1.webp)

---

## 🐳 Docker 執行指令
```bash
# -v /opt/gaea/accounts.json 請改成你自己的檔案路徑
docker run -d --restart always --replace -m 50M \
-v /opt/gaea/accounts.json:/app/gaea/accounts.json \
--name Gaea \
78chicken/gaea:latest
```
