---
description: 啟動Insight Server並同時將其註冊為Microsoft Windows Service的程式。
title: 將 Insight Server 註冊為 Windows 服務
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 3%

---

# 將 Insight Server 註冊為 Windows 服務{#registering-insight-server-as-a-windows-service}

啟動Insight Server並同時將其註冊為Microsoft Windows Service的程式。

>[!NOTE]
>
>當您首次啟動[!DNL Insight Server]時，它會自動連接到Adobe許可證伺服器以註冊您的數字證書。 要成功完成註冊過程，執行以下步驟時，您的電腦必須連接到Internet。

**啟動 [!DNL Insight Server] 並註冊為Windows服務**

1. 開啟命令提示符，並導航至[!DNL Insight Server]所安裝資料夾中的bin子目錄。

   範例：[!DNL C:\Adobe\Server\bin]

1. 在命令提示符下，執行以下命令以啟動[!DNL Insight Server]並同時註冊它以作為Microsoft Windows下的服務運行：

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. 若要確認[!DNL Insight Server]是否正常運作，請按一下「**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**」。 此命令序列可能因您使用的Windows版本而異。

   1. 在服務清單中，找到&#x200B;**[!DNL Adobe Insight Server]**&#x200B;的條目，並確認其狀態為「啟動」且其啟動類型為「自動」。
   1. 關閉「服務」控制面板。

1. 要檢查[!DNL Insight Server]在啟動過程中是否遇到任何錯誤，請按一下「**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**」。 此命令序列可能因您使用的Windows版本而異。

   1. 在[!DNL Event Viewer]窗口的左窗格中，選擇&#x200B;**[!UICONTROL Application]**&#x200B;日誌。
   1. 在右窗格中，查找[!DNL Source]列中帶有「Adobe」的事件。
   1. 如果從「Adobe」中發現錯誤，請連按兩下錯誤以顯示[!DNL Event Properties]窗口。 此窗口提供有關錯誤的詳細資訊。

1. 檢查完[!DNL Applications]日誌後，關閉事件查看器。

您已完成[!DNL Insight Server]的安裝。 [!DNL Insight Server] 設計為持續執行。如果重新啟動電腦，[!DNL Insight Server]將自動重新啟動。 如果需要手動啟動和停止[!DNL Insight Server]，可以使用Windows中的「服務」控制面板執行此操作。 如以下部分所述，您可以選擇配置[!DNL Insight Server]服務以定期自動重新啟動。

## 配置服務以自動重新啟動{#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] 可持續執行。它通常僅在執行不頻繁的任務（如軟體升級或證書更改）或發生某些系統錯誤時停止或啟動。 在正常系統操作期間無需停止或重新啟動[!DNL Insight Server]服務；不過，您可以將服務設定為定期（每日、每週或每月）重新啟動，例如清除事件訊息。

**配置服務 [!DNL Insight Server] 以自動重新啟動**

1. 導覽至[!DNL Insight Server]安裝目錄中的[!DNL Components]資料夾。

   範例：[!DNL C:\Adobe\Server\Components]

1. 使用文本編輯器（如記事本）建立名為[!DNL ScheduledRestart.cfg]的新檔案。
1. 在[!DNL ScheduledRestart.cfg]檔案中輸入以下文本：

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
      <td colname="col2"> <p>您想要首次重新啟動<span class="keyword"> Insight Server </span>的時間。 </p> <p>範例：2013年8月13日東22:30:00年 </p> <p> <p>注意： 必須指定時區。 如果未指定，時區不預設為系統時間。 如果要實作日光節約時間或類似的時鐘轉移政策，必須儲存<span class="filepath"> .dst </span>檔案，其中包含Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span>電腦中的適當規則。 如需支援的時區縮寫清單以及實施日光節約時間的相關資訊，請參閱<a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211">時區代碼</a>。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>頻率</i> </td> 
      <td colname="col2"> <p>以下任一值： 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">個月 </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">週 </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">天 </li> 
       </ul> </p> <p>指出在「開始時間」中指定的初始時間之後，您要重新啟動<span class="keyword"> Insight Server </span>的頻率。 </p> <p>例如，如果您想要<span class="keyword"> Insight Server </span>每週重新啟動一次，您可將此值設為「week」。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 保存[!DNL ScheduledRestart.cfg]檔案。

   確認[!DNL ScheduledRestart.cfg]檔案位於[!DNL Insight Server]安裝目錄的[!DNL Components]資料夾中。
