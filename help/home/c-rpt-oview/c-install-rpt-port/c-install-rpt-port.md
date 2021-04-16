---
description: 若要使用報表入口網站，您必須在IIS上安裝並設定一組應用程式伺服器頁面(ASP)。
title: 安裝 Report Portal
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# 安裝 Report Portal{#installing-the-report-portal}

若要使用報表入口網站，您必須在IIS上安裝並設定一組應用程式伺服器頁面(ASP)。

**開始之前**

本章中的過程介紹如何安裝和配置[!DNL Report Portal]。 要完成這些過程，您必須：

* 已安裝Microsoft IIS並瞭解其版本。
* 瞭解報告集的名稱，其報告由[!DNL Report Portal]顯示。
* 瞭解[!DNL Report Server]儲存這些報表集輸出的目錄位置。 請確定IIS應用程式伺服器可存取此目錄。

>[!NOTE]
>
>* 若要使用[!DNL Report Portal]檢視報表，報表必須遵循特定的命名慣例。 此外，要將報告保存到的目錄必須遵循指定的結構。 如需這些需求的說明，請參閱[確保您的報表集與報表入口網站相容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)。
   >
   >
* 報告入口網站中的密碼現在符合AES-256位元規範。 如果升級至報告入口2.0，請將&#x200B;**users.mdb**&#x200B;資料庫中的「密碼欄位大小」欄位從50增加為150。 必須增加欄位大小，才能使用更新的加密來容納密碼。
>* 如果要升級到報告門戶2.0，請將users.mdb資料庫中&#x200B;**Password**&#x200B;欄位的欄位大小從50增加到150。 必須增加欄位大小，才能使用更新的加密來容納密碼。
>* 報表入口網站現在提供更強大的雜湊演算法與銷售支援。 如果要升級至&#x200B;**報表入口2.1**，請在[!DNL users.mdb]資料庫中新增欄位大小為20個字元的&#x200B;*PasswordSalt*&#x200B;新文字欄位。 此欄位是儲存口令salt的必需欄位。

>


