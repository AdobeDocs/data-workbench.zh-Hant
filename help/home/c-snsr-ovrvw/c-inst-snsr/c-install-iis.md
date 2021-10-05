---
description: 有關如何安裝和配置在Microsoft Windows Server 2000或更新版本下運行的Sensor for Internet Information Services(IIS)5.x或6.x的說明。
title: Windows Server 2000 或更新版本上的 Microsoft IIS
uuid: 26da0638-82c8-424f-9f00-aab3a940e5a9
exl-id: e4b5ac44-b0ac-43be-9b9c-180a64354081
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1718'
ht-degree: 1%

---

# Windows Server 2000 或更新版本上的 Microsoft IIS{#microsoft-iis-on-windows-server-or-later}

有關如何安裝和配置在Microsoft Windows Server 2000或更新版本下運行的Sensor for Internet Information Services(IIS)5.x或6.x的說明。

使用IIS 6.x時，必須啟用記錄功能，Sensor才能正常運作。 如果您禁用了日誌記錄以減少磁碟I/O，則可以啟用日誌記錄，而無需將任何資料寫入日誌。 要執行此操作，請啟用日誌記錄，然後清除W3C擴展日誌檔案格式「屬性」的「高級」頁簽上的所有欄位。 若您需要協助，請聯絡Adobe諮詢服務。

Sensor的程式檔案將打包在安裝檔案中，您可從Adobe下載站點獲取該檔案。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案(或從Adobe代表處獲取)，然後再開始執行以下步驟。

要安裝和配置Sensor，必須執行以下高級步驟：

## 1.安裝程式檔案 {#section-9ef8c4e38c244b7d8b6d4bc6c0ad53fd}

在Windows IIS上運行Sensor時，程式檔案和磁碟隊列檔案必須位於同一目錄中。

因此，在安裝程式檔案之前，必須確定要在哪個位置維護磁碟隊列，因為這也是必須安裝程式檔案的位置。

使用以下過程提取並安裝Sensor的程式檔案。

1. 在Windows電腦上，建立要安裝感測器程式檔案的目錄。 請記住，磁碟隊列也駐留在此目錄中，因此，請確保您選擇的設備有足夠的空間容納所需大小的隊列。

   例如：C:\VisualSensor

1. 將安裝檔案的內容解壓縮至您剛建立的目錄。 在此步驟中，Sensor會安裝下列檔案：

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
   <td colname="col1"> TestExperiment.xls </td>
   <td colname="col2"> <p>架構師可用來設定受控實驗的Excel試算表檔案。 </p> <p>Sensor不使用此檔案。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> trust_ca_cert.pem </td>
   <td colname="col2"> 用於驗證Insight Server在連線程式期間所提供數位憑證的憑證。 </td>
  </tr>
  <tr>
   <td colname="col1"> TXLog.exe </td>
   <td colname="col2"> 發射程式。 </td>
  </tr>
  <tr>
   <td colname="col1"> txlogd.conf </td>
   <td colname="col2"> 感測器配置檔案。 </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>安裝套件包含名為TestExperience.xls的試算表檔案。 這個試算表是一種工具，建築師們用來配置受控實驗。 Sensor本身不使用此檔案，因此不需要在運行Sensor的電腦上安裝該檔案（儘管您可以選擇安裝）。 您可能會想要將檔案複製到架構師可存取的位置，或視需要從安裝套件中擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight受控實驗指南。

## 2.編輯組態檔 {#section-206daf855e664f16af9a96a5cd3e62b1}

txlogd.conf檔案包含Sensor的配置參數。

您必須編輯檔案，以指定磁碟佇列的大小、Insight Server的位址，以及將附加至此感測器產生之資料的ID。 設定檔案包含必要參數和選用參數。

* **必** 需參數是安裝Sensor時必須指定的設定。沒有這些設定，Sensor將無法成功運行。
* **可** 選參數是預設為預定義值（您可以修改）或啟用可選功能的設定。

**編輯Sensor配置檔案**

1. 在文字編輯器中開啟`<SensorDirectory>/txlogd.conf`檔案，並設定所需的參數以及任何所需的選用參數。

   有關txlogd.conf參數的說明，請參閱Sensor Txlogd.conf檔案參數。

   有關已完成配置檔案的示例，請參閱感測器示例配置檔案。

1. 儲存並關閉檔案。

## 3.啟動發射器並建立磁碟隊列 {#section-a0af390ee1954109bcff5d9f09798683}

設定txlogd.conf檔案後，您可以啟動傳送器程式、將其註冊為Windows服務，然後建立磁碟佇列。

1. 從Windows的「開始」菜單中，選擇「附件」>「命令提示符」。
1. 在命令提示符窗口中，導航到安裝Sensor的目錄，然後執行以下命令：

   ```
   txlog /regserver
   ```

   此命令將啟動發射器、建立磁碟隊列，並將Sensor註冊為Windows服務。

1. 若要確認傳輸器是否正常運作，請按一下「開始>控制面板>管理工具>服務」。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而異。

   1. 在服務清單中，找到Sensor的條目，並確認其狀態為「啟動」，其啟動類型為「自動」。
   1. 關閉「服務」控制面板。

1. 若要檢查傳送器在啟動期間是否發生任何錯誤，請按一下「開始」 > 「控制面板」 > 「管理工具」 > 「事件檢視器」 ，以開啟「事件檢視器」。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而異。

   1. 在「事件查看器」窗口的左窗格中，選擇「應用程式」日誌。
   1. 在右窗格中，查找「源」列中帶有「Adobe」的事件。
   1. 如果從「Adobe」中發現錯誤，請按兩下錯誤以顯示「事件屬性」窗口。 此窗口提供有關錯誤的詳細資訊。

1. 檢查完應用程式日誌後，關閉事件查看器。
1. 驗證發送器已在安裝感測器程式檔案的目錄中建立磁碟隊列(Diskq2000.log)，並且該隊列的大小是您在txlogd.conf檔案的QueueSize參數中指定的大小。

   如果未正確建立隊列：

   1. 檢查txtlogd.conf檔案，並確認QueueSize參數已正確設定。
   1. 檢查Sensor安裝設備上是否有足夠的空間可容納QueueSize參數中指定大小的檔案。
   1. 在Windows中使用「服務」控制面板，停止發射器。
   1. 刪除隊列檔案。
   1. 將Sensor重新註冊為Windows服務：從Windows的「開始」菜單中，選擇「附件」>「命令提示符」。 在命令提示符窗口中，導航到安裝Sensor的目錄，然後執行以下命令：

      ```
      txlog /regserver
      ```

發射器設計為連續運行。 如果重新啟動電腦，發射器會自動重新啟動。 如果您需要手動啟動和停止傳輸器，則可以使用Windows中的「服務」控制面板執行此操作。

## 將收集器添加到Web伺服器 {#section-682dc480e5574791ac18da104daf7906}

對於IIS，收集器是一個ISAPI篩選器，您將其添加到IIS中的Web伺服器。

1. 使用「開始」>「管理工具」>「Internet資訊服務(IIS)管理器」開啟IIS管理器。
1. 展開「本地電腦」和「網站」節點。
1. 按一下右鍵要向其添加收集器的網站，然後選擇「屬性」。
1. 選擇「ISAPI篩選器」頁簽，然後按一下「添加」。
1. 在「篩選器名稱」欄位中，輸入篩選器的顯示名稱。 建議的篩選器名稱為「Sensor」。
1. 按一下瀏覽，選擇qlog.dll檔案（位於安裝Sensor的目錄中），然後按一下確定。
1. 按一下「確定」以新增篩選器。

   新增篩選器後，收集器會立即運作並準備好收集資料。 在「IIS管理器」的「ISAPI篩選器」頁簽的「狀態」列中，應顯示一個向上綠色箭頭。 在流量實際流過篩選器之前，您可能不會看到綠色箭頭。 在這種情況下，您需要向Web伺服器提交請求，以確認收集器運行正常。

如果流量流向收集器後沒有顯示綠色箭頭，請完成下列步驟：

1. 按一下「開始」>「管理工具」>「事件查看器」，以檢查事件查看器中是否有錯誤。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而異。

1. 在「事件查看器」窗口的左窗格中，選擇「應用程式」日誌。
1. 在右窗格中，查找「源」列中帶有「Adobe」的事件。
1. 如果發現錯誤，請按兩下錯誤以顯示「事件屬性」窗口。

## 擷取其他資料 {#section-dcd10073eb1947a5928e4f9b9fa99e3a}

網頁通常使用ASP(Active Server Pages)寫程式語言進行結構化。

ASP是一種在IIS內執行的Microsoft技術。 當瀏覽器請求ASP檔案時，IIS會將請求傳遞給ASP引擎。 ASP引擎逐行讀取ASP檔案，並執行檔案中的指令碼。 最後，ASP檔案以純HTML形式返回到瀏覽器。 ASP提供RESPONDE或REQUEST對象，除了其他實用程式外，還允許從HTML表單提交的用戶查詢或資料的響應或請求。

在某些情況下，您可能不想將輸入表單的值附加至顯示在使用者瀏覽器之位址列中，或可在HTML程式碼本身中檢視的URL。 簡單的伺服器端ASP指令碼可讓您將表單欄位名稱及其各自的值附加至記錄檔，而無須在使用者的瀏覽器中使用或將它們嵌入HTML檔案中。 若要擷取在您網站內特定表單中輸入的實際表單值，必須新增幾行程式碼，將表單值附加至記錄請求。

在表單的處理頁面內，納入下列程式碼，將輸入的表單值附加至請求資料（除了將提交的表單值寫入外部資料庫或其他位置之外）:

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

此程式會將定義的表單值附加至「表單處理」頁面的請求資料。 在記錄檔資料中，附加的值將可作為「表單處理」頁面的查詢字串使用，如下圖所示。 例如， v_1、v_2、v_3和v_4現在將是查詢字串，其中包含輸入到相應表單欄位中的資料。 您可以針對您要擷取的任何其他表單欄位和值複製上述範例中所述的語法：

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

如果您想要擷取每個表單欄位和值並供分析之用，您可以使用下列語法：

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

此範例會取用HTML內顯示的所有表單欄位及其個別值，並將它們附加為「表單處理」頁面的記錄項目中的查詢字串。 請注意，這會包含表單中顯示的任何隱藏欄位。

日誌資料將如下表詳述：

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_1 | 與NAME查詢字串關聯的值 | v_1=John Smith |
| v_2 | 與CITY查詢字串關聯的值 | v_2=洛杉磯 |
| v_3 | 與STATE查詢字串關聯的值 | v_3=加州 |
| v_4 | 與ZIP查詢字串關聯的值 | v_4=90210 |
