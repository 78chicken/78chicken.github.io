---
title: "OpenLoop on Docker"
date: 2025-01-27
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣]
description: "使用 Docker 掛機 OpenLoop，將裝置閒置資源轉換為獎勵，輕鬆實現被動收入。"
image: /assets/images/openloop/banner.png
written_by: 機掰雞
lang: zh-TW
---

![OpenLoop 封面圖](/assets/images/openloop/banner.png)

**OpenLoop** 是一個數據共享與裝置資源交換平台，透過登入與掛機的方式，允許用戶獲取獎勵。支援 Docker 掛機模式，適合技術玩家低成本、長時間穩定運行。

---

## 🌟 核心特色

### 🛡️ 保留隱私的數據貢獻模式
- OpenLoop 鼓勵用戶分享匿名裝置資訊，用於研究、模型訓練等用途。
- 用戶可保有資料主權，自主選擇是否參與，符合 GDPR 等規範。

### 💰 輕鬆掛機，穩定收益
- 執行後幾乎無需干預，掛機即可持續賺取獎勵。
- 運行資源需求極低，小型 VPS 或閒置主機皆可部署。

### 🐳 Docker 掛機版本
- 機掰雞已將非官方原始碼封裝為 Docker 版本，簡化部署流程。
- 只需準備 `tokens.txt` 並掛載對應路徑，即可快速啟動。

---

## 📝 註冊帳號

👉 [立即註冊 OpenLoop](https://openloop.so/auth/register?ref=ol3f840cc94)

🎉 使用機掰雞的邀請連結註冊，我可以獲得 5% 的雞飼料，而你的收益完全不會受影響 ❤️

---

## 🔗 連結

- 🌐 官方網站：[OpenLoop](https://openloop.so/)
- 🐳 Docker Hub：[78chicken/openloop](https://hub.docker.com/r/78chicken/openloop)

---

## ⚠️ 注意事項

> ❗ **非官方掛機版本**，存在被封號或資安風險，使用前請自行評估風險。
>
> 此版本並非由機掰雞開發，只是將原始程式加工為 Docker 容器版本，供懶人快速部署使用。

---



### 📄 準備 `tokens.txt`

請先準備一份 `tokens.txt`，內容為你的 Token，每行一個，例如：
> #建議每個帳號使用不同 IP 掛機，以降低風險
> 
> eyJhbGciOiJIUzI1N........TFTMzaXuKZc

## 🔍 如何取得 Token？

1. 登入 OpenLoop
2. Dashboard Page->F12
3. 複製Token，貼到 `tokens.txt` 中
![OpenLoop token](/assets/images/openloop/img_1.png)

## 📁 Docker 執行方式
```bash
#-v /opt/openloop/tokens.txt 請改成你自己的路徑 
docker run -d --restart always -m 50M \
--name OpenLoop \
-v /opt/openloop/tokens.txt:/app/openloop/tokens.txt \
docker.io/78chicken/openloop:latest
```
