---
description: Data Workbench6.73中的新功能和修正。
title: Data Workbench 6.73 發行說明
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
exl-id: 911c0cb7-ad95-4dbb-90ff-8e5c40b19f7f
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 26%

---

# Data Workbench 6.73 發行說明{#data-workbench-release-notes}

Data Workbench6.73中的新功能和修正。

## 修正 {#section-160baf6ea04c45a993777ee4260691ed}

* 修正使用者在 Workstation 中無法登入某些高解度和高 DPI 硬體的問題。
* 修正使用IMS登入時，封存檔案名稱中缺少電子郵件的伺服器問題。
* 更新 OpenSSL 至第 1.1.0h 版，其中包含多項漏洞修正以及新的 SSL 加密。
* 將下列開放原始碼程式庫更新為最新的穩定版本

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* 新增「查詢」檔案列計數超過支援之 357913908 列的錯誤記錄。

## 已知問題 {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbench工作站6.73版未連線至Data Workbench伺服器6.61版及更舊版本。 原因是，較舊的伺服器版本使用6.73版中不支援的弱密碼形式。要啟用對較舊版本的支援

   1. 使用OpenSSL 1.0.1h版支援的強密碼清單覆蓋伺服器上的預設SSL密碼清單。 若要覆寫，請在「元件」和「處理伺服器的元件」目錄中可用的「Communications.cfg」檔案中新增金鑰「SSL加密」。 例如︰`SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >確保密鑰與SSL埠處於同一級別。 有關詳細資訊，請參閱[通信配置設定](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. 將最新的trust_ca_cert.pem檔案放置在伺服器6.61和舊版伺服器上。 此設定適用於所有Workstation 6.7x版本。

請參閱[封存的發行說明](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html)，了解Data Workbench5.3到5.52。
