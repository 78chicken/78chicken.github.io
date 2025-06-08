---
title: "CenticQuests on Docker"
date: 2025-05-20
updated: 2025-06-08
categories: [quest]
tags: [Docker, 網路賺錢, 掛機, depin, 虛擬貨幣, airdrop, 空投, 被動收入]
description: "Centic 是一個 Web3 智能數據基礎設施平台，透過整合鏈上與鏈下資料，提供實體評分、行為洞察與成長分析，協助用戶與企業深入了解 Web3 生態系統。"
image: /assets/images/quest/centic/banner.webp
written_by: 機掰雞
lang: zh-TW
---
![DDAI 封面圖](/assets/images/quest/centic/banner.webp)
> 📢 **【2025-06-08 更新通知】**
>
> 映像檔更新
# CenticQuests 簡介

**Centic** 是一個 Web3 智能數據基礎設施平台，致力於將來自區塊鏈網路的原始資料轉化為可操作的智能資訊。透過整合鏈上（如交易、合約、地址）與鏈下（如社交媒體、新聞、市場數據）資料，Centic 為用戶提供全面的 Web3 實體洞察與評分系統。

---

## 🌟 核心特色

- **智能資料層**  
  將多種區塊鏈網路的原始資料轉化為智能資訊，革新資料的貢獻與整合方式。

- **實體評分系統**  
  提供全面的評估系統，追蹤、分析並展示整個區塊鏈實體（如錢包、協議、代幣）的表現，協助用戶做出正確的投資決策。

- **鏈上與鏈下資料整合**  
  無縫存取各種鏈上和鏈下資料，探索有價值的洞察，包括標準化的鏈上資料（區塊、交易、事件）和鏈下資料（社交媒體、市場數據、瀏覽器）。

- **知識圖譜建構**  
  分析、聚合並豐富原始資料，建立由實體及其關係組成的知識圖譜，提供更深入的資料洞察。

- **用戶成長分析**  
  提供分析和智能，協助企業擴展用戶基礎，包括 DApp 成長、行銷自動化和 Web3 參與等解決方案。

---
## 📝 註冊帳號

👉 [立即註冊 CenticQuests](https://centic.io/quests/daily?refferalCode=eJwFwQcBACAIBMBKIkviMN4MxvduPWc2drRVAiBRkq40pqtRJ2M29rj6B_9XC9E=)

🎉 使用機掰雞的邀請連結可以獲得額外的「雞飼料」，你也會收到一些點數，不會影響自身收益！

---
## 🔗 連結

- 🌐 官方網站：[Centic](https://centic.io/)
- 🐳 Docker image：[78chicken/centic](https://hub.docker.com/r/78chicken/centic)

--- 

{% include warning.md %}

---

## 📁 運行前準備

在開始掛機任務前，請先準備好一個名為 `accounts.txt` 的文字檔案，內容格式如下：

- 每行一個 **Private Key**
- 建議使用子帳號私鑰，避免主帳號資安風險
- 如何取得 Private Key 請參考這篇教學 👉 [取得你的 Private Key](/posts/Get-Your-Private-Key/)

📄 範例內容：
```txt
2b9ed18e0b60369dbb...
0xfedcba0987654321...
```


## 🐳 Docker 執行方式

請根據你的實際檔案路徑替換 `/opt/centic/accounts.txt`：
```bash
docker run -d --restart always --replace -m 50M \  
  -v /opt/centic/accounts.txt:/app/centic/accounts.txt \
  --name CenticQuests \
  docker.io/78chicken/centic:latest
```
{% include quest-note.md %}
