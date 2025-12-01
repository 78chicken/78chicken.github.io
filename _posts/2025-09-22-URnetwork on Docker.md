---
title: "URnetwork Docker 掛機教學：告別傳統 VPN，打造去中心化被動收入節點！"
date: 2025-11-30
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 虛擬貨幣, 被動收入, VPN 替代方案, URnetwork, USDC]
description: "想利用閒置網路頻寬賺取被動收入？本教學深入解析 URnetwork（ur.io）如何透過 Docker 建立去中心化節點，告別傳統 VPN 限制，安全賺取 USDC 穩定幣。了解收益計算、支付機制與 Docker 快速部署步驟。"
image: /assets/images/bot/urnetwork/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![URnetwork 封面圖](/assets/images/bot/urnetwork/banner.webp)

強調「告別 VPN！」的理念。換句話説，不完全是傳統 VPN，而是類似私人網路（Private Network）或去中心化節點網絡，用戶可透過節點連接，獲得類似本地網路的體驗。

> 📢 **【更新通知】**  
> 11.30 最近幾個禮拜都有收到USDC,雖然都少於1USDC,但至少有付錢;機掰雞在此就不附上貼圖了  
> 11.3 新增付款證明-4USDC  
> 10.2 介紹更新
---
## 💵 付款證明
收到4USDC
![URnetwork 付款證明](/assets/images/bot/urnetwork/img_1.webp)  

## 🧠 核心功能與特色

- 適合重視 **網路隱私**、想避免 VPN 被封鎖或監控的使用者
- 希望有國際節點或低延遲、連線品質穩定的網路體驗
- 想要在以節點為主的網絡中自由切換，像在本地網路一樣上網

---

## 📝 註冊帳號

👉 [立即註冊 URnetwork](https://ur.io/c?bonus=2AV5EX)

🎉 請多多使用機掰雞的邀請連結，感恩！

---
## 💵 獎勵機制（收益怎麼算）

URnetwork 採用的是 **社群分潤 + 補貼機制**，主要依據以下幾個因素來計算你能得到多少獎勵：

| 🏷️ 項目 | 📌 說明 |
|---------|--------|
| 💰 獎勵來源比例 | URnetwork 會從 premium 收入中撥出 **10% 作為補貼給網絡**，並且加上其他的收益分享機制。 |
| 🛡️ 最低保證 | 每位月活躍用戶（MAU, Monthly Active User）都有最低保證金額：**0.10 美元（或等值）**。 |
| 📡 數據流量權重 | 實際派息金額會依據設備所路由（relay / 轉發）的流量來決定。**流量越多，獎勵越多**。 |
| 🌍 國家與全球分配比例 | 獎勵計算中，**75% 的權重**來自全球比較，**25% 來自所在國家比較**。換句話說：你的表現同時與國內外節點對比。 |
| 👥 推薦獎金 | 當你推薦他人加入時，可獲得被推薦者收益的一部分：**50% 的收益 + 50% 的推薦獎金**。 |
| 📆 支付時間與結算方式 | 獎勵為 **每週結算一次**，依據「上週 premium 收入」及「上月 MAU 數量」計算。 |
| 🪙 支付幣種 / 錢包 | 獎勵以 **USDC（穩定幣）**發放，支援 **Polygon** 或 **Solana** 錢包。 |
| ⛽ 手續費 / gas 費 | 發放獎勵時會扣除鏈上交易（gas）費用，若累積獎勵扣除後仍為正值，才會真正發放。 |

---

### 📌 總結
**URnetwork 會將 Premium 收入的一部分回饋給幫忙運營網絡、提供頻寬與流量的使用者。**

---

## 💵 付款狀況
- ✅ 已確認收到 **0.2 USDC** 1次。
- 📱 必須下載手機 APP 才能設定 **Solana Wallet** 與 **Refer URL**。
- 🛠️ 進階用戶：也可以透過 **API 呼叫** 自行設定。
---

## 🔗 官方連結

- 🌐 官方網站：[URnetwork](https://ur.io/)
- 🐳 Docker image：ghcr.io/techroy23/docker-urnetwork:latest  

---

{% include warning.md %}

---

## 🐳 Docker 執行方式
請根據你的實際檔案路徑替換 /opt/bless/accounts.json：

```bash
docker run -d --platform linux/amd64 \
  -m 64m \ 
  --name="URnetwork" \
  --restart="always" \  
  --cap-add NET_ADMIN \
  -e USER_AUTH="Your-Email@here.com" \
  -e PASSWORD="YourPassword" \    
  -p 8080:8080 \
  ghcr.io/techroy23/docker-urnetwork:latest  
```
