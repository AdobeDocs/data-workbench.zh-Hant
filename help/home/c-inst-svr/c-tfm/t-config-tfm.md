---
description: 轉換功能會在Insight Server FSU電腦上執行，以啟用匯出記錄來源資料以供其他應用程式使用。
title: 設定轉換
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# 設定轉換{#configuring-transform}

轉換功能會在Insight Server FSU電腦上執行，以啟用匯出記錄來源資料以供其他應用程式使用。

[!DNL Transform] 可以讀 [!DNL .vsl] 取檔案、日誌檔案、XML檔案和ODBC資料，並將資料導出為檔案、文本 [!DNL .vsl] 檔案或分隔文本檔案，這些檔案可用於資料倉庫載入常式、審核機構或其他目標。資料提取和轉換可以連續執行，或者以其它預定方式執行。 提供更改事件資料輸出的每個[!DNL Insight Server] FSU必須運行[!DNL Transform]。

>[!NOTE]
>
>通常， [!DNL Transform]安裝在[!DNL Insight Server] FSU上。 不過，您的實作可能需要在[!DNL Insight Server] DPU上安裝。 如需詳細資訊，請聯絡Adobe。

有關安裝、配置和操作[!DNL Transform]的系統需求的資訊，請參閱&#x200B;*最低系統需求*&#x200B;文檔。

Adobe將[!DNL Transform]功能作為[!DNL Insight Server]版本包的[!DNL .zip]檔案中的配置檔案分發。 [!DNL Transform]設定檔是內部設定檔，可為[!DNL Insight Server]提供額外功能。 如同Adobe提供的所有其他內部設定檔，不應變更設定檔。 所有自訂都必須發生在您的資料集、角色專屬設定檔或您建立的其他設定檔中。

設定檔包含下列檔案：

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight]轉換模式.cfg]
* 記錄處理資料集包含檔案

所有這些檔案都位於配置檔案的[!DNL Dataset]資料夾中。

**若要將設定 [!DNL Transform] 檔安裝在[!DNL Insight Server]**

>[!NOTE]
>
>以下安裝說明假定您已安裝[!DNL Insight]並在[!DNL Insight]和要安裝[!DNL Transform]的[!DNL Insight Server]之間建立了連接。 如果尚未這麼做，請參閱* [!DNL Insight]使用手冊*。

1. 開啟[!DNL Insight Server]版本包的[!DNL .zip]檔案，並開啟該[!DNL .zip]檔案中的[!DNL Profiles]資料夾。
1. 將[!DNL Transform]資料夾複製到[!DNL Insight Server]安裝目錄中的[!DNL Profiles]資料夾。 您想要在[!DNL Insight Server]上取得[!DNL ...\Profiles\Transform]資料夾，如下列範例所示。

   ![步驟資訊](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >如果您按照安裝[!DNL Insight Server]的所有步驟操作（請參閱[Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)），則Profiles目錄中可能已有[!DNL Transform]資料夾。

1. 使用下列步驟來更新要使用[!DNL Transform]的配置檔案的[!DNL profile.cfg]檔案。 完成這些步驟後，資料集會重新處理。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵[!DNL profile.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。

   1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出現[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]視窗中，按一下右鍵&#x200B;**[!UICONTROL Directories]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 鍵入新目錄的名稱：[!DNL Transform]
   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL profile.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

      >[!NOTE]
      >
      >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔（包括設定檔），因為您安裝這些設定檔的更新時，變更會遭到覆寫。
