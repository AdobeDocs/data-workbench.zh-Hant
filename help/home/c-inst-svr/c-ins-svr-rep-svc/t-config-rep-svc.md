---
description: 您必須設定目標Insight Server，以從儲存原始事件資料的中繼器擷取資料。
title: 設定複寫服務
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 2%

---

# 設定複寫服務{#configuring-the-replication-service}

您必須設定目標Insight Server，以從儲存原始事件資料的中繼器擷取資料。

要配置從[!DNL Repeater]到目標[!DNL Insight Server]的資料檢索，必須按以下過程中所述編輯目標[!DNL Insight Server(s)]上[!DNL Components]資料夾中提供的[!DNL Replicate.cfg]檔案：

**在目標電 [!DNL Replication Service] 腦上配置**

1. 在[!DNL Insight]中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要配置的目標[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以查看其內容。 [!DNL Replicate.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL Replicate.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Replicate.cfg]的[!DNL Temp]列中出現複選標籤。
1. 在[!DNL Temp]欄中按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 將開啟[!DNL Replicate.cfg]窗口。
1. 在[!DNL Replicate.cfg]視窗中，按一下&#x200B;**[!UICONTROL Replicate.cfg]**，然後按一下&#x200B;**[!UICONTROL component]**&#x200B;以檢視其內容。
1. 使用下列範例和表格作為參考線來編輯參數：

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
      <td colname="col2"> <p>要複製（複製）到目標<span class="keyword"> Insight Server</span>的<span class="wintitle">中繼器</span>上的目錄。 <span class="wintitle">複製服務</span>允許從單個<span class="wintitle">中繼器</span>複製多個目錄。 </p> <p>要添加新目錄，請按一下右鍵<span class="uicontrol">目錄</span>，然後按一下<span class="uicontrol">新增</span> &gt; <span class="uicontrol">目錄</span>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 平面化路徑 </td> 
      <td colname="col2"> <p>True 或 False. 由此參數的設定定義的操作取決於此檔案中Recursive參數的設定： 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">如果遞歸為false，平面化路徑將無效。 僅複製由遠程URI參數指定的目錄的頂級檔案。 </li>
      <li id="li_8FDB351102344E3995035557445354BB">如果遞歸為true且平面化路徑為false，則遠程（<span class="wintitle">中繼器</span>）目錄的目錄結構將完全複製到目標<span class="keyword"> Insight Server</span>上的本機路徑中。 </li>
      <li id="li_3114B191C73744658799E112C61AB004">如果遞歸路徑和平面化路徑均為true，則不會在本地路徑中建立子目錄。 相反，遠程目錄樹中的所有檔案都放在本地目錄的頂層。 </li>
      </ul></p> <p> <p>注意：如果平面化路徑和遞歸都為true，並且遠程電腦上的各個子目錄中的檔案共用相同的名稱，則<span class="wintitle">複製服務</span>可能會停止，或者可能發生其他未定義的行為。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 本機路徑 </td> 
      <td colname="col2">從<span class="wintitle">中繼器</span>中擷取的檔案的儲存位置。 路徑相對於<span class="keyword"> Insight Server</span>安裝目錄。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 遞歸 </td> 
      <td colname="col2"> True 或 False. 如果為false，則僅複製由遠程URI參數指定的目錄的頂級檔案。 請參閱此表格中的平面化路徑。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 遠程URI </td> 
      <td colname="col2">訪問<span class="wintitle">中繼器的</span>檔案儲存的URI，包括檔案掩碼。 <span class="wintitle">中繼器</span>上的<span class="filepath"> Communications.cfg</span>檔案應進行配置，以便使用此URI訪問事件資料。 請參閱<a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440">監控事件資料空間</a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 伺服器 </td> 
      <td colname="col2"><span class="wintitle">中繼器</span>的參數，目標<span class="keyword"> Insight Server</span>從中擷取事件資料檔案。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 名稱 </td> 
      <td colname="col2">選填。用於標識<span class="wintitle">中繼器</span>的名稱。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL伺服器公用名稱 </td> 
      <td colname="col2">只有在「使用SSL」設為true時才需要。 儲存事件資料的<span class="wintitle">中繼器</span>的通用名稱。 此名稱必須與電腦的通信證書中列出的通用名稱匹配。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 地址 </td> 
      <td colname="col2">儲存事件資料的<span class="wintitle">中繼器</span>的主機名或數值IP地址。 伺服器的常用名稱不是有效條目。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 連接埠 </td> 
      <td colname="col2"> 用於資料傳輸的埠。 預設連接埠為 80。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL用戶端憑證 </td> 
      <td colname="col2">只有在「使用SSL」設為true時才需要。 用於連接到<span class="wintitle">中繼器</span>的許可證證書的名稱。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 使用SSL </td> 
      <td colname="col2"> <p>確定是否將SSL用於資料傳輸。 選項為true或false，預設值為false。 </p> <p> <p>注意：不建議使用SSL，因為這可能對效能造成負面影響。 請注意，除非將<span class="wintitle">中繼器</span>連接到目標電腦的網路不安全，否則不需要SSL。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 結束時間、開始時間 </td> 
      <td colname="col2"> <p>（選用）將複製到目標<span class="keyword"> Insight Server</span>的事件資料檔案集限制為包含由「開始時間」和「結束時間」定義之範圍內資料的檔案集。 如果設定了「開始時間」，則不會複製所有日誌條目都早於指定開始時間的事件資料檔案。 如果設定了「結束時間」，則不會複製指定或更新時間的所有日誌條目的事件資料檔案。 如果檔案中只有一部分資料在指定範圍內，則整個檔案將被複製到目標電腦。 </p> <p>Adobe建議您暫時使用下列其中一種格式： 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">2013年1月1日HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">2013年1月1日HH:MM:SS GMT </li>
      </ul></p> <p> <p>注意：必須指定時區。 如果未指定，時區不預設為系統時間。 如果要實作日光節約時間或類似的時鐘轉移政策，必須儲存<span class="filepath"> .dst</span>檔案，其中包含Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span>電腦中的適當規則。 如需支援的時區縮寫清單以及實施日光節約時間的相關資訊，請參閱<a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211">時區代碼</a>。 </p> </p> <p> <p>注意： 若要使用這些設定，事件資料檔案的名稱必須以ISO日期(YYYYMMDD)開頭，且每個檔案必須包含從該日期上午12點開始的24小時期間資料。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
   1. 在[!DNL Server Files Manager]中，按一下右鍵[!DNL Temp]列中檔案的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

此示例說明如果「平面化路徑」和「遞歸」參數均設定為true，則如何複製檔案。

假設遠程URI為[!DNL /RemoteRoot/]，本地路徑為 [!DNL E:\LocalRoot\]。 在遠程([!DNL Repeater])電腦上，檔案的組織如下：

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

複製完成時，本地目錄具有以下檔案：

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

在本地目錄中，不會建立子目錄，並且遠程目錄樹中的所有檔案都放在本地目錄的頂層。

>[!NOTE]
>
>如果遠程電腦上各個子目錄中的檔案具有相同名稱，則[!DNL Replication Service]可能會停止，或者可能發生其他未定義的行為。
