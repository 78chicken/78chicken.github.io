---
title: "OpenLoop on Docker"
date: 2025-01-27
updated: 2025-06-16
categories: [bot]
tags: [Docker, 網路賺錢, 掛機, 被動收入, 虛擬貨幣]
description: "使用 Docker 掛機 OpenLoop，將裝置閒置資源轉換為獎勵，輕鬆實現被動收入。"
image: /assets/images/bot/openloop/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![OpenLoop 封面圖](/assets/images/bot/openloop/banner.webp)
> 📢 **【更新通知】**
>
> 映像檔更新,設定方式及名稱更新

**OpenLoop** 是一個專注於基礎設施驗證的 DePIN 專案，任何人都能運行節點參與鏈上驗證流程，協助 OpenLoop 協議運作，同時獲得代幣獎勵與空投機會。

## 📌 核心功能與特點

- **去中心化基礎設施驗證機制**：任何用戶皆可透過 OpenLoop 提供節點驗證服務。
- **鏈上報告與監控整合**：節點狀態、資源狀況與異常可即時上報鏈上。
- **無需 KYC 門檻低**：一般家用設備即可參與，適合所有人。
- **貢獻可得代幣與空投獎勵**：持續運作節點即可累積驗證報酬。
- **簡易部署**：支援 Docker 快速啟動，不需手動安裝複雜依賴。

---

## 🎯 使用者價值

- 用戶可運行 OpenLoop Validator 節點，參與驗證任務賺取報酬。
- 基礎設施供應商可透過 OpenLoop 提供可信節點服務。
- 整體設計透明，鼓勵社群貢獻與長期參與。

---

## 📝 註冊帳號

👉 [立即註冊 OpenLoop](https://openloop.so/auth/register?ref=ol3f840cc94)

🎉 使用機掰雞的邀請連結註冊，我可以獲得 5% 的雞飼料，而你的收益完全不會受影響 ❤️

---

## 🔗 連結

- 🌐 官方網站：[OpenLoop](https://openloop.so/)
- 🐳 Docker image：[78chicken/openloop](https://hub.docker.com/r/78chicken/openloop)

---

{% include warning.md %}

---

### 📄 準備 `tokens.json`

請先準備一份 `tokens.json`，內容為你的 Token，每行一個，例如：
> #建議每個帳號使用不同 IP 掛機，以降低風險
```json
[
    {
        "Email": "Your Email",
        "accessToken": "eyJhbGciOiJIUzI1N........TFTMzaXuKZc"
    }
]
```

## 🔍 如何取得 Token？

1. 登入 OpenLoop
2. Dashboard Page->F12
3. 複製Token，貼到 `tokens.json` 中
![OpenLoop token](/assets/images/bot/openloop/img_1.webp)

## 🐳 Docker 執行指令
```bash
#-v /opt/openloop/tokens.txt 請改成你自己的路徑 
docker run -d --restart always -m 50M \
--name OpenLoop \
-v /opt/openloop/tokens.json:/app/openloop/tokens.json \
docker.io/78chicken/openloop:latest
```
