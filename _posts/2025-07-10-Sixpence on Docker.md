---
title: "⚠️Sixpence on Docker-使用Wallet PK"
date: 2025-07-10
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣, 空投]
description: "Sixpence AI（原名 OpenLayer）是一個去中心化瀏覽器網絡，連接 AI agents 與人類網際網路，平台運行依賴全球用戶貢獻的瀏覽器資源，並透過 Chrome 擴充功能參與貢獻可賺取點數。"
image: /assets/images/bot/sixpence/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![Sixpence AI 封面圖](/assets/images/bot/sixpence/banner.webp)

## Sixpence AI 簡介

**Sixpence AI**（前身為 **OpenLayer**）是一個結合去中心化實體基礎設施網絡（DePIN）與 AI training 的項目，致力打造一個全球分布式瀏覽器網絡，讓 AI agents 能像真人一樣登入、互動、擷取資訊，包括經過認證的社群平台內容，並具備 JavaScript 渲染能力 :contentReference[oaicite:1]{index=1}。

---

## 核心特色

- **全球分散式瀏覽器網絡**  
  用戶貢獻自己的瀏覽器資源和頻寬，成為「節點」，使 AI agents 能模擬真人正常操作網頁環境 :contentReference[oaicite:2]{index=2}。

- **Chrome 擴充功能生態**  
  透過官方 Chrome 插件（原名 OpenLayer extension），用戶可以提交計算資源、網路頻寬與自願提供的數據，同時完成每日任務、追蹤進度與邀請好友參與 :contentReference[oaicite:3]{index=3}。

- **高度隱私及資料控制**  
  擴充功能強調不會販售用戶資料，且開發者保證不會用於信用評分等未授權用途 :contentReference[oaicite:4]{index=4}。

- **點數與未來空投機制**  
  使用者使用擴充功能獲得「Extension Points」，累積越多點數，未來可能參與代幣空投、DePIN 獎勵或被動收入計畫 :contentReference[oaicite:5]{index=5}。

- **即時且真實的操作模擬**  
  借助參與者瀏覽器，Sixpence 能達成 sub‑second 回應速度的網頁操作，協助 AI 快速存取動態內容區塊 :contentReference[oaicite:6]{index=6}。

---

## 📝 註冊與節點設置

👉 [立即下載 SixPence Extension](https://chromewebstore.google.com/detail/sixpence-prev-openlayer/bcakokeeafaehcajfkajcpbdkfnoahlh?hl=en-US&utm_source=ext_sidebar)

🎉 使用機掰雞的介紹碼「`9Y3OJX`」可獲得額外的「雞飼料」，你的收益不會因此被扣減！

---
## 🔗 連結

- 🌐 官方網站：[https://sixpence.ai](https://sixpence.ai)
- 🐳 Docker image：[78chicken/sixpence](https://hub.docker.com/r/78chicken/sixpence)

---

{% include warning.md %}

---

{% include privatekey-note.md %}

---
🐳 Docker 執行方式
請根據您的實際檔案路徑替換 /opt/sixpence/accounts.txt：

```bash
docker run -d --restart always -m 50M \
  -v /opt/sixpence/accounts.txt:/app/sixpence/accounts.txt \
  --name SixPence \
  docker.io/78chicken/sixpence:latest
```

