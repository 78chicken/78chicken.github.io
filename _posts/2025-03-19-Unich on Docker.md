---
title: "Unich on Docker"
date: 2025-03-19
categories: [quest]
tags: [Docker, 空投, 掛機, 被動收入, 虛擬貨幣, 自動化]
description: "參與 Unich 空投活動，完成每日任務與 Tap-to-Earn 掛機任務，賺取 Freedom Points 並兌換 UN 代幣。"
image: /assets/images/quest/unich/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![Unich 空投封面圖](/assets/images/quest/unich/banner.webp)

Unich是一個基於區塊鏈技術的一站式場外交易（OTC）平台，專注於加密貨幣交易。
讓用戶能夠更早參與新興代幣的交易，並通過其空投計劃（Airdrop Program）吸引用戶參與。空投活動中，
用戶可以通過完成任務獲得「Freedom Points (FD Points)」，這些點數最終將轉換為平台代幣 $UN。

---

## 🌟 核心功能與特色

- Pre-Market OTC（預上市交易）  
  允許用戶在代幣正式上市前進行交易，無需資產鎖倉，透過智能合約確保交易安全與透明。
- Point-Market OTC（點對點市場）
  提供即時的P2P交易環境，適合需要快速完成大額交易的用戶，避免對公開市場價格造成影響。
- Options OTC Market（期權市場）
  支持加密貨幣期權的場外交易，為用戶提供更多元的交易策略選擇。




## 📝 註冊帳號

👉 [立即註冊 Unich](https://unich.com/en/airdrop/sign-up?ref=D2W614)

🎉 使用機掰雞的邀請連結註冊後，**我將獲得你收益的一點點雞飼料作為回饋**（不影響你的收益）。

---

## 🔗 連結

- 🌐 官方網站：[https://unich.com/en](https://unich.com/en)
- 🐳 Docker image：[78chicken/unich](https://hub.docker.com/r/78chicken/unich)

---

{% include warning.md %}

---

## 📦 準備 token.txt

運行前請先準備好 `token.txt`，內容為你的 Unich 登入 Token。取得方法如下：

1. 註冊並登入後，點右上角 **My Earning**
2. 按下 `F12` 開啟開發者工具 → 點選 Network → 找到 `my-info` 並複製 Bearer Token
3. 將 Token 存入 `token.txt` 檔案中（每行一個 Token）

![Unich token1](/assets/images/quest/unich/img_1.webp)
---

## 🐳 Docker 執行指令

請將以下指令中的路徑 `/opt/unich/tokens.txt` 改成你自己的 `token.txt` 路徑。

```bash
# 執行 Unich 自動空投腳本
docker run --rm -m 50M \ 
-v /opt/unich/tokens.txt:/app/unich/tokens.txt:Z \
--name Unich \
docker.io/78chicken/unich:latest
# 等待 N 秒後自動結束
sleep 60s
docker stop Unich
``` 
{% include quest-note.md %}
