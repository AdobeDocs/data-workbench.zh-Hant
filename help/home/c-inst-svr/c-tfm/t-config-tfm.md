---
description: 轉換功能會在Insight Server FSU電腦上執行，以啟用匯出記錄來源資料以供其他應用程式使用。
title: 設定轉換
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# 設定轉換{#configuring-transform}

{{eol}}

轉換功能會在Insight Server FSU電腦上執行，以啟用匯出記錄來源資料以供其他應用程式使用。

[!DNL Transform] 可讀 [!DNL .vsl] 檔案、日誌檔案、XML檔案和ODBC資料，並將資料導出為 [!DNL .vsl] 可用於資料倉庫載入常式、審計機構或其他目標的檔案、文本檔案或分隔文本檔案。 資料提取和轉換可以連續執行，或者以其它預定方式執行。 每個 [!DNL Insight Server] 提供更改事件資料輸出的FSU必須運行 [!DNL Transform].

>[!NOTE]
>
>通常， [!DNL Transform] 安裝在 [!DNL Insight Server] FSU。 不過，您的實作可能需要在 [!DNL Insight Server] DPU。 如需詳細資訊，請聯絡Adobe。

有關安裝、配置和操作的系統要求的資訊 [!DNL Transform]，請參閱 *最低系統需求* 檔案。

Adobe [!DNL Transform] 功能作為設定檔 [!DNL .zip] 檔案 [!DNL Insight Server] 發行套件。 此 [!DNL Transform] 設定檔是內部設定檔，可為 [!DNL Insight Server]. 如同Adobe提供的所有其他內部設定檔，不應變更設定檔。 所有自訂都必須發生在您的資料集、角色專屬設定檔或您建立的其他設定檔中。

設定檔包含下列檔案：

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* 記錄處理資料集包含檔案

這些檔案都位於 [!DNL Dataset] 資料夾。

**若要安裝 [!DNL Transform] 設定檔[!DNL Insight Server]**

>[!NOTE]
>
>以下安裝說明假設您已安裝 [!DNL Insight] 並建立 [!DNL Insight] 和 [!DNL Insight Server] 安裝 [!DNL Transform]. 如果您尚未這麼做，請參閱* [!DNL Insight] 使用手冊*。

1. 開啟 [!DNL .zip] 檔案 [!DNL Insight Server] 發行套件，然後開啟 [!DNL Profiles] 資料夾 [!DNL .zip] 檔案。
1. 複製 [!DNL Transform] 檔案夾 [!DNL Profiles] 檔案夾 [!DNL Insight Server] 安裝目錄。 你最後想用 [!DNL ...\Profiles\Transform] 資料夾 [!DNL Insight Server] 如下列範例所示。

   ![步驟資訊](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >如果您按照安裝的所有步驟操作 [!DNL Insight Server] (請參閱 [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md))，您可能已有 [!DNL Transform] 資料夾。

1. 使用下列步驟來更新 [!DNL profile.cfg] 檔案，用於要使用的配置檔案 [!DNL Transform]. 完成這些步驟後，資料集會重新處理。

   1. 開啟 [!DNL Profile Manager].
   1. 以滑鼠右鍵按一下旁的核取記號 [!DNL profile.cfg] 按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。

   1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 此 [!DNL profile.cfg] 的上界。

   1. 在 [!DNL profile.cfg]窗口，按一下右鍵 **[!UICONTROL Directories]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. 鍵入新目錄的名稱： [!DNL Transform]
   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Profile Manager]，按一下右鍵的複選標籤 [!DNL profile.cfg] 在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔（包括設定檔），因為您安裝這些設定檔的更新時，變更會遭到覆寫。
