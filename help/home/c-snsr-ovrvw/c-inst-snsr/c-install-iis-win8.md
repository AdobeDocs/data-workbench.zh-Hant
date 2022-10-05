---
description: 安裝並配置在Microsoft Windows Server 2008或更新版本下運行的Microsoft IIS 7.x或8.x感測器。
title: Windows Server 2008 或更新版本上的 Microsoft IIS
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
exl-id: cc909daa-60c0-4188-8e90-035c41bf3105
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 1%

---

# Windows Server 2008 或更新版本上的 Microsoft IIS{#microsoft-iis-on-windows-server-or-later}

{{eol}}

安裝並配置在Microsoft Windows Server 2008或更新版本下運行的Microsoft IIS 7.x或8.x感測器。

Sensor的程式檔案將打包在安裝檔案中，您可從Adobe下載站點獲取該檔案。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案(或從Adobe代表處獲取)，然後再開始執行以下步驟。

要安裝和配置Sensor，必須執行以下高級步驟：

1. [安裝程式檔案](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [編輯Sensor配置檔案](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [啟動發射器並建立磁碟隊列](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [將收集器添加到Web伺服器](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [擷取其他資料](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## 安裝程式檔案 {#section-cb51e5932a6d40c5b00758a7a51b7578}

在Windows IIS上運行Sensor時，程式檔案和磁碟隊列檔案必須位於同一目錄中。

安裝程式檔案之前，請先確定要在哪個位置維護磁碟隊列，因為必須在哪裡安裝程式檔案。

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

## 編輯Sensor配置檔案 {#section-1e1590a92222430e92066292512ae0df}

txlogd.conf檔案包含Sensor的配置參數。

您必須編輯檔案，以指定磁碟佇列的大小、Insight Server的位址，以及將附加至此感測器產生之資料的ID。 設定檔案包含必要參數和選用參數。

* **必要參數** 是安裝Sensor時必須指定的設定。 沒有這些設定，Sensor將無法成功運行。
* **選用參數** 是預設為預先定義值（您可以修改）或啟用可選功能的設定。

**編輯Sensor配置檔案**

1. 開啟 `<SensorDirectory>/txlogd.conf` 檔案，並設定所需的參數以及任何所需的選用參數。

   如需 [!DNL txlogd.conf] 參數，請參閱 [Sensor Txlogd.conf檔案參數](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed).

1. 儲存並關閉檔案。

## 啟動發射器並建立磁碟隊列 {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

設定 [!DNL txlogd.conf]檔案中，可以啟動發送器程式，將其註冊為Windows服務，然後建立磁碟隊列。

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
1. 驗證發送器已在安裝感測器程式檔案的目錄中建立磁碟隊列(Diskq2008.log)，並且該隊列的大小是您在txlogd.conf檔案的QueueSize參數中指定的大小。

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

## 將收集器添加到Web伺服器 {#section-088960c986cf449cb712152298b3518d}

對於IIS，收集器是一個ISAPI篩選器，您將其添加到IIS中的Web伺服器。

1. 使用開啟IIS管理器 **「開始」>「管理工具」>「Internet資訊服務(IIS)管理器」**.
1. 展開 **本地電腦** 和 **網站** 節點。
1. 選取網站，然後在右窗格中，按兩下 **ISAPI篩選器**.
1. 在 **動作** 按一下 **新增**.

1. 在 **篩選器名稱** 欄位，輸入篩選器的顯示名稱。 建議的篩選器名稱為「Sensor」。
1. 按一下 **瀏覽**，選擇qlog.dll檔案（位於安裝Sensor的目錄中），然後按一下 **確定**.

1. 按一下 **確定** 來新增篩選器。

   新增篩選器後，收集器會立即運作並準備好收集資料。

如果流量流向收集器後沒有顯示綠色箭頭，請完成下列步驟：

1. 按一下「開始」>「管理工具」>「事件查看器」，以檢查事件查看器中是否有錯誤。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而異。

1. 在「事件查看器」窗口的左窗格中，選擇 **應用程式** 記錄檔。
1. 在右窗格中，尋找在 **來源** 欄。
1. 如果發現錯誤，請連按兩下錯誤以顯示 **事件屬性** 窗口。

## 擷取其他資料 {#section-98db9625efdc4b60bfd76f7adf4af74d}

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

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->
