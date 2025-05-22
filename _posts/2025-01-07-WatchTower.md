---
title: "WatchTower on Docker"
date: 2025-01-07
categories: [tool]
tags: [Docker, WatchTower, 自動升級, 無人值守, DevOps]
description: "使用 WatchTower 自動升級 Docker 容器，避免版本落後或手動升級困擾，支援自訂更新策略與通知機制。"
image: /assets/images/tool/watchtower/banner.webp
written_by: 機掰雞
lang: zh-TW
---
![WatchTower 封面圖](/assets/images/tool/watchtower/banner.webp)

**WatchTower** 是一款自動更新 Docker 容器的工具。它會定期檢查執行中容器所用的映像檔是否有更新，一旦偵測到新版，就會自動拉取並重新啟動容器，以套用最新版本。

這能大幅減少手動維護的工作量，並確保服務保持在最新、最安全的狀態。

---

## 🌟 主要特點

- 🔄 **自動檢查更新**：根據時間間隔自動掃描映像更新
- ⏰ **可自訂更新頻率**：透過 `--interval` 設定檢查間隔
- 🧹 **清理舊版映像與匿名 volume**：使用 `--cleanup` 和 `--remove-volumes` 釋放磁碟空間
- 📬 **支援通知整合**：可設定 Slack、Email 等通報方式
- ❌ **支援排除特定容器**：透過 label 控制是否自動更新
- 🐳 **輕量部署**：單一容器即可實現無人值守的升級流程
- 
## 🌐 延伸閱讀（中文資源）

- [官方文件](https://containrrr.dev/watchtower/)
- [Docker 全自動無人值守升級 WatchTower](https://blog.jkgtw.com/)
- [自動升級更新 Docker 容器 — AppleBOY](https://blog.wu-boy.com/)

---

## ⚙️ Docker 執行指令

這是機掰雞平常使用的版本，**加了幾個參數避免磁碟空間爆掉**，也可以依照需求調整成只通知不自動升級。

```bash
docker run -d --restart always --name watchtower \
-v /var/run/docker.sock:/var/run/docker.sock \
containrrr/watchtower \
--cleanup \
--remove-volumes \
--interval 21600
```
