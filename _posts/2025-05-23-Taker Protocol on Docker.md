---
title: "Taker Protocol on Docker"
date: 2025-05-23
updated: 2025-05-29
categories: [quest]
tags: [Docker, 空投, 掛機, 被動收入, 虛擬貨幣, 自動化]
description: "參與 Taker Lite Mining 空投活動，完成每日任務與掛機任務，賺取 TAKER 代幣。"
image: /assets/images/quest/taker/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![Taker 空投封面圖](/assets/images/quest/taker/banner.webp)
> 📢 **【2025-05-29 更新通知】**
>
> 版本更新

Taker 是一個專注於比特幣流動性的區塊鏈協議，透過創新的 NPOL（Nominated Proof-of-Liquidity）共識機制，將流動性提供者的激勵與生態系統的成長結合，打造一個去中心化且高效的比特幣激勵層。用戶可以透過參與 Lite Mining 空投活動，完成每日任務與掛機任務，賺取 TAKER 代幣。

---

## 🌟 核心功能與特色

- **NPOL 共識機制**  
  Taker 採用 Nominated Proof-of-Liquidity 共識機制，鼓勵用戶提供流動性，並透過提名系統選出驗證者，確保網路的安全與去中心化。

- **跨鏈橋接技術**  
  利用 DHC（Dynamic Hidden Committee）技術，實現安全且高效的跨鏈資產轉移，支持 BTC、ETH 等主流區塊鏈。

- **EVM 相容性**  
  Taker 支援以太坊虛擬機（EVM），開發者可以輕鬆部署智能合約，擴展應用場景。

- **去中心化交易所（DEX）**  
  Taker Swap 是 Taker 協議的原生 DEX，採用 AMM 機制，提供高效的資產交換與流動性挖礦機會。

---

## 📝 註冊帳號

👉 [立即註冊 Taker](https://earn.taker.xyz?start=82KK8)

🎉 使用機掰雞的邀請連結註冊後，**我將獲得你收益的一點點雞飼料作為回饋**（不影響你的收益）。

---

## 🔗 連結

- 🌐 官方網站：[https://taker.xyz](https://taker.xyz)
- 🐳 Docker image：[78chicken/taker](https://hub.docker.com/r/78chicken/takerprotocol)

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
---

## 🐳 Docker 執行方式

請根據你的實際檔案路徑替換 `/opt/taker/accounts.txt`：
```bash
docker run -d --restart always --replace -m 50M \  
  -v /opt/takerprotocol/accounts.txt:/app/takerprotocol/accounts.txt \
  --name TakerProtocol \
  docker.io/78chicken/takerprotocol:latest
```
{% include quest-note.md %}
