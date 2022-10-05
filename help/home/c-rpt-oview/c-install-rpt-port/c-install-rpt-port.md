---
description: 要使用Report Portal，必須在IIS上安裝並配置一組應用程式伺服器頁(ASP)。
title: 安裝 Report Portal
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# 安裝 Report Portal{#installing-the-report-portal}

{{eol}}

要使用Report Portal，必須在IIS上安裝並配置一組應用程式伺服器頁(ASP)。

**開始之前**

本章中的過程介紹如何安裝和配置 [!DNL Report Portal]. 要完成這些過程，您必須：

* 安裝Microsoft IIS並了解其版本。
* 知道其報告由顯示的報告集的名稱 [!DNL Report Portal].
* 知道目錄的位置 [!DNL Report Server] 儲存這些報表集的輸出。 確保IIS應用程式伺服器有權訪問此目錄。

>[!NOTE]
>
>* 使用 [!DNL Report Portal]，報表必須遵循特定的命名慣例。 此外，保存報告的目錄必須遵循規定的結構。 如需這些需求的說明，請參閱 [確保您的報表集與Report Portal相容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
>
>* 報告門戶中的密碼現在符合AES-256位。 若升級至Report Portal 2.0，請將 **users.mdb** 資料庫。 需要增加欄位大小，以便通過更新的加密來容納密碼。
>* 如果您要升級至Report Portal 2.0，請增加 **密碼** users.mdb資料庫中50到150的欄位。 需要增加欄位大小，以便通過更新的加密來容納密碼。
>* Report Portal現在提供更強大的雜湊演算法，並支援Salting。 如果您要升級至 **Report Portal 2.1**，新增文字欄位， *PasswordSalt* 欄位大小為20個字元(在 [!DNL users.mdb]資料庫。 此欄位是儲存密碼鹽的必填欄位。
>

