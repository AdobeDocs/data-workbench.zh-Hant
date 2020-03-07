---
description: 資料工作台報表入口網站的安全性更新。
title: DWB Report Portal 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWB Report Portal 2.1{#dwb-report-portal}

資料工作台報表入口網站的安全性更新。

**重要安全性更新**

報表入口網站現在提供更強大的雜湊演算法與銷售支援。 如果要升級至Report Portal 2.1，請在users.mdb資料庫中新增一個新的「文字」欄位PasswordSalt，欄位大小為20個字元。 此欄位是儲存口令salt的必需欄位。
