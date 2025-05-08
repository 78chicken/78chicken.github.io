---
title: "Proxyrack on Docker"
date: 2024-05-21
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, ProxyRack]
description: "使用 Docker 掛載 ProxyRack 分享頻寬賺取收益，支援無頭裝置，詳細教學含註冊與部署指令。"
image: /assets/images/bot/proxyrack/banner.png
written_by: 機掰雞
lang: zh-TW
---

![Proxyrack 封面圖](/assets/images/bot/proxyrack/banner.png)

## 📝 註冊帳號

👉 [連結點我註冊 Proxyrack](https://www.proxyrack.com/become-a-peer/)

🎉 使用機掰雞的推薦連結註冊後，**我將獲得你收益的 10% 作為飼料費**（不影響你的收入）。

---

### 🧪 使用心得
 
> 每日頻寬分享的營利非常少，對機掰雞來說是可有可無的項目。

---

## 🌐 官方連結

- 🌐 官方網站：[ProxyRack](https://www.proxyrack.com/become-a-peer/)
- 🐳 Docker image：[proxyrack/pop](https://hub.docker.com/r/proxyrack/pop)

---

## 🐳 Docker 部署步驟

### 1. 產生 Device ID
記下輸出的亂數字串作為你的 DEVICE ID。
```bash
cat /dev/urandom | LC_ALL=C tr -dc 'A-F0-9' | dd bs=1 count=64 2>/dev/null && echo
```
### 2. 啟動 Proxyrack 容器
請將 你的UUID 替換為你剛剛產生的 Device ID。
```bash 
docker run -d --restart always -m 64M \
--log-opt max-size=1m --log-opt max-file=1 \
--name Proxyrack \
-e UUID=你的UUID \
proxyrack/pop
```
### 3. 加入設備（手動或 API）
你可以到 Proxyrack 的 Web UI 手動加入，也可以透過 API 加入：
```bash  
curl --location 'https://peer.proxyrack.com/api/device/add' \
--header 'Api-Key: 你的APIKEY' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--data '{ 
  "device_id":"你的DEVICE ID", 
  "device_name":"Device名稱(自取)"
}'
```
## ⚠️ 注意事項

- 官方建議容器啟動後 **等待 5～10 分鐘** 再進行設備綁定，機掰雞實測大概需要 **20 分鐘左右** 才會正常出現在列表中，請耐心等待。
- 啟動容器後可能會看到一些錯誤訊息（如連接失敗），但實際運作不受影響，**可以放心忽略**。

![Proxyrack 錯誤訊息](/assets/images/bot/proxyrack/error.png)
