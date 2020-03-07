---
description: 有關在Windows Server 2000或更高版本下運行的Apache Jakarta Tomcat 4.1或更高版本的感測器安裝和配置的詳細說明。
title: Windows Server 2000或更高版本上的Tomcat Server
uuid: 58feec67-ffbb-4f25-8f22-3d109d464e9a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Server 2000或更高版本上的Tomcat Server{#tomcat-server-on-windows-server-or-later}

有關在Windows Server 2000或更高版本下運行的Apache Jakarta Tomcat 4.1或更高版本的感測器安裝和配置的詳細說明。

感測器的程式檔案將打包在您從Adobe下載站點獲得的安裝檔案中。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案（或從Adobe代表處獲取），然後開始執行以下步驟。

支援的J2EE實作包括：

* 在Microsoft Windows Server 2000或更高版本上運行的JBoss Server 4.0.5或更高版本。

要安裝和配置感測器，必須執行以下步驟：

## 安裝程式檔案 {#section-2f3e85083b4f4aa989a85997330e86ae}

解壓並安裝感測器程式檔案的過程。

1. 在Tomcat伺服器上，建立一個目錄以在其中安裝感測器程式檔案。 請記住，您的磁碟隊列位於此目錄中，因此，請確定您選擇的設備有足夠的空間容納所需大小的隊列。

   ```
   C:\VisualSensor
   ```

1. 將安裝檔案的內容解壓到剛建立的目錄中。 在此步驟中，感測器將安裝以下檔案：

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 目標目錄 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> visual_sciences.dll </td> 
   <td colname="col2"> 收集器載入模組。 </td> 
   <td colname="col3"> 在任何目錄中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> 收集器載入模組庫 </td> 
   <td colname="col3"> WEB-INF/lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.exe </p> </td> 
   <td colname="col2"> 發射器程式。 </td> 
   <td colname="col3"> 在任何目錄中 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 感測器配置檔案。 </td> 
   <td colname="col3"> 在任何目錄中 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用於驗證Insight Server在連線程式中呈現之數位憑證的憑證 </td> 
   <td colname="col3"> 在任何目錄中 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安裝套件包含名為的試算表檔案 [!DNL TestExperiment.xls]。 這個試算表是建築師用來設定受控實驗的工具。 感測器本身不使用此檔案，因此無需在運行感測器的電腦上安裝該檔案（儘管可以選擇安裝）。 您可能會想要將檔案複製至建築師可存取的位置，或視需要從安裝套件擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight Controlled Experies Guide。

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

   1. 在「事件查看器」窗口的左窗格中，選擇「應用程式日誌」。
   1. 在右窗格中，尋找「來源」欄中含有「Adobe」的事件。
   1. 如果您在&quot;Adobe&quot;中發現錯誤，請連按兩下錯誤以顯示「事件屬性」視窗。 此窗口提供了有關錯誤的詳細資訊。

1. 檢查完「應用程式記錄檔」後，請關閉「事件檢視器」。
1. 驗證發射器是否已在安裝感測器程式檔案的目錄中建立了磁碟隊列(Diskq2000.log)，並且該隊列是在txlogd.conf檔案的QueueSize參數中指定的大小。

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

## 將收集器添加到Web伺服器 {#section-c5b83ae4ebce430aa764f951e849b333}

對於JBoss伺服器，收集器在servlet容器中作為篩選器操作。

要將收集器添加到Web伺服器，必須按照下面所述編 [!DNL web.xml] 輯檔案並重新啟動Web應用程式。

1. 使用文本編輯器開啟Sensor [!DNL web.xml] 捕獲事件的Web伺服器的檔案。
1. 將下列元素 `<filter>` 和元 `<filter-mapping>` 素添加到描述符檔案中。 如果您未在/etc目錄中安裝txlogd.conf，則需要在元素中輸入此檔案的正確路 `<param-value>` 徑：

   ```
   <filter> 
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping> 
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping> 
   ```

   >[!NOTE]
   >
   >這些行區分大小寫。 請依上方顯示的方式輸入。

1. 重新啟動Web伺服器進程（您不必重新啟動整個伺服器電腦，只需重新啟動Web伺服器進程）。 收集器隨Web伺服器載入，開始收集事件資料並將其寫入磁碟隊列。

## 修改Java庫路徑 {#section-0dae181ef8884f10a57f6cfda8500969}

有關將visual_sciences.dll添加到Tomcat Java庫路徑的說明。

1. 在您的Windows伺服器上，導覽至Tomcat安裝目錄。 (Tomcat > bin)
1. 在bin資料夾下，運行Tomcat9w.exe（常用守護程式服務管理器）。

   在「Java」頁籤的「Java選項」下，添加新行：

   ```
   -Djava.library.path=C:\Sensor directory
   ```

   其中， [!DNL C:\Sensor] 目錄是包含檔案的目 [!DNL visual_sciences.dll] 錄。

## 擷取其他資料 {#section-9483b663cbd0432daaca50c1089c7fca}

您可以使用appendToLog()功能，從以J2EE為基礎的Web應用程式擷取其他測量資料。

1. 將下列程式碼新增至您要擷取資料的。jsp頁面頂端：

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %> 
   ```

1. 使用收集器對象的appendToLog()方法，將所需的名稱——值對附加到請求的。jsp頁的查詢字串。 下列範例會將&quot;A=1&quot;和&quot;B=2&quot;附加至所要求。jsp頁面的/index.jsp頁面查詢字串：

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html> 
   ```

   產生的請求URI為/index.jsp?A=1&amp;B=2。

1. 對要從中捕獲其他資料的每個。jsp頁重複此過程。

