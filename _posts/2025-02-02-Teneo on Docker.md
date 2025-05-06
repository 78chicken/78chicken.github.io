---
title: "Teneo on Docker"
date: 2025-02-02
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣]
description: "使用 Docker 掛機 Teneo，將裝置閒置資源轉換為 Teneo Point，輕鬆實現被動收入。"
image: /assets/images/teneo/banner.png
written_by: "機掰雞"
lang: zh-TW
---

![Teneo 封面圖](/assets/images/teneo/banner.png)

**Teneo** 是一個裝置資源共享平台，用戶可透過登入與掛機方式貢獻資源，換取 Teneo Point。支援 Docker 掛機模式，適合技術玩家低成本、長時間穩定運行。

---

## 🌟 核心特色

### 🛡️ 匿名貢獻，保留主控權
- Teneo 鼓勵用戶貢獻裝置資源，回饋獎勵。
- 適用於低功耗掛機，且無需提供真實資料。

### 💰 輕鬆掛機，穩定收益
- 執行後幾乎無需人工干預。
- 單主機也可部署，適合閒置設備再利用。

### 🐳 Docker 掛機版本
- 機掰雞已將非官方原始碼加工封裝為 Docker 版本。
- 僅需準備 `tokens.txt` 並掛載對應路徑，即可快速啟動。

---

## 📝 註冊帳號

👉 [立即註冊 Teneo](https://dashboard.teneo.pro/auth/signup)

🎉 推薦碼：`1J15s`
- 你可獲得 **1,000 Teneo Point**
- 機掰雞將獲得額外雞飼料，但**不影響你的收益**

---

## 🔗 連結

- 🌐 官方網站：[https://teneo.pro/](https://teneo.pro/)
- 🐳 Docker Hub：[78chicken/teneo](https://hub.docker.com/r/78chicken/teneo)

---

## ⚠️ 注意事項

> ❗ **非官方掛機方式**，可能存在被封號或資安風險，請自行評估是否使用。
>
> - 有被封號或資安風險
> - 程式非機掰雞開發，僅加工為 Docker 映像以方便掛機部署。

---

### 📄 準備 `tokens.txt`

建立一份 `tokens.txt` 檔案，內容如下，每行一個帳號的 Token：

```txt
# 建議每帳號搭配一個獨立 IP 運行，避免封號
eyJhbGciOiJIUzI1NiJ9.eyJ...
```

### 🔍 如何取得 Token？
1. 使用 Chrome 瀏覽器登入 Teneo Dashboard
2. 按下 F12 開啟開發者工具
3. 前往 Application → Storage → Local Storage
4. 複製 accessToken- 對應的值
5. 貼入 tokens.txt

![Teneo token](/assets/images/teneo/img_1.png)

### 📁 Docker 執行方式
```bash
# -v /opt/teneo/tokens.txt 請改成你自己的檔案路徑
docker run -d --restart always -m 50M \
-v /opt/teneo/tokens.txt:/app/teneo/tokens.txt \
--name Teneo \
docker.io/78chicken/teneo:latest
```
