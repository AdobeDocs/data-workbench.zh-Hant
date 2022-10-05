---
description: 您必須設定目標Insight Server，以從儲存原始事件資料的中繼器擷取資料。
title: 設定複寫服務
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# 設定複寫服務{#configuring-the-replication-service}

{{eol}}

您必須設定目標Insight Server，以從儲存原始事件資料的中繼器擷取資料。

配置從 [!DNL Repeater] 目標 [!DNL Insight Server]，您必須編輯 [!DNL Replicate.cfg] 檔案 [!DNL Components] 目標上的資料夾 [!DNL Insight Server(s)] 如下列程式所述：

**若要設定 [!DNL Replication Service] 在目標電腦上**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。
1. 以滑鼠右鍵按一下目標的圖示 [!DNL Insight Server] 要配置，請按一下 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL Replicate.cfg] 檔案位於此目錄中。
1. 以滑鼠右鍵按一下 *伺服器名稱* 欄 [!DNL Replicate.cfg] 按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Replicate.cfg].
1. 在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 此 [!DNL Replicate.cfg] 窗口。
1. 在 [!DNL Replicate.cfg] 按一下 **[!UICONTROL Replicate.cfg]**，然後 **[!UICONTROL component]** 來檢視其內容。
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
      <td colname="col2"> <p>上的目錄 <span class="wintitle"> 中繼器</span> 將複製（複製）到目標 <span class="keyword"> Insight Server</span>. 此 <span class="wintitle"> 復寫服務</span> 允許從單個目錄複製多個目錄 <span class="wintitle"> 中繼器</span>. </p> <p>要添加新目錄，請按一下右鍵 <span class="uicontrol"> 目錄</span> 按一下 <span class="uicontrol"> 新增</span> &gt; <span class="uicontrol"> 目錄</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 平面化路徑 </td> 
      <td colname="col2"> <p>True或False。 由此參數的設定定義的操作取決於此檔案中Recursive參數的設定： 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">如果遞歸為false，平面化路徑將無效。 僅複製由遠程URI參數指定的目錄的頂級檔案。 </li>
      <li id="li_8FDB351102344E3995035557445354BB">如果遞歸為true，平面化路徑為false，則遠程(<span class="wintitle"> 中繼器</span>)目錄完全複製到目標上的本機路徑中 <span class="keyword"> Insight Server</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">如果遞歸路徑和平面化路徑均為true，則不會在本地路徑中建立子目錄。 相反，遠程目錄樹中的所有檔案都放在本地目錄的頂層。 </li>
      </ul></p> <p> <p>注意：如果「平面化路徑」和「遞歸」都為true，且遠程電腦上各個子目錄中的檔案共用相同的名稱，則 <span class="wintitle"> 復寫服務</span> 可能停止，或可能發生其他未定義的行為。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 本機路徑 </td> 
      <td colname="col2">從中檢索的檔案的儲存位置 <span class="wintitle"> 中繼器</span>. 路徑相對於 <span class="keyword"> Insight Server</span> 安裝目錄。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 遞歸 </td> 
      <td colname="col2"> True或False。 如果為false，則僅複製由遠程URI參數指定的目錄的頂級檔案。 請參閱此表格中的平面化路徑。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 遠程URI </td> 
      <td colname="col2">訪問URI的URI（包括檔案掩碼） <span class="wintitle"> 中繼器</span> 檔案存放區。 此 <span class="filepath"> Communications.cfg</span> 檔案 <span class="wintitle"> 中繼器</span> 應進行配置，以便使用此URI訪問事件資料。 請參閱 <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> 監控事件資料空間</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 伺服器 </td> 
      <td colname="col2">適用於 <span class="wintitle"> 中繼器</span> 從目標 <span class="keyword"> Insight Server</span> 擷取事件資料檔案。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 名稱 </td> 
      <td colname="col2">選填。用以識別 <span class="wintitle"> 中繼器</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL伺服器公用名稱 </td> 
      <td colname="col2">只有在「使用SSL」設為true時才需要。 公用名稱 <span class="wintitle"> 中繼器</span> 儲存事件資料的位置。 此名稱必須與電腦的通信證書中列出的通用名稱匹配。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 地址 </td> 
      <td colname="col2">主機名或數值IP地址 <span class="wintitle"> 中繼器</span> 儲存事件資料的位置。 伺服器的常用名稱不是有效條目。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 埠 </td> 
      <td colname="col2"> 用於資料傳輸的埠。 預設連接埠為 80。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL用戶端憑證 </td> 
      <td colname="col2">只有在「使用SSL」設為true時才需要。 用於連接到的許可證證書的名稱 <span class="wintitle"> 中繼器</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 使用SSL </td> 
      <td colname="col2"> <p>確定是否將SSL用於資料傳輸。 選項為true或false，預設值為false。 </p> <p> <p>注意：不建議使用SSL，因為這可能對效能造成負面影響。 請注意，除非網路連接 <span class="wintitle"> 中繼器</span> 目標電腦不安全。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 結束時間、開始時間 </td> 
      <td colname="col2"> <p>（可選）限制複製到目標的事件資料檔案集 <span class="keyword"> Insight Server</span> 包含「開始時間」和「結束時間」所定義範圍內資料的訪客。 如果設定了「開始時間」，則不會複製所有日誌條目都早於指定開始時間的事件資料檔案。 如果設定了「結束時間」，則不會複製指定或更新時間的所有日誌條目的事件資料檔案。 如果檔案中只有一部分資料在指定範圍內，則整個檔案將被複製到目標電腦。 </p> <p>Adobe建議您暫時使用下列其中一種格式： 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">2013年1月1日HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">2013年1月1日HH:MM:SS GMT </li>
      </ul></p> <p> <p>注意：必須指定時區。 如果未指定，時區不預設為系統時間。 如果要實施日光節約時間或類似的時鐘轉移政策，則必須保存 <span class="filepath"> .dst</span> 檔案包含Base\Dataset\Timezone目錄中的適當規則 <span class="keyword"> Insight Server</span> 機器。 如需支援的時區縮寫清單，以及實作日光節約時間的相關資訊，請參閱 <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> 時區代碼</a>. </p> </p> <p> <p>注意：若要使用這些設定，事件資料檔案的名稱必須以ISO日期(YYYYMMDD)開頭，且每個檔案必須包含從該日期上午12點開始的24小時期間資料。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.
   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄和選取 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

此示例說明如果「平面化路徑」和「遞歸」參數均設定為true，則如何複製檔案。

假設遠程URI為 [!DNL /RemoteRoot/] 且本機路徑為[!DNL E:\LocalRoot\]。 在遠端( [!DNL Repeater])，檔案的組織如下：

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
>如果遠程電腦上各個子目錄中的檔案具有相同名稱，則 [!DNL Replication Service] 可能停止，或可能發生其他未定義的行為。
