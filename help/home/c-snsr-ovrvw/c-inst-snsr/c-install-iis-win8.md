---
description: 安裝並配置在Microsoft Windows Server 2008或更高版本下運行的Microsoft IIS 7.x或8.x感測器。
title: Windows Server 2008或更高版本上的Microsoft IIS
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Server 2008或更高版本上的Microsoft IIS{#microsoft-iis-on-windows-server-or-later}

安裝並配置在Microsoft Windows Server 2008或更高版本下運行的Microsoft IIS 7.x或8.x感測器。

感測器的程式檔案將打包在您從Adobe下載站點獲得的安裝檔案中。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案（或從Adobe代表處獲取），然後開始執行以下步驟。

要安裝和配置感測器，必須執行以下高級步驟：

1. [安裝程式檔案](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [編輯感測器配置檔案](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [啟動發射器並建立磁碟隊列](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [將收集器添加到Web伺服器](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [擷取其他資料](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## 安裝程式檔案 {#section-cb51e5932a6d40c5b00758a7a51b7578}

在Windows IIS上運行感測器時，程式檔案和磁碟隊列檔案必須位於同一目錄中。

在安裝程式檔案之前，請先確定要在哪裡維護磁碟隊列，因為必須在哪裡安裝程式檔案。

請按下列步驟解壓並安裝感測器的程式檔案。

1. 在Windows電腦上，建立一個目錄以安裝感測器程式檔案。 請記住，您的磁碟隊列也位於此目錄中，因此，請確定您選擇的設備有足夠的空間容納所需大小的隊列。

   例如：C:\VisualSensor

1. 將安裝檔案的內容解壓到剛建立的目錄中。 在此步驟中，感測器將安裝以下檔案：

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> 事件檢視器訊息。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> qlog.dll </td> 
   <td colname="col2"> 收集器模組（ISAPI篩選器）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TestEnperity.xls </td> 
   <td colname="col2"> <p>架構師可用來設定受控實驗的Excel試算表檔案。 </p> <p>感測器不使用此檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用於驗證Insight Server在連線程式中呈現之數位憑證的憑證。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> 發射器程式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 感測器配置檔案。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安裝套件包含名為TestEnperity.xls的試算表檔案。 這個試算表是建築師用來設定受控實驗的工具。 感測器本身不使用此檔案，因此無需在運行感測器的電腦上安裝該檔案（儘管可以選擇安裝）。 您可能會想要將檔案複製至建築師可存取的位置，或視需要從安裝套件擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight Controlled Experies Guide。

## 編輯感測器配置檔案 {#section-1e1590a92222430e92066292512ae0df}

txlogd.conf檔案包含感測器的配置參數。

您必須編輯檔案，以指定磁碟隊列的大小、Insight Server的地址以及將附加到此感測器生成的資料的ID等。 配置檔案包含必需參數和可選參數。

* **必要參數** 是安裝感測器時必須指定的設定。 沒有這些設定，感測器無法成功運行。
* **可選參數** ，是預設為預先定義值（您可修改）或啟用可選功能的設定。

**編輯感測器配置檔案**

1. 在文字 `<SensorDirectory>/txlogd.conf` 編輯器中開啟檔案，並設定所需參數以及任何所需的選用參數。

   有關參數的 [!DNL txlogd.conf] 說明，請參 [見Sensor Txlogd.conf File Parameters](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed)。

1. 儲存並關閉檔案。

## 啟動發射器並建立磁碟隊列 {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

配置檔案後， [!DNL txlogd.conf]可以啟動發射器程式，將其註冊為Windows服務，並建立磁碟隊列。

1. 從Windows的「開始」菜單中，選擇「附件」>「命令提示符」。
1. 在命令提示符窗口中，導航到安裝Sensor的目錄並執行以下命令：

   ```
   txlog /regserver
   ```

   此命令將啟動發射器、建立磁碟隊列，並將感測器註冊為Windows服務。

1. 若要確認發射器是否正常運作，請按一下「開始>控制面板>管理工具>服務」。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而異。

   1. 在服務清單中，找到感測器條目並確認其狀態為「啟動」，其啟動類型為「自動」。
   1. 關閉「服務」控制面板。

1. 若要檢查發射器在啟動期間是否發生任何錯誤，請按一下「開始>控制面板>管理工具>事件檢視器」以開啟事件檢視器。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而異。

   1. 在「事件查看器」窗口的左窗格中，選擇「應用程式日誌」。
   1. 在右窗格中，尋找「來源」欄中含有「Adobe」的事件。
   1. 如果您在&quot;Adobe&quot;中發現錯誤，請連按兩下錯誤以顯示「事件屬性」視窗。 此窗口提供了有關錯誤的詳細資訊。

1. 檢查完「應用程式記錄檔」後，請關閉「事件檢視器」。
1. 驗證發射器是否已在安裝感測器程式檔案的目錄中建立了磁碟隊列(Diskq2008.log)，並且該隊列是在txlogd.conf檔案的QueueSize參數中指定的大小。

   如果未正確建立隊列：

   1. 檢查txtlogd.conf檔案並驗證QueueSize參數設定正確。
   1. 檢查安裝感測器的設備是否有足夠的空間容納QueueSize參數中指定的大小的檔案。
   1. 使用Windows中的「服務」控制面板，停止發射器。
   1. 刪除隊列檔案。
   1. 將感測器重新註冊為Windows服務：從Windows的「開始」菜單中，選擇「附件」>「命令提示符」。 在命令提示符窗口中，導航到安裝Sensor的目錄並執行以下命令：

      ```
      txlog /regserver
      ```

該發射機設計為連續運行。 如果重新啟動電腦，發射器會自動重新啟動。 如果您需要手動啟動和停止發射器，則可使用Windows中的「服務」控制面板執行此操作。

## 將收集器添加到Web伺服器 {#section-088960c986cf449cb712152298b3518d}

對於IIS，收集器是您在IIS中添加到Web伺服器的ISAPI過濾器。

1. 使用「開始」>「管 **理工具」>「Internet資訊服務(IIS)管理器」開啟IIS管理器**。
1. 展開「本 **地電腦** 」和「 **站點** 」節點。
1. 選取網站，然後在右窗格中，按兩下「 **ISAPI篩選器」**。
1. 在「動作 **」窗格** 下，按一下「 **新增」**。

1. 在「篩 **選器名稱** 」欄位中，輸入篩選器的顯示名稱。 建議的篩選器名稱為「感測器」。
1. 單 **擊瀏覽**，選擇qlog.dll檔案（位於安裝感測器的目錄中），然後按一下 **確定**。

1. 按一 **下「確定** 」以新增篩選。

   新增篩選器後，收集器會立即運作並準備收集資料。

如果流量流向收集器後未出現綠色箭頭，請完成以下步驟：

1. 按一下「開始>管理工具>事件檢視器」，檢查事件檢視器是否有錯誤。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而異。

1. 在「事件查看器」窗口的左窗格中，選擇「應用 **程式日誌** 」。
1. 在右窗格中，尋找「來源」欄中有「Adobe」的 **事件** 。
1. 如果您發現錯誤，請連按兩下錯誤以顯示「事件 **屬性** 」視窗。

## 擷取其他資料 {#section-98db9625efdc4b60bfd76f7adf4af74d}

網頁通常採用ASP(Active Server Pages)寫程式語言結構。

ASP是一種在IIS中運行的Microsoft技術。 當瀏覽器要求ASP檔案時，IIS會將要求傳送至ASP引擎。 ASP引擎逐行讀取ASP檔案，並執行檔案中的指令碼。 最後，ASP檔案會以純HTML格式傳回至瀏覽器。 ASP提供RESPONSE或REQUEST物件，除了其他實用程式外，還允許回應或要求使用者查詢或從HTML表單提交的資料。

在某些情況下，您可能不想將輸入表單的值附加至顯示在使用者瀏覽器位址列中或可在HTML程式碼本身檢視的URL。 簡單的伺服器端ASP指令碼可讓您將表單欄位名稱及其個別值附加至記錄檔，而不需在使用者的瀏覽器中使用或將它們內嵌至HTML檔案。 若要擷取在網站內特定表單中輸入的實際表單值，必須新增幾行程式碼，才能將表單值附加至記錄請求。

在表單的處理頁面中，請包含下列程式碼，將輸入的表單值附加至請求資料（除了將提交的表單值寫入外部資料庫或其他位置之外）:

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

此程式會將定義的表單值附加至「表單處理」頁的請求資料。 在記錄檔資料中，附加的值可當成「表單處理」頁面的查詢字串，如下圖所示。 例如，v_1、v_2、v_3和v_4現在將是查詢字串，包含輸入到適當表單欄位中的資料。 您可以針對您要擷取的任何其他表單欄位和值，複製前述範例中所述的語法：

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

如果您想要擷取每個表單欄位和值並加以分析，可以使用下列語法：

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues);
```

此範例會取用HTML中顯示的所有表單欄位及其個別值，並將它們附加為查詢字串至「表單處理」頁面的記錄項目。 請注意，這將包含表單中顯示的任何隱藏欄位。

日誌資料將被增加，如下表中所詳述：

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_1 | 與NAME查詢字串關聯的值 | v_1=John Smith |
| v_2 | 與CITY查詢字串關聯的值 | v_2=洛杉磯 |
| v_3 | 與STATE查詢字串關聯的值 | v_3=加州 |
| v_4 | 與ZIP查詢字串關聯的值 | v_4=90210 |

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->

