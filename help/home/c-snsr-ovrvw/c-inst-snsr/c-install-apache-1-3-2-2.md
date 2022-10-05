---
description: 為在Microsoft Windows Server 2000或更新版本下運行的Apache Server 1.3、Apache Server 2.0.42或更新版本，或Apache Server 2.2安裝和配置Sensor的說明。
title: Windows Server 2000 或更新版本上的 Apache Server 1.3、2、2.2 或 2.4
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
exl-id: d1bd0fc1-da5b-4183-8270-73c46195f724
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 1%

---

# Windows Server 2000 或更新版本上的 Apache Server 1.3、2、2.2 或 2.4{#apache-server-or-on-windows-server-or-later}

{{eol}}

為在Microsoft Windows Server 2000或更新版本下運行的Apache Server 1.3、Apache Server 2.0.42或更新版本，或Apache Server 2.2安裝和配置Sensor的說明。

Sensor的程式檔案將打包在安裝檔案中，您可從Adobe下載站點獲取該檔案。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案(或從Adobe代表處獲取)，然後再開始執行以下步驟。

* Apache Server 1.3
* Apache Server 2.0.42或更新版本
* 在Microsoft Windows Server 2000或更新版本下執行的Apache Server 2.2

## 安裝程式檔案 {#section-2f3e85083b4f4aa989a85997330e86ae}

在安裝程式檔案之前，必須確定要在哪個位置維護磁碟隊列，因為這也是必須安裝程式檔案的位置。提取和安裝Sensor的程式檔案的過程。

要安裝和配置Sensor，必須執行以下步驟：

1. 在Windows電腦上，建立要安裝感測器程式檔案的目錄。 請記住，磁碟隊列也駐留在此目錄中，因此，請確保您選擇的設備有足夠的空間容納所需大小的隊列。

   ```
   C:\VisualSensor
   ```

1. 將安裝檔案的內容解壓縮至您剛建立的目錄。 在此步驟中，Sensor會安裝下列檔案：

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
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
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> 收集器模組。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>架構師可用來設定受控實驗的Excel試算表檔案。 Sensor不使用此檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用於驗證Insight Server在連線程式期間所提供數位憑證的憑證。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> 發射機程式 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 感測器配置檔案 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安裝套件包含名為TestExperience.xls的試算表檔案。 這個試算表是一種工具，建築師們用來配置受控實驗。 Sensor本身不使用此檔案，因此不需要在運行Sensor的電腦上安裝該檔案（儘管您可以選擇安裝）。 您可能會想要將檔案複製到架構師可存取的位置，或視需要從安裝套件中擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight受控實驗指南。

## 編輯感測器配置檔案 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

此 [!DNL txlogd.conf] 檔案包含Sensor的配置參數。

您必須編輯此檔案，以指定磁碟佇列檔案的大小和位置、Insight Server的位址，以及將附加至此感測器產生之事件資料的ID。

設定檔案包含必要參數和選用參數。

* **必要參數** 是安裝Sensor時必須指定的設定。 沒有這些設定，Sensor將無法成功運行。
* **選用參數** 是預設為預先定義值（您可以修改）或啟用可選功能的設定。

**編輯Sensor配置檔案**

* 開啟 [!DNL /etc/txlogd.conf] 檔案，並設定所需的參數以及任何所需的選用參數。
* 儲存並關閉檔案。

**編輯Sensor配置檔案**

1. 開啟 [!DNL /etc/txlogd.conf] 檔案，並設定所需的參數以及任何所需的選用參數。
1. 儲存並關閉檔案。

## 啟動發射器並建立磁碟隊列 {#section-55630de65f264274aefd771da2002852}

設定txlogd.conf檔案後，您可以啟動傳送器程式、將其註冊為Windows服務，然後建立磁碟佇列。

1. 如果磁碟隊列所在的目錄尚未存在，請建立它。 確保目錄為收集器模組和發送器程式提供對檔案的讀/寫訪問。

   有關磁碟隊列檔案所需權限的詳細資訊，請參閱Sensor UNIX File Permissions。
1. 在安裝Sensor的電腦上，執行以下命令以啟動發射器：

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * 此命令中的「i」選項會以「互動式模式」啟動傳送器。 此模式在螢幕上顯示發射器消息，還允許您使用鍵盤命令與發射器交互。
   * &quot;c&quot;選項會引導傳送器建立磁碟佇列。
   * 「f」選項指定配置檔案的位置。

   有關啟動發射器時可使用的選項的其他資訊，請參閱感測器發射器命令行選項。

1. 驗證發送器已在QueueFile參數中指定的位置和QueueSize參數中指定的大小中建立磁碟隊列。
1. 如果未正確建立隊列，請鍵入Ctrl+C以終止發送器，然後執行以下操作：

   1. 檢查txtlogd.conf檔案，並驗證QueueFile和QueueSize參數設定正確。
   1. 檢查分配給磁碟隊列的設備是否正常運行，並且有足夠的空間容納在QueueSize參數中指定的大小的檔案。
   1. 進行任何必要的更正，並重複此過程。

## 將收集器添加到Web伺服器 {#section-c5b83ae4ebce430aa764f951e849b333}

對於Apache伺服器，收集器是您載入到Web伺服器進程中的動態共用對象。

若要將收集器新增至Web伺服器，您必須編輯 [!DNL httpd.conf] 檔案（如下所述），然後重新啟動您的Web伺服器。

>[!NOTE]
>
>如果Sensor正在為伺服器電腦上的多個Web伺服器捕獲資料，則必須對每個Web伺服器執行以下過程。

1. 使用文字編輯器，開啟 [!DNL httpd.conf]檔案，用於Sensor捕獲的事件。
1. 將下列兩行加到檔案結尾：

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >這些行區分大小寫。 請按上方顯示的方式輸入。

1. 重新啟動Web伺服器進程（您不必重新啟動整個伺服器電腦，只需重新啟動Web伺服器進程即可）。 收集器隨Web伺服器載入，並開始收集事件資料並將其寫入磁碟隊列。
