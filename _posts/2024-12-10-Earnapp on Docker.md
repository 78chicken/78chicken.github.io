---
title: "EarnApp Docker 掛機教學：全自動分享頻寬賺取美金被動收入"
date: 2026-04-20
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, Paypal, 被動收入, 頻寬分享, EarnApp, 閒置頻寬]
description: "EarnApp 是最穩定的閒置頻寬分享平台之一。本教學提供 EarnApp 完整的 Docker 掛機部署指令，教你如何設置 UUID、全自動賺取美金被動收入，並詳細說明 PayPal 提現流程與收益評估，輕鬆利用伺服器或樹莓派賺錢。"
image: /assets/images/bot/earnapp/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![EarnApp 封面圖](/assets/images/bot/earnapp/banner.webp)
> 📢 **【更新通知】**
> 04.20 LINUX(Docker)版本看起來真的死光了,考慮改用WIN安裝版
> 10.7 已換回docker.io/madereddy/earnapp:latest最新版

**EarnApp** 是一個被動收入平台，只需安裝後背景執行，就能透過分享你的閒置頻寬來賺取收益。適合長時間開機的設備（如樹莓派、伺服器等），**完全自動化掛機**，**不影響網速、不需額外操作**。

---

## 📝 註冊帳號

👉 [立即註冊 EarnApp](https://earnapp.com/i/cxyYAjPT)

🎉 使用機掰雞的邀請連結註冊，你會成為我的下線，**我將獲得你收入的 10% 作為飼料費**，但**不會影響你的收益**！

---

## 🔗 連結

- 🌐 官方網站：[Earnapp](https://earnapp.com)
- 🐳 Docker image：[madereddy/earnapp](https://hub.docker.com/r/madereddy/earnapp)
> **功能：** 自動掛機，分享頻寬賺錢，適合背景長期執行

---

{% include warning.md %}

---

## 🐳 Docker 執行指令

第一次使用（沒有 UUID 時）請依照以下流程操作：

```bash
# 啟動 container（第一次使用無 UUID）
docker run -d --restart always -m 64M  \
--name EarnApp \
docker.io/madereddy/earnapp:latest
```
接著進入 container 取得 UUID：
```bash
# 進入 container
docker exec -it EarnApp bash
# 執行以下指令產生 UUID（Token）
echo -n sdk-node- && head -c 1024 /dev/urandom | md5sum | tr -d ' -'
```
然後使用產生的 UUID 重啟 container：
```bash
# 使用 UUID 重啟 container
docker run -d --restart always -m 64M \
--name EarnApp \
-e EARNAPP_UUID=你的Token \
docker.io/madereddy/earnapp:latest
```
最後記得註冊你的機器,這樣才能綁定帳號跟營利的機器
先登入你的帳號,然後綁定你的SDK-NODE
```url
https://earnapp.com/r/sdk-node-XXXXXXXXXXXXXXXXXXXXX
```

