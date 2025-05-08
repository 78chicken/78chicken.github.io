---
title: "3DOS on Docker"
date: 2025-03-14
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣]
description: "透過 Docker 掛機 3DOS，參與去中心化製造網絡，將設計轉化為收益，快速啟動僅需提供 token。"
image: /assets/images/bot/3dos/banner.png
written_by: "機掰雞"
lang: zh-TW
---

![3DOS 封面圖](/assets/images/bot/3dos/banner.png)

**3DOS** 是一個去中心化的按需製造平台，致力於讓任何人都能在數小時內將設計轉化為產品，並透過全球網絡進行製造、銷售與分發。平台支持全球法幣與加密貨幣支付，並利用區塊鏈技術保護設計者的版稅收益。

---

## 🌟 3DOS 平台核心特色

### 🏭 去中心化製造網絡
- 建立全球最大的點對點按需製造網絡，讓任何人都能上傳設計，獲得版稅，並在世界各地製造產品。
- 支援即時連接需求與供應，實現本地按需生產，減少浪費與庫存。

### 💡 設計者與創作者的收益保障
- 利用區塊鏈技術保護設計者的版稅收益，確保設計權益不被侵害。
- 設計者可透過平台上傳設計，並在全球範圍內獲得持續的版稅收入。

### 🌐 全球支付與分發
- 支援全球法幣與加密貨幣支付，方便用戶進行交易。
- 產品可在數小時內完成製造、銷售與分發，實現快速市場進入。

### 🤖 AI 驅動的製造資源索引
- 推出 AI 驅動的 Chrome 擴展，實時抓取與索引全球的製造能力，包括 3D 打印、CNC 加工與注塑等。
- 使用戶能夠立即訪問本地生產選項，提升製造效率。

---

## ⚠️ 注意事項

> - 此工具為非官方版本，使用上請自行評估資安與帳號風險。
> - 程式並非機掰雞撰寫，僅加工為 Docker 映像以方便掛機部署。
> - 建議每個帳號搭配獨立 IP，以降低封號風險。

---

## 📝 註冊帳號

👉 [立即註冊 3DOS](https://dashboard.3dos.io/register?ref_code=2e88ea)

🎉 使用此推薦連結，**機掰雞可獲得額外雞飼料**，**不影響你的收益**。

註冊後進入 Dashboard，記得產生你的 CODE，才能開始賺取收益。

---

## 🔗 連結

- 🌐 官方網站：[3dos](https://3dos.io/)
- 🐳 Docker image：[78chicken/3dos](https://hub.docker.com/r/78chicken/3dos)

---

## 📄 準備 `token.txt`

> 建立 `token.txt` 檔案，內容為你的 Token。

### 🔍 如何取得 Token？

1. 使用 Chrome 登入 3DOS Dashboard。
2. 按下 F12 → 前往 Application。
3. 點選左側 Local Storage。
4. 找到你的 Token 並複製。
![3DOS token](/assets/images/bot/3dos/img_1.png)
---

## 🐳 Docker 執行指令

```bash
# -v /opt/3dos/token.txt 請改成你自己的檔案路徑
docker run --rm -m 50M -e TZ=Asia/Taipei \
--name 3Dos \
-v /opt/3dos/token.txt:/app/3dos/token.txt \
78chicken/3dos:latest
```
