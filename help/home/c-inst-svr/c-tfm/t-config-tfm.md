---
description: 轉換功能可在Insight Server FSU機器上執行，以便匯出記錄來源資料供其他應用程式使用。
solution: Insight
title: 配置轉換
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 配置轉換{#configuring-transform}

轉換功能可在Insight Server FSU機器上執行，以便匯出記錄來源資料供其他應用程式使用。

[!DNL Transform] 可以讀 [!DNL .vsl][!DNL .vsl] 取檔案、記錄檔、XML檔案和ODBC資料，並將資料匯出為檔案、文字檔或分隔文字檔，供資料倉庫載入常式、稽核機構或其他目標使用。 資料提取和轉換可以連續地執行或其它排程的。 每個 [!DNL Insight Server] 提供變更事件資料輸出的FSU都必須執行 [!DNL Transform]。

>[!NOTE]
>
>通常 [!DNL Transform] 安裝在 [!DNL Insight Server] FSU上。 不過，您的實作可能需要在 [!DNL Insight Server] DPU上安裝。 如需詳細資訊，請聯絡Adobe。

有關安裝、配置和作業系統需求的資訊，請參 [!DNL Transform]閱最低系 *統需求文檔* 。

Adobe會將 [!DNL Transform] 功能當成發行套件 [!DNL .zip] 的檔案內 [!DNL Insight Server] 的設定檔。 此 [!DNL Transform] 描述檔是內部描述檔，可提供其他功能 [!DNL Insight Server]。 如同Adobe提供的所有其他內部設定檔，不應變更設定檔。 所有自訂都必須發生在您的資料集、角色特定的描述檔或您建立的其他描述檔中。

配置檔案由以下檔案組成：

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL轉 [!DNL Insight] 換模式。cfg]
* 日誌處理資料集包括檔案

所有這些檔案都位於配置文 [!DNL Dataset] 件的資料夾中。

**若要將描述[!DNL Transform]檔安裝在[!DNL Insight Server]**

>[!NOTE]
>
>以下安裝說明假定您已 [!DNL Insight] 經安裝並建立了 [!DNL Insight] 與 [!DNL Insight Server] 要安裝的連接 [!DNL Transform]。 如果您尚未這麼做，請參閱*使用 [!DNL Insight] 指南*。

1. 開啟 [!DNL .zip] 發行套件 [!DNL Insight Server] 的檔案，並開啟該 [!DNL Profiles] 檔案中的資 [!DNL .zip] 料夾。
1. 將檔案 [!DNL Transform] 夾複製到安 [!DNL Profiles] 裝目錄中 [!DNL Insight Server] 的資料夾。 您最後想要在您的檔案 [!DNL ...\Profiles\Transform] 夾上找到資 [!DNL Insight Server] 料夾，如下列範例所示。

   ![步驟資訊](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >如果您遵循了所有安裝步驟 [!DNL Insight Server] (請參 [閱Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md))，則Profiles目錄中可能已 [!DNL Transform] 有資料夾。

1. 使用下列步驟更 [!DNL profile.cfg] 新要使用的配置檔案 [!DNL Transform]。 完成這些步驟後，資料集會重新處理。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵旁邊的複選標 [!DNL profile.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。

   1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Insight]**。 出現 [!DNL profile.cfg] 窗口。

   1. 在視窗 [!DNL profile.cfg]中，按一下滑鼠右鍵 **[!UICONTROL Directories]** 並按一下 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 鍵入新目錄的名稱： [!DNL Transform]
   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 在中， [!DNL Profile Manager]按一下右鍵列中的複選 [!DNL profile.cfg] 標籤 [!DNL User] ，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

      >[!NOTE]
      >
      >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔（包括設定檔），因為當您安裝這些設定檔的更新時，會覆寫您的變更。

