---
description: 啟動Insight Server並同時將其註冊為Microsoft Windows服務的程式。
solution: Analytics
title: 將 Insight Server 註冊為 Windows 服務
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 3%

---


# 將 Insight Server 註冊為 Windows 服務{#registering-insight-server-as-a-windows-service}

啟動Insight Server並同時將其註冊為Microsoft Windows服務的程式。

>[!NOTE]
>
>當您第一次 [!DNL Insight Server] 啟動時，它會自動連線至Adobe License Server，以註冊您的數位憑證。 要成功完成註冊過程，在執行以下步驟時，您的電腦必須連接到Internet。

**啟動並[!DNL Insight Server]將其註冊為Windows服務**

1. 開啟命令提示符，並導航到所安裝資料夾中的bin子目錄 [!DNL Insight Server]。

   範例：[!DNL C:\Adobe\Server\bin]

1. 在命令提示符下，執行以下命令以啟動並同 [!DNL Insight Server] 時註冊它以作為Microsoft Windows下的服務運行：

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. 若要確認 [!DNL Insight Server] 正確執行，請按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**。 此命令序列可能因您使用的Windows版本而異。

   1. 在服務清單中，找到條目並確 **[!DNL Adobe Insight Server]** 認其狀態為「啟動」，其啟動類型為「自動」。
   1. 關閉「服務」控制面板。

1. 若要檢查啟 [!DNL Insight Server] 動期間是否遇到任何錯誤，請按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**。 此命令序列可能因您使用的Windows版本而異。

   1. 在窗口的左窗格中， [!DNL Event Viewer] 選擇日誌 **[!UICONTROL Application]** 。
   1. 在右窗格中，尋找欄中有「Adobe」的 [!DNL Source] 事件。
   1. 如果您在&quot;Adobe&quot;中發現錯誤，請連按兩下錯誤以顯示視 [!DNL Event Properties] 窗。 此窗口提供了有關錯誤的詳細資訊。

1. 檢查完日誌後， [!DNL Applications] 關閉事件查看器。

您已完成安裝 [!DNL Insight Server]。 [!DNL Insight Server] 設計為可持續運行。 如果重新啟動電腦，則會自 [!DNL Insight Server] 動重新啟動。 如果您需要手動啟動和停 [!DNL Insight Server] 止，則可使用Windows中的「服務」控制面板執行此動作。 如以下章節所述，您可選擇將服務設 [!DNL Insight Server] 定為定期自動重新啟動。

## 配置服務以自動重新啟動 {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] 旨在持續不間斷地運行。 通常只有在執行不頻繁的任務（如軟體升級或證書更改）或發生某些系統錯誤時才會停止或啟動它。 在正常系統操作期間，無需停 [!DNL Insight Server] 止或重新啟動服務；不過，您可以設定服務定期（每日、每週或每月）重新啟動，例如清除事件訊息。

**要配置服[!DNL Insight Server]務以自動重新啟動**

1. 導覽至您 [!DNL Components] 所安裝目錄中的資料夾 [!DNL Insight Server]。

   範例：[!DNL C:\Adobe\Server\Components]

1. 使用文本編輯器（如記事本）建立名為的新檔案 [!DNL ScheduledRestart.cfg]。
1. 在檔案中輸入以下文 [!DNL ScheduledRestart.cfg] 本：

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 對於此值…… </th> 
      <th colname="col2" class="entry"> 指定分類的 </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>月DD, YYYY HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>您希望Insight Server首 <span class="keyword"> 次重 </span> 新啟動的時間。 </p> <p>範例：2013年8月13日美國東部標準時22點30分 </p> <p> <p>注意： 您必須指定時區。 如果未指定，時區不預設為系統時間。 如果您想要實作日光節約時間或類似的時鐘移位政策，則必須在Base\Dataset\Timezone directory on the <span class="filepath"> Insight Server機器中儲存包含適當規則的 </span> .dst <span class="keyword"></span> 檔案。 有關支援的時區縮寫和實施日光節約時間的資訊的清單，請參閱時 <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> 區代碼 </a>。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>頻率</i> </td> 
      <td colname="col2"> <p>下列值之一： 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">個月 </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">週 </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">天 </li> 
       </ul> </p> <p>指出在「開始時間」中指 <span class="keyword"> 定的初 </span> 始時間後，您要重新啟動Insight Server的頻率。 </p> <p>例如，如果您想要 <span class="keyword"> Insight Server每 </span> 周重新啟動一次，您會將此值設為「week」。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Save the [!DNL ScheduledRestart.cfg] file.

   驗證文 [!DNL ScheduledRestart.cfg] 件是否位 [!DNL Components] 於安裝目錄的資料夾中 [!DNL Insight Server]。
