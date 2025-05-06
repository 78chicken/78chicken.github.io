---
title: "Repocket on Docker"
date: 2024-10-23
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, Paypal, USDT, 被動收入, 頻寬分享]
description: "使用 Docker 掛機部署 Repocket，透過分享頻寬方式獲取被動收入，支援 Paypal 與 USDT 出金，是簡單易用的流量變現工具。"
image: /assets/images/repocket/banner.png
written_by: 機掰雞
lang: zh-TW
---

![Repocket 封面圖](/assets/images/repocket/banner.png)

**Repocket** 是另一個熱門的掛機賺錢平台，透過分享你的網路流量來換取被動收入。相較於其他平台，Repocket 強調簡單安裝、透明獲利，適合任何閒置設備背景執行。

---

### 🧪 使用心得

> ⚠️ **機掰雞的實際經驗分享：**  
> 機掰雞曾在同一帳號下於不同設備上執行 Repocket，可能因此在出金時被系統認定違反官方規範，導致無法成功提領。加上本身所使用的是便宜的第四台網路，頻寬利用率偏低，實際收益有限。因此對這個項目的觀感較差(個人感受)。 
> 不過平台本身仍能正常運作，若你使用的是穩定且高頻寬的網路，仍可以考慮掛機賺取額外收入，只是請多加注意帳號使用規則與風險。

---

## 📝 註冊帳號

👉 [立即註冊 Repocket](https://link.repocket.com/UWh3)

🎉 使用機掰雞的邀請連結註冊，你會成為我的下線，**我將獲得你收入的 10% 作為飼料費**，但**不會影響你的收益**！

---

## 🔗 連結

- 🌐 官網：[https://repocket.co/](https://repocket.co/)
- 🐳 Docker Hub：[repocket/repocket](https://hub.docker.com/r/repocket/repocket)
> **功能：** 自動掛機、分享頻寬，適合 24/7 長時間執行

---

## 🐳 Docker 執行指令

```bash
# 參數：背景執行 / 使用 Host 網路 / 開機自動啟動 / 限制記憶體 / 帳號信箱
docker run -d --restart=always --replace -m 64M \
--name repocket \
-e RP_EMAIL=你的EMAIL \
repocket/repocket
```
