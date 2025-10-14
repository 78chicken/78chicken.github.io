---
title: "⚠️KiteAi on Docker-使用Wallet PK"
date: 2025-07-18
categories: [quest]
tags: [AI, 區塊鏈, 空投, 去中心化, 自動化, 被動收入]
description: "參與 Kite AI 激勵測試網，探索去中心化 AI 經濟，完成任務獲得代幣獎勵。"
image: /assets/images/quest/kiteai/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![Kite AI 空投封面圖](/assets/images/quest/kiteai/banner.webp)

> 📢 **【更新通知】**
>
> 映像檔更新

Kite AI 是一個專為人工智慧（AI）設計的主權 Layer-1 區塊鏈，旨在實現數據、模型與智能體之間的公平透明協作。透過創新的 PoAI（Proof of Attributed Intelligence）共識機制，確保所有貢獻者的公平歸因與透明獎勵。

---

## 🌟 核心功能與特色

- **PoAI 共識機制**  
  Kite AI 採用 PoAI 共識機制，追蹤並獎勵數據、模型與智能體的貢獻，確保 AI 經濟中的公平性與透明度。

- **EVM 相容性**  
  Kite AI 與以太坊虛擬機（EVM）相容，開發者可以輕鬆部署智能合約，擴展應用場景。

- **去中心化 AI 市場**  
  提供開放的市場，讓數據提供者、模型開發者與 AI 代理能夠公平交易與協作，促進 AI 資產的去信任交換。

- **模組化子網架構**  
  Kite AI 的子網架構允許為特定 AI 應用程式定製區塊鏈解決方案，提升可擴展性與效率。

---

## 📝 註冊帳號

👉 [立即註冊 Kite AI](https://testnet.gokite.ai?referralCode=7DIJ35MW)

🎉 使用機掰雞的邀請連結註冊後，**我將獲得你收益的一點點雞飼料作為回饋**（不影響你的收益）。

---

## 🔗 連結

- 🌐 官方網站：[Kite.Ai](https://gokite.ai)
- 🐳 Docker image：[78chicken/bless](https://hub.docker.com/r/78chicken/kiteai)

---

{% include warning.md %}

---
## 📁 運行前準備

請準備好 `accounts.txt`，內容如下：
```txt
your_evm(EOA)_address_1
EX:
0x733637......2e2d757
```
---

## 🐳 Docker 執行方式
請根據你的實際檔案路徑替換 /opt/kiteai/accounts.txt：

```bash
docker run -d --restart always -m 50M \
-v /opt/kiteai/accounts.txt:/app/kiteai/accounts.txt \
--name KiteAi \
docker.io/78chicken/kiteai:latest
```
---

{% include quest-note.md %}
