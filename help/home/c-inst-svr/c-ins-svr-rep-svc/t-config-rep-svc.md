---
description: 您必須設定目標Insight伺服器，以便從儲存原始事件資料的中繼器擷取資料。
title: 設定複寫服務
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 2%

---

# 設定複寫服務{#configuring-the-replication-service}

您必須設定目標Insight伺服器，以便從儲存原始事件資料的中繼器擷取資料。

要配置從[!DNL Repeater]到目標[!DNL Insight Server]的資料檢索，必須編輯目標[!DNL Insight Server(s)]上[!DNL Components]資料夾中提供的[!DNL Replicate.cfg]檔案，如以下過程所述：

**要在目標 [!DNL Replication Service] 電腦上配置**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要配置的目標[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;查看其內容。 [!DNL Replicate.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL Replicate.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL Replicate.cfg]的[!DNL Temp]欄中會出現複選標籤。
1. 在[!DNL Temp]欄中按一下新建立的核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 將開啟[!DNL Replicate.cfg]窗口。
1. 在[!DNL Replicate.cfg]視窗中，按一下&#x200B;**[!UICONTROL Replicate.cfg]**，然後按一下&#x200B;**[!UICONTROL component]**&#x200B;以檢視其內容。
1. 使用下列範例和表格作為參考線編輯參數：

   ![步驟資訊](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 對於此參數…… </th> 
      <th colname="col2" class="entry"> 指定分類的... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> 目錄 </td> 
      <td colname="col2"> <p>要複製（複製）到目標<span class="keyword"> Insight Server</span>的<span class="wintitle"> Repeater</span>上的目錄。 <span class="wintitle">複製服務</span>允許從單個<span class="wintitle">中繼器</span>複製多個目錄。 </p> <p>要添加新目錄，請按一下右鍵<span class="uicontrol">目錄</span> ，然後按一下<span class="uicontrol">添加新</span> &gt; <span class="uicontrol">目錄</span>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 平面化路徑 </td> 
      <td colname="col2"> <p>True 或 False. 此參數設定所定義的動作取決於此檔案中遞歸參數的設定： 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">如果「遞歸」為false，則「平面化路徑」不會產生任何效果。 僅複製遠程URI參數所指定目錄頂級的檔案。 </li>
      <li id="li_8FDB351102344E3995035557445354BB">如果遞歸為true而平面化路徑為false，則遠端(<span class="wintitle"> Repeater</span>)目錄的目錄結構會精確複製到目標<span class="keyword"> Insight Server</span>上的本機路徑中。 </li>
      <li id="li_3114B191C73744658799E112C61AB004">如果「遞歸路徑」和「平面化路徑」都為true，則本地路徑中不會建立子目錄。 而是將遠程目錄樹中的所有檔案放在本地目錄的頂層。 </li>
      </ul></p> <p> <p>注意：如果「平面化路徑」和「遞歸」都為真，並且遠程電腦上各個子目錄中的檔案共用相同的名稱，則<span class="wintitle">複製服務</span>可能會停止，或者可能發生其他未定義的行為。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 本機路徑 </td> 
      <td colname="col2">從<span class="wintitle">中繼器</span>檢索到的檔案的儲存位置。 路徑相對於<span class="keyword"> Insight Server</span>安裝目錄。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 遞歸 </td> 
      <td colname="col2"> True 或 False. 如果為false，則僅複製遠程URI參數所指定目錄頂級的檔案。 請參閱此表格中的平面化路徑。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 遠程URI </td> 
      <td colname="col2">URI（包括檔案遮色片）可存取<span class="wintitle"> Repeater的</span>檔案存放區。 應設定<span class="wintitle">中繼器</span>上的<span class="filepath"> Communications.cfg</span>檔案，以便使用此URI存取事件資料。 請參閱<a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440">監視事件資料空間</a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 伺服器 </td> 
      <td colname="col2">目標<span class="keyword"> Insight Server</span>從中檢索事件資料檔案的<span class="wintitle">中繼器</span>參數。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 名稱 </td> 
      <td colname="col2">選填。用以識別<span class="wintitle"> Repeater</span>的名稱。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL伺服器通用名稱 </td> 
      <td colname="col2">只有當「使用SSL」設為true時才需要。 儲存事件資料的<span class="wintitle">中繼器</span>的公用名稱。 此名稱必須與電腦通信證書中列出的公用名稱匹配。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 地址 </td> 
      <td colname="col2">儲存事件資料的<span class="wintitle">中繼器</span>的主機名或數字IP地址。 伺服器的公用名稱不是有效的項目。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 連接埠 </td> 
      <td colname="col2"> 用於資料傳輸的埠。 預設連接埠為 80。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL用戶端憑證 </td> 
      <td colname="col2">只有當「使用SSL」設為true時才需要。 用於連接<span class="wintitle"> Repeater</span>的許可證證書的名稱。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 使用SSL </td> 
      <td colname="col2"> <p>判斷SSL是否用於資料傳輸。 選項為true或false，預設值為false。 </p> <p> <p>注意：不建議使用SSL，因為它可能對效能有負面影響。 請注意，除非將<span class="wintitle"> Repeater</span>連接至目標電腦的網路不安全，否則不需要SSL。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 結束時間，開始時間 </td> 
      <td colname="col2"> <p>（可選）將複製到目標<span class="keyword"> Insight Server</span>的事件資料檔案集限制為包含「開始時間」和「結束時間」所定義範圍內資料的事件資料檔案集。 如果設定了「開始時間」，則不會複製所有日誌條目都早於指定開始時間的事件資料檔案。 如果設定了「結束時間」，則不會複製指定或更新時間的所有日誌條目的事件資料檔案。 如果檔案中的部分資料只在指定範圍內，則整個檔案將被複製到目標電腦。 </p> <p>Adobe建議目前使用下列其中一種格式： 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">2013年1月1日美國東部夏令時間 </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">2013年1月1日HH:MM:SS GMT </li>
      </ul></p> <p> <p>注意：您必須指定時區。 如果未指定，時區不預設為系統時間。 如果您想要實作日光節約時間或類似的時鐘移位政策，則必須儲存<span class="filepath"> .dst</span>檔案，其中包含Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span>機器中的適當規則。 有關支援的時區縮寫和實施日光節約時間的資訊的清單，請參閱<a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211">時區代碼</a>。 </p> </p> <p> <p>注意： 若要使用這些設定，事件資料檔案的名稱必須以ISO日期(YYYYMMDD)開頭，且每個檔案必須包含該日期的24小時期間資料，從12 AM GMT開始。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 執行下列動作，將變更儲存至伺服器：

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
   1. 在[!DNL Server Files Manager]中，按一下右鍵[!DNL Temp]列中檔案的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

此示例說明如果「平面化路徑」和「遞歸」參數都設定為true，則如何複製檔案。

假設遠程URI為[!DNL /RemoteRoot/] ，本地路徑為 [!DNL E:\LocalRoot\]。 在遠程([!DNL Repeater])電腦上，檔案的組織如下：

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

複製完成時，本地目錄具有以下檔案：

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

在本地目錄中，不建立子目錄，並且遠程目錄樹中的所有檔案都放在本地目錄的頂層。

>[!NOTE]
>
>如果遠程電腦上各個子目錄中的檔案具有相同的名稱，則[!DNL Replication Service]可能會停止，或發生其它未定義的行為。
