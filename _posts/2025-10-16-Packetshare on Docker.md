---
title: "Packetshare Docker 掛機教學：使用 QEMU 模擬器在 x86_64 上運行 ARM 節點、賺取美金與被動收益實測"
date: 2025-10-16
categories: [bot]
tags: [Docker, QEMU, 模擬器, 網路賺錢, 掛機, 被動收入, Packetshare, Paypal, 虛擬貨幣, 流量分享]
description: "Packetshare 是一款能讓你透過分享閒置網路頻寬來賺取被動收入的服務。本篇教學將介紹如何使用 QEMU 模擬器在 x86_64 系統中模擬 ARM 架構，並透過 Docker 一鍵部署 Packetshare 節點，包含註冊教學、執行指令與提領實測。"
image: /assets/images/bot/packetshare/banner.webp
written_by: 機掰雞
lang: zh-TW
---


![Packetshare 封面圖](/assets/images/bot/packetshare/banner.webp)

Packetshare 是一款類似 Honeygain 的頻寬共享平台，透過分享家中或辦公室的閒置網路頻寬，即可賺取美金報酬。  
它支援 Windows、Linux、macOS 及 Docker，非常適合用來部署在閒置伺服器或樹莓派上賺取被動收入。

Packetshare已經出現多年，機掰雞也寫過關於它的文章。只不過它對ip的類型規定比較嚴格，非家用ip就無法繼續營利。  
且官方釋出的image後來也只支援arm架構(x86_64/amd64不可用)。所以後來機掰雞就逐漸淡出這塊。  
最近大概知道有模擬器（qemu）可以使用，就寫了這篇來告知有興趣的各位。  
不過使用模擬器的效率就是會比較差,也許差蠻多的,大家可以測試看看。(小弟的ip關係首先就被打槍了,故不加入測試)
---

## 📝 註冊帳號

👉 [立即註冊 Packetshare](https://www.packetshare.io?code=741F0A1DE8748B75)

🎉 註冊後登入 Dashboard，就可以取得專屬的節點 Token，等下部署 Docker 節點會用到這個值。

---

## 🔗 連結

- 🌐 官方網站：[https://www.packetshare.io/](https://www.packetshare.io/)
- 🐳 Docker image：[packetshare/packetshare](https://hub.docker.com/r/packetshare/packetshare)
> **功能：** 分享閒置網路頻寬，賺取被動收入

---

## 💻 安裝 QEMU 模擬器（支援多架構容器） - 機掰雞系統採用rocky9

在 x86_64 / amd64 系統上執行 ARM、386 等異架構容器。

---

### 🧩 1. 註冊 QEMU 模擬器

```bash
docker run --rm --privileged docker.io/multiarch/qemu-user-static --reset -p yes
```

> 💡 此指令會自動在系統中註冊多種 QEMU 模擬架構（ARM、PPC、S390x 等）。

---

### 🔍 2. 驗證是否註冊成功

```bash
ls /proc/sys/fs/binfmt_misc/
```

應該會看到以下類似輸出：

```
qemu-aarch64
qemu-arm
qemu-ppc64le
qemu-s390x
register
status
```

---

### 🧠 3. 實際測試模擬是否成功

執行 ARM64 測試容器：

```bash
docker run --rm -t --arch arm64 docker.io/arm64v8/alpine uname -m
```

- 預期輸出：
  ```
  aarch64
  ```

若沒有輸出，可加上 `--privileged` 再試一次：

```bash
sudo podman run --rm -t --privileged --arch arm64 docker.io/arm64v8/alpine uname -m
```

---

### 🎯 測試通過後

代表你已能在 x86_64 主機上模擬運行 ARM64、ARMv7、PPC64LE 等多種架構的容器 🎉  
接下來即可順利執行不同架構的應用，例如：

```bash
docker run --rm --arch arm64 packetshare/packetshare
```


## 🐳 Docker 執行指令
```bash
docker run -d --restart always -m 128M \
 --name PacketShare \
 --arch arm64 \
 packetshare/packetshare \
 -accept-tos -email=你的email -password=你的密碼 
```
