---
title: "Earnapp on Docker"
date: 2024-12-10
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, Paypal, 被動收入, 頻寬分享]
description: "利用 Docker 掛機部署 EarnApp，分享閒置頻寬即可賺取美金，支援 Paypal 出金，輕鬆打造被動收入來源。"
image: /assets/images/earnapp/banner.png
author: 機掰雞
lang: zh-TW
---

![EarnApp 封面圖](/assets/images/earnapp/banner.png)

**EarnApp** 是一個被動收入平台，只需安裝後背景執行，就能透過分享你的閒置頻寬來賺取收益。適合長時間開機的設備（如樹莓派、伺服器等），**完全自動化掛機**，**不影響網速、不需額外操作**。

---

## 📝 註冊帳號

👉 [立即註冊 EarnApp](https://earnapp.com/i/eTgpCCsj)

🎉 使用機掰雞的邀請連結註冊，你會成為我的下線，**我將獲得你收入的 10% 作為飼料費**，但**不會影響你的收益**！

---

## 🔗 連結

- 🌐 官網：[https://earnapp.com](https://earnapp.com)
- 🐳 Docker Hub：[madereddy/earnapp](https://hub.docker.com/r/madereddy/earnapp)
> **功能：** 自動掛機，分享頻寬賺錢，適合背景長期執行

---

## ⚠️ 注意事項

> ❗ **非官方映像檔**，請自行評估使用風險：
> - 持續執行需使用者的網路頻寬
> - 若網路品質差可能影響收益
> - 不建議在計量型網路或有流量上限的環境使用

---

## 🐳 Docker 執行指令

第一次使用（沒有 UUID 時）請依照以下流程操作：

```bash
# 啟動 container（第一次使用無 UUID）
docker run -d --restart always -m 64M  \
--name EarnApp \
madereddy/earnapp
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
docker run -d --restart always --replace -m 64M \
--name EarnApp \
-e EARNAPP_UUID=你的Token \
madereddy/earnapp
```
