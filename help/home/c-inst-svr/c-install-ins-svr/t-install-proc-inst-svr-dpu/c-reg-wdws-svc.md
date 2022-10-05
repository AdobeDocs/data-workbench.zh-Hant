---
description: 啟動Insight Server並同時將其註冊為Microsoft Windows Service的程式。
title: 將 Insight Server 註冊為 Windows 服務
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 3%

---

# 將 Insight Server 註冊為 Windows 服務{#registering-insight-server-as-a-windows-service}

{{eol}}

啟動Insight Server並同時將其註冊為Microsoft Windows Service的程式。

>[!NOTE]
>
>開始時 [!DNL Insight Server] 首次會自動連線至Adobe授權伺服器，註冊您的數位憑證。 要成功完成註冊過程，執行以下步驟時，您的電腦必須連接到Internet。

**開始 [!DNL Insight Server] 並註冊為Windows服務**

1. 開啟命令提示符，並導覽至安裝資料夾中的bin子目錄 [!DNL Insight Server].

   範例：[!DNL C:\Adobe\Server\bin]

1. 在命令提示符下，執行以下命令以啟動 [!DNL Insight Server] 同時註冊以在Microsoft Windows下作為服務執行：

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. 確認 [!DNL Insight Server] 執行正確，按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. 此命令序列可能因您使用的Windows版本而異。

   1. 在服務清單中，找到 **[!DNL Adobe Insight Server]** 並確認其狀態為「已啟動」且其啟動類型為「自動」。
   1. 關閉「服務」控制面板。

1. 檢查 [!DNL Insight Server] 在啟動期間遇到任何錯誤，請按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. 此命令序列可能因您使用的Windows版本而異。

   1. 在 [!DNL Event Viewer] ，選擇 **[!UICONTROL Application]** 記錄檔。
   1. 在右窗格中，尋找在 [!DNL Source] 欄。
   1. 如果您在「Adobe」中發現錯誤，請連按兩下錯誤以顯示 [!DNL Event Properties] 窗口。 此窗口提供有關錯誤的詳細資訊。

1. 檢查完 [!DNL Applications] 日誌，關閉事件查看器。

您已完成 [!DNL Insight Server]. [!DNL Insight Server] 設計為持續執行。 如果重新啟動電腦， [!DNL Insight Server] 自動重新啟動。 如果您需要開始和停止 [!DNL Insight Server] 您可以手動使用Windows中的「服務」控制面板執行此操作。 如下節所述，您可以選擇設定 [!DNL Insight Server] 定期自動重新啟動的服務。

## 配置服務以自動重新啟動 {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] 可持續執行。 它通常僅在執行不頻繁的任務（如軟體升級或證書更改）或發生某些系統錯誤時停止或啟動。 不需要停止或重新啟動 [!DNL Insight Server] 在正常系統運行期間提供服務；不過，您可以將服務設定為定期（每日、每週或每月）重新啟動，例如清除事件訊息。

**若要設定 [!DNL Insight Server] 自動重新啟動的服務**

1. 導覽至 [!DNL Components] 資料夾（位於安裝的目錄中） [!DNL Insight Server].

   範例：[!DNL C:\Adobe\Server\Components]

1. 使用Notepad等文本編輯器建立名為 [!DNL ScheduledRestart.cfg].
1. 在 [!DNL ScheduledRestart.cfg] 檔案：

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
      <td colname="col1"> <i>月DD, YYYY HH:MM:SStzone</i> </td> 
      <td colname="col2"> <p>您想要的時間 <span class="keyword"> Insight Server </span> 第一次重啟。 </p> <p>範例：2013年8月13日22:30:東部標準時間00 </p> <p> <p>注意：必須指定時區。 如果未指定，時區不預設為系統時間。 如果要實施日光節約時間或類似的時鐘轉移政策，則必須保存 <span class="filepath"> .dst </span> 檔案包含Base\Dataset\Timezone目錄中的適當規則 <span class="keyword"> Insight Server </span> 機器。 如需支援的時區縮寫清單，以及實作日光節約時間的相關資訊，請參閱 <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> 時區代碼 </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>頻率</i> </td> 
      <td colname="col2"> <p>以下任一值： 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">月 </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">週 </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">天 </li> 
       </ul> </p> <p>指出您想要的頻率 <span class="keyword"> Insight Server </span> 在「開始時間」中指定的初始時間後重新啟動。 </p> <p>例如，如果您想 <span class="keyword"> Insight Server </span> 若要每週重新啟動一次，您可將此值設為「周」。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 儲存 [!DNL ScheduledRestart.cfg] 檔案。

   確認 [!DNL ScheduledRestart.cfg] 檔案位於 [!DNL Components] 資料夾（位於安裝的目錄中） [!DNL Insight Server].
