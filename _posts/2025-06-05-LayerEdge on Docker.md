---
title: "LayerEdge on Docker"
date: 2025-06-05
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, depin, 虛擬貨幣, airdrop, 空投, 被動收入]
description: "LayerEdge 是一個去中心化的模組化區塊鏈平台，透過零知識證明（ZK）與 BitVM 技術，將比特幣網絡轉變為支持 AI、DePIN 等應用的去中心化超級計算機。"
image: /assets/images/bot/layeredge/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![LayerEdge 封面圖](/assets/images/bot/layeredge/banner.webp)

## LayerEdge Network 簡介

**LayerEdge Network** 是一個去中心化的模組化區塊鏈平台，旨在透過零知識證明（ZK）與 BitVM 技術，將比特幣網絡轉變為支持 AI、DePIN 等應用的去中心化超級計算機。該平台允許用戶利用閒置設備資源參與驗證，並獲得獎勵，實現真正的「人民驅動」網絡。

---

## 核心特色

- **去中心化驗證層**  
  利用 ZK 技術，將用戶設備轉變為輕量級驗證節點，實現大規模的去中心化驗證網絡。

- **模組化架構**  
  將共識、執行和數據可用性分成不同模組，開發者可自由組合模組以滿足不同需求。

- **跨鏈兼容性**  
  支援比特幣、以太坊等主流區塊鏈，推動資料與資源自由流通。

- **社群參與與獎勵**  
  用戶可透過運行節點貢獻運算資源並獲得 EDGE 代幣獎勵。

---

## 📝 註冊帳號

👉 [立即註冊 LayerEdge](https://dashboard.layeredge.io/?ref=xFXGr6E6)  
🎉 推薦碼：`xFXGr6E6`

使用機掰雞的推薦碼註冊可獲得額外獎勵，你也會收到一些點數，完全不影響自身收益！

---

## 🔗 連結

- 🌐 官方網站：[https://layeredge.io/](https://layeredge.io/)
- 📚 使用者儀表板：[https://dashboard.layeredge.io/](https://dashboard.layeredge.io/)
- 🐳 Docker 映像檔：[78chicken/layeredge](https://hub.docker.com/r/78chicken/layeredge)

---

{% include warning.md %}

---

## 📁 運行前準備

請前往 LayerEdge 儀表板的 `Overview` 頁面，點選按鈕，產生您的驗證碼，並儲存為 `tokens.txt`。

```txt
eyJ0eXAiOiJKV1QiLCJhbGciOi...RZzE6Z7qH8
```
OverView頁面點選按鈕產生token
![LayerEdge 封面圖](/assets/images/bot/layeredge/img_1.webp)

---

🐳 Docker 執行方式
請根據您的實際檔案路徑替換 /opt/layeredge/tokens.txt：

```bash
docker run -d --restart always --replace -m 50M \
  -v /opt/layeredge/tokens.txt:/app/layeredge/tokens.txt \
  --name LayerEdge \
  docker.io/78chicken/layeredge:latest
```
