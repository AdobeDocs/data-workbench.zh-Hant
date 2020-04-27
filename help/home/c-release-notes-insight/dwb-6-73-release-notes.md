---
description: 資料工作台6.73中的新功能和修正。
title: 資料工作台6.73發行說明
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
translation-type: tm+mt
source-git-commit: 9552a2f9fe4e450b1e212b38a09f77252a009419

---


# Data Workbench 6.73 Release Notes{#data-workbench-release-notes}

資料工作台6.73中的新功能和修正。

## 修正 {#section-160baf6ea04c45a993777ee4260691ed}

* 修正使用者在 Workstation 中無法登入某些高解度和高 DPI 硬體的問題。
* 修正使用IMS登入時，封存檔案名稱中遺失電子郵件的伺服器問題。
* 更新 OpenSSL 至第 1.1.0h 版，其中包含多項漏洞修正以及新的 SSL 加密。
* 將下列開放原始碼程式庫更新為最新穩定版本

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* 新增「查詢」檔案列計數超過支援之 357913908 列的錯誤記錄。

## Known issue {#section-f2cb932f6225457a872fb916a78df89a}

* 資料工作台工作站版本6.73不會連線至6.61版及更舊版本的資料工作台伺服器。 原因是，舊版伺服器使用6.73版不支援的弱密碼。若要啟用舊版支援

   1. 使用OpenSSL 1.0.1h版支援的強式密碼清單，覆寫伺服器上的預設SSL密碼清單。 若要覆寫，請在「元件」和「處理伺服器的元件」目錄中的「Communications.cfg」檔案中新增「SSL密碼」。 例如︰`SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >確保密鑰與SSL埠處於相同級別。 有關詳細資訊，請參 [閱通信配置設定](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. 將最新的trust_ca_cert.pem檔案置於伺服器6.61及舊版伺服器上。 此設定適用於所有Workstation 6.7x版本。

請參 [閱「資料工作台](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) 5.3至5.52的封存發行說明」。
