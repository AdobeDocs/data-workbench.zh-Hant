---
description: 有關安裝和配置Apache Server 1.3、Apache Server 2.0.42或更新版本或Microsoft Windows Server 2000或更新版本下運行Apache Server 2.2的感測器的說明。
title: Windows Server 2000或更高版本上的Apache Server 1.3、2、2.2或2.4
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Server 2000或更高版本上的Apache Server 1.3、2、2.2或2.4{#apache-server-or-on-windows-server-or-later}

有關安裝和配置Apache Server 1.3、Apache Server 2.0.42或更新版本或Microsoft Windows Server 2000或更新版本下運行Apache Server 2.2的感測器的說明。

感測器的程式檔案將打包在您從Adobe下載站點獲得的安裝檔案中。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案（或從Adobe代表處獲取），然後開始執行以下步驟。

* Apache Server 1.3
* Apache Server 2.0.42或更新版本
* 在Microsoft Windows Server 2000或更高版本下運行的Apache Server 2.2

## 安裝程式檔案 {#section-2f3e85083b4f4aa989a85997330e86ae}

在安裝程式檔案之前，必須確定要在哪裡維護磁碟隊列，因為在那裡，您必須安裝程式檔案。為感測器解壓和安裝程式檔案的過程。

要安裝和配置感測器，必須執行以下步驟：

1. 在Windows電腦上，建立一個目錄以安裝感測器程式檔案。 請記住，您的磁碟隊列也位於此目錄中，因此，請確定您選擇的設備有足夠的空間容納所需大小的隊列。

   ```
   C:\VisualSensor
   ```

1. 將安裝檔案的內容解壓到剛建立的目錄中。 在此步驟中，感測器將安裝以下檔案：

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
   <td colname="col1"> <p>TestEnperity.xls </p> </td> 
   <td colname="col2"> <p>架構師可用來設定受控實驗的Excel試算表檔案。 感測器不使用此檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用於驗證Insight Server在連線程式中呈現之數位憑證的憑證。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> 發射器程式 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 感測器配置檔案 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安裝套件包含名為TestEnperity.xls的試算表檔案。 這個試算表是建築師用來設定受控實驗的工具。 感測器本身不使用此檔案，因此無需在運行感測器的電腦上安裝該檔案（儘管可以選擇安裝）。 您可能會想要將檔案複製至建築師可存取的位置，或視需要從安裝套件擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight Controlled Experies Guide。

## 編輯感測器配置檔案 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

該文 [!DNL txlogd.conf] 件包含感測器的配置參數。

您必須編輯此檔案，以指定磁碟隊列檔案的大小和位置、Insight Server的地址以及將附加到此感測器生成的事件資料的ID等。

配置檔案包含必需參數和可選參數。

* **必要參數** 是安裝感測器時必須指定的設定。 沒有這些設定，感測器無法成功運行。
* **可選參數** ，是預設為預先定義值（您可修改）或啟用可選功能的設定。

**編輯感測器配置檔案**

* 在文字 [!DNL /etc/txlogd.conf] 編輯器中開啟檔案，並設定所需參數以及任何所需的選用參數。
* 儲存並關閉檔案。

**編輯感測器配置檔案**

1. 在文字 [!DNL /etc/txlogd.conf] 編輯器中開啟檔案，並設定所需參數以及任何所需的選用參數。
1. 儲存並關閉檔案。

## 啟動發射器並建立磁碟隊列 {#section-55630de65f264274aefd771da2002852}

配置txlogd.conf檔案後，可以啟動發射器程式，將其註冊為Windows服務，並建立磁碟隊列。

1. 如果磁碟隊列所在的目錄尚不存在，請建立該目錄。 確保目錄為收集器模組和發射器程式提供對檔案的讀／寫訪問。

   有關磁碟隊列檔案所需權限的詳細資訊，請參見Sensor UNIX File Permissions。
1. 在安裝感測器的電腦上，執行以下命令以啟動發射器：

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * 此命令中的&quot;i&quot;選項以&quot;互動式模式&quot;啟動發射器。此模式在螢幕上顯示發射器消息，還允許您使用鍵盤命令與發射器交互。
   * &quot;c&quot;選項指示發射器建立磁碟隊列。
   * &quot;f&quot;選項指定配置檔案的位置。
   有關啟動發射器時可使用的選項的詳細資訊，請參閱感測器發射器命令行選項。

1. 驗證發射器是否已在QueueFile參數中指定的位置和QueueSize參數中指定的大小中建立磁碟隊列。
1. 如果未正確建立隊列，請鍵入Ctrl+C以終止發射器，然後執行以下操作：

   1. 檢查txtlogd.conf檔案並驗證QueueFile和QueueSize參數設定正確。
   1. 檢查分配了磁碟隊列的設備是否工作，並且有足夠的空間容納QueueSize參數中指定的大小的檔案。
   1. 進行任何必要的更正並重複此步驟。

## 將收集器添加到Web伺服器 {#section-c5b83ae4ebce430aa764f951e849b333}

對於Apache伺服器，收集器是一個動態共用對象，您將其載入到Web伺服器進程中。

要將收集器添加到Web伺服器，必須按照下面所述編 [!DNL httpd.conf] 輯檔案並重新啟動Web伺服器。

>[!NOTE]
>
>如果感測器正在捕獲伺服器電腦上多個Web伺服器的資料，則必須對每個Web伺服器執行以下過程。

1. 使用文本編輯器開啟Sensor [!DNL httpd.conf]捕獲事件的Web伺服器的檔案。
1. 將下列兩行新增至檔案結尾：

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >這些行區分大小寫。 請依上方顯示的方式輸入。

1. 重新啟動Web伺服器進程（您不必重新啟動整個伺服器電腦，只需重新啟動Web伺服器進程）。 收集器隨Web伺服器載入，開始收集事件資料並將其寫入磁碟隊列。

