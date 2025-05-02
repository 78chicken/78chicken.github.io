# Stobix on Docker

![Stobix 封面圖](/assets/images/stobix/banner.png)

Stobix 是一個專注於隱私的加密貨幣投資平台，結合人工智慧（AI）與雙重投資（Dual Investment）策略，提供高達年化 **400%** 的收益率，**無需 KYC 或 Gas 費**，支援超過 70 種熱門加密貨幣。

---

## 🌟 核心特色

### 🔁 雙重投資（Dual Investment）
- 用戶可透過自動化買賣策略獲得 **被動收益**
- **投資期限靈活**，最低僅需 **$10**
- 可隨時提前贖回，無需主動交易

### 🤖 Pulse AI 智能分析
- 利用 AI 即時分析市場數據
- 提供個性化交易建議
- 預測 **收益率、成功機率、建議倉位大小**

### 🔐 Stobix 錢包
- **支援多鏈**（Ethereum、BSC、Solana 等）
- **無需 KYC**
- 提供快速、安全的存取款和資產管理

### ⚡ 高槓桿期貨交易
- 高達 **100 倍槓桿**
- 搭載智慧風險管理機制
- 適合進階與活躍交易者

### 🎁 獎勵與推薦計畫
- 邀請好友、參與交易可獲得獎勵與空投
- 提升積分與整體收益

---

## 📝 註冊帳號

👉 [立即註冊 Stobix](https://stobix.com/invite/jvd6v)

🎉 使用機掰雞的邀請連結可以獲得額外的「雞飼料」，你也會收到一些點數，不會影響自身收益！

---

## 🔗 官方連結

- 🌐 官網：[https://stobix.com](https://stobix.com)
- 🐳 Docker Hub：[78chicken/stobix](https://hub.docker.com/r/78chicken/stobix)

> **功能：** 自動點擊挖礦 & 自動完成任務

---

## ⚠️ 注意事項

> ❗ **非官方開發版本**，請謹慎使用：
> - 有被封號或資安風險
> - 此程式非由機掰雞撰寫，僅轉製為 Docker 版本
> - 使用前請自行評估風險

---

## 📁 運行前準備

請建立 `accounts.txt` 檔案，並將你的 **錢包私鑰** 放入（例如 MetaMask）  
範例路徑：

<div style="text-align: left">
  <img src="/assets/images/stobix/img_1.png" width="400" style="display: block; margin-bottom: 16px;" />
  <img src="/assets/images/stobix/img_2.png" width="400" style="display: block; margin-bottom: 16px;" />
  <img src="/assets/images/stobix/img_3.png" width="400" style="display: block; margin-bottom: 16px;" />
  <img src="/assets/images/stobix/img_4.png" width="400" style="display: block;" />
</div>



---

## 🚀 Docker 執行指令

請根據你的實際檔案路徑替換 `/opt/stobix/accounts.txt`：
```bash
#/opt/stobix/accounts.txt請改成你自己的路徑
docker run -d --restart always --replace -m 50M --name Stobix -v /opt/stobix/accounts.txt:/app/accounts.txt docker.io/78chicken/stobix
```
