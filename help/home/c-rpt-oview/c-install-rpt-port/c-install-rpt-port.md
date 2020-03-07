---
description: 若要使用報表入口網站，您必須在IIS上安裝並設定一組應用程式伺服器頁面(ASP)。
solution: Analytics
title: 安裝報表入口網站
topic: Data workbench
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安裝報表入口網站{#installing-the-report-portal}

若要使用報表入口網站，您必須在IIS上安裝並設定一組應用程式伺服器頁面(ASP)。

**開始之前**

本章中的過程介紹如何安裝和配置 [!DNL Report Portal]。 要完成這些過程，您必須：

* 已安裝Microsoft IIS並瞭解其版本。
* 瞭解報表顯示的報表集名稱 [!DNL Report Portal]。
* 瞭解儲存這些報表集 [!DNL Report Server] 輸出的目錄位置。 請確定IIS應用程式伺服器可存取此目錄。

>[!NOTE]
>
>* 若要使用檢視， [!DNL Report Portal]報表必須遵循特定的命名慣例。 此外，要將報告保存到的目錄必須遵循指定的結構。 如需這些需求的說明，請參 [閱「確保報表集與報表入口網站相容……」](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* 報告入口網站中的密碼現在符合AES-256位元規範。 如果升級至Report Portal 2.0，請將users.mdb資料庫中的「密碼欄位大小」欄位從50 **增加至150** 。 必須增加欄位大小，才能使用更新的加密來容納密碼。
>* 如果要升級至Report Portal 2.0，請將users.mdb資料庫中「 **Password** 」欄位的「欄位大小」從50增加為150。 必須增加欄位大小，才能使用更新的加密來容納密碼。
>* 報表入口網站現在提供更強大的雜湊演算法與銷售支援。 如果您要升級至 **Report Portal 2.1**，請在資料庫中新增欄位大小為20個字元的「文字」欄位 *PasswordSalt*[!DNL users.mdb]。 此欄位是儲存口令salt的必需欄位。
>



