---
title: "Assisterr on Docker"
date: 2025-05-31
updated: 2025-06-10
categories: [quest]
tags: [AI, 區塊鏈, 去中心化, 自動化, 被動收入, SLM]
description: "探索 Assisterr AI 平台，打造並變現小型語言模型（SLM），加入去中心化 AI 生態系，公平參與並獲得獎勵。"
image: /assets/images/quest/assisterr/banner.webp
written_by: 機掰雞
lang: zh-TW
---

![Assisterr AI 平台封面圖](/assets/images/quest/assisterr/banner.webp)
> 📢 **【2025-06-10 更新通知】**
>
> 映像檔更新

**Assisterr AI** 是一個去中心化的人工智慧平台，主打以「社群擁有」為核心理念。透過小型語言模型（SLM）和去信任化的 AI 協作架構，讓更多人能公平參與、共創與共享 AI 的價值，打造開放又可持續的智慧經濟。

---

## 🌟 核心特色

- **小型語言模型（SLM）設計**  
  相較於傳統大型語言模型（LLM），SLM 更輕量、高效，運算需求較低，也更環保，非常適合針對特定任務開發專屬 AI 智能體。

- **社群擁有的 AI 智能體**  
  Assisterr 強調由用戶掌握模型的訓練與應用權，推動民主化的 AI 架構，不再讓科技只被少數大公司壟斷。

- **免寫程式的工具介面**  
  平台提供友善的圖形化介面，即使不會寫程式也能打造屬於自己的 AI 模型，大幅降低進入門檻。

- **模型與數據市集**  
  用戶可自由上架、交易、共享模型或訓練資料，創造被動收入，同時促進 AI 協作生態的蓬勃發展。

- **資料與模型透明化管理**  
  透過區塊鏈確保所有貢獻都能被正確記錄與獎勵，讓整體運作具備透明、公平與信任基礎。

---

## 📝 註冊帳號

👉 [點我註冊 Assisterr AI](https://build.assisterr.ai/?ref=67a7143f50650e5d108af900)

🎉 使用機掰雞的推薦連結註冊，**我將收到你收益的一點點雞飼料做為回饋**（完全不會影響你的獎勵）。

---

## 🔗 官方連結整理

- 🌐 官網：[Assisterr.ai](https://assisterr.ai)
- 🐳 Docker image：[78chicken/assisterr](https://hub.docker.com/r/78chicken/assisterr)

---

{% include warning.md %}

---

## 📁 運行前準備

請準備好 `accounts.txt`，內容如下：
```txt
your_solana_private_key
EX:
49RYi2v9.......e8BhKACA7
```
---

## 🐳 Docker 執行方式
請根據你的實際檔案路徑替換 /opt/assisterr/accounts.txt：

```bash
docker run -d --restart always -m 50M \
-v /opt/assisterr/accounts.txt:/app/assisterr/accounts.txt \
--name Assisterr \
docker.io/78chicken/assisterr:latest
```
---

{% include quest-note.md %}
