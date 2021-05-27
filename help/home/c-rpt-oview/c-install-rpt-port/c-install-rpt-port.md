---
description: 要使用Report Portal，必須在IIS上安裝並配置一組應用程式伺服器頁(ASP)。
title: 安裝 Report Portal
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# 安裝 Report Portal{#installing-the-report-portal}

要使用Report Portal，必須在IIS上安裝並配置一組應用程式伺服器頁(ASP)。

**開始之前**

本章中的過程介紹如何安裝和配置[!DNL Report Portal]。 要完成這些過程，您必須：

* 已安裝Microsoft IIS並了解其版本。
* 知道其報告由[!DNL Report Portal]顯示的報告集的名稱。
* 了解[!DNL Report Server]保存這些報告集輸出的目錄的位置。 確保IIS應用程式伺服器有權訪問此目錄。

>[!NOTE]
>
>* 若要使用[!DNL Report Portal]來檢視，報表必須遵循特定命名慣例。 此外，要將報告保存到的目錄必須遵循規定的結構。 如需這些需求的說明，請參閱[確保您的報表集與Report Portal相容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)。
   >
   >
* 報告門戶中的密碼現在符合AES-256位。 如果升級到Report Portal 2.0，請將&#x200B;**users.mdb**&#x200B;資料庫中的「密碼欄位大小」欄位從50增加為150。 需要增加欄位大小，以便通過更新的加密來容納密碼。
>* 如果要升級到Report Portal 2.0，請將users.mdb資料庫中&#x200B;**Password**&#x200B;欄位的「欄位大小」從50增加為150。 需要增加欄位大小，以便通過更新的加密來容納密碼。
>* Report Portal現在提供更強大的雜湊演算法，並支援Salting。 如果要升級到&#x200B;**Report Portal 2.1**，請在[!DNL users.mdb]資料庫中添加欄位大小為20個字元的新文本欄位&#x200B;*PasswordSalt*。 此欄位是儲存密碼鹽的必填欄位。

>


