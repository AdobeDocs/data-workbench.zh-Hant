---
description: 安裝和配置在Microsoft Windows Server 2000或更新版本下運行的JBoss Server 4.0.5或更新版本的感測器的詳細說明。
title: Windows Server 2000 或更新版本上的 JBoss Server
uuid: b0501749-9479-484b-8876-fe3001825f8d
exl-id: d9001bc4-f3ef-4d26-9190-807194d20ada
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 1%

---

# Windows Server 2000 或更新版本上的 JBoss Server{#jboss-server-on-windows-server-or-later}

{{eol}}

安裝和配置在Microsoft Windows Server 2000或更新版本下運行的JBoss Server 4.0.5或更新版本的感測器的詳細說明。

Sensor的程式檔案將打包在安裝檔案中，您可從Adobe下載站點獲取該檔案。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案(或從Adobe代表處獲取)，然後再開始執行以下步驟。

支援的J2EE實施包括：

* 在Microsoft Windows Server 2000或更新版本上執行的JBoss Server 4.0.5或更新版本。

要安裝和配置Sensor，必須執行以下步驟：

## 安裝程式檔案 {#section-2f3e85083b4f4aa989a85997330e86ae}

提取和安裝Sensor程式檔案的過程。

1. 在JBoss Server上，建立要安裝Sensor程式檔案的目錄。 請記住，磁碟隊列位於此目錄中，因此，請確保您選擇的設備有足夠的空間容納所需大小的隊列。

   ```
   C:\VisualSensor
   ```

1. 將安裝檔案的內容解壓縮至您剛建立的目錄。 在此步驟中，Sensor會安裝下列檔案：

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
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> 收集器載入模組。 </td> 
   <td colname="col3"> <i> IBMHttpServer/模組</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> 發射程式。 </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--或--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 感測器配置檔案。 </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用於驗證Insight Server在連線程式期間所提供數位憑證的憑證 </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安裝套件包含的試算表檔案稱為 [!DNL TestExperiment.xls]. 這個試算表是一種工具，建築師們用來配置受控實驗。 Sensor本身不使用此檔案，因此不需要在運行Sensor的電腦上安裝該檔案（儘管您可以選擇安裝）。 您可能會想要將檔案複製到架構師可存取的位置，或視需要從安裝套件中擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight受控實驗指南。

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

## 將收集器添加到Web伺服器 {#section-c5b83ae4ebce430aa764f951e849b333}

對於JBoss伺服器，收集器作為Servlet容器中的篩選器運作。

若要將收集器新增至Web伺服器，您必須編輯 [!DNL web.xml] 檔案（如下所述），然後重新啟動您的Web應用程式。

1. 使用文字編輯器，開啟 [!DNL web.xml] 檔案，用於Sensor捕獲的事件。
1. 新增下列項目 `<filter>` 和 `<filter-mapping>` 元素。 若您未在/etc目錄中安裝txlogd.conf，您必須在 `<param-value>` 元素：

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
   >這些行區分大小寫。 請按上方顯示的方式輸入。

1. 重新啟動Web伺服器進程（您不必重新啟動整個伺服器電腦，只需重新啟動Web伺服器進程即可）。 收集器隨Web伺服器載入，並開始收集事件資料並將其寫入磁碟隊列。

## 修改啟動指令碼 {#section-0dae181ef8884f10a57f6cfda8500969}

在修改啟動指令碼之前，請確保已在Windows環境中定義JAVA_HOME變數。

在 [!DNL run.bat] 檔案(例如C:\jboss-4.0.5.GA\bin\run.bat)，在檔案結尾附近，在JBoss伺服器啟動命令前面的「echo」行前面添加以下行：

```
set JBOSS_CLASSPATH=%JBOSS_CLASSPATH%;C:\jboss-4.0.5.GA\server\default\lib\javax.servlet.jar;C:\VisualSciences\J2EECollector.jar 
set JAVA_OPTS=%JAVA_OPTS% -Djava.library.path=C:\VisualSciences
```

## 擷取其他資料 {#section-9483b663cbd0432daaca50c1089c7fca}

您可以使用appendToLog()功能，從基於J2EE的Web應用程式中捕獲其他測量資料。

1. 將以下代碼添加到要從中捕獲資料的.jsp頁的頂部：

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %> 
   ```

1. 使用收集器對象的appendToLog()方法將所需的名稱值對附加到請求的.jsp頁的查詢字串。 以下示例將&quot;A=1&quot;和&quot;B=2&quot;附加到/index.jsp頁請求的.jsp頁的查詢字串中：

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

1. 對要從中捕獲其他資料的每個.jsp頁重複此過程。
