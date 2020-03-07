---
description: 有關如何在IBM AIX 5.1或更新版本（在Microsoft Windows Server 2000或更新版本下執行）上安裝和配置IBM HTTP Server的說明。
title: AIX 5.1或更新版本上的IBM HTTP Server
uuid: d4a37ab2-514a-4afb-905b-420159c4ef0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AIX 5.1或更新版本上的IBM HTTP Server{#ibm-http-server-on-aix-or-later}

有關如何在IBM AIX 5.1或更新版本（在Microsoft Windows Server 2000或更新版本下執行）上安裝和配置IBM HTTP Server的說明。

感測器的程式檔案將打包在您從Adobe下載站點獲得的安裝檔案中。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案（或從Adobe代表處獲取），然後開始執行以下步驟。

要安裝和配置感測器，必須執行以下高級步驟：

## 安裝程式檔案 {#section-2f3e85083b4f4aa989a85997330e86ae}

在IBM AIX伺服器上，建立一個目錄，在其中安裝感測器程式檔案。 請記住，您的磁碟隊列也位於此目錄中，因此，請確定您選擇的設備有足夠的空間容納所需大小的隊列。

1. 以root用戶或具有root權限的用戶身份登錄。
1. 使用以下命令解壓縮安裝檔案並解壓縮：

   ```
   tar -zxf installationFilename
   ```

1. 將解壓縮的程式檔案複製到下表中標識的目錄：

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
   <td colname="col2"> 發射器程式。 </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--或--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 感測器配置檔案。 </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用於驗證Insight Server在連線程式中呈現之數位憑證的憑證 </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安裝套件包含名為TestEnperity.xls的試算表檔案。 這個試算表是建築師用來設定受控實驗的工具。 感測器本身不使用此檔案，因此無需在運行感測器的電腦上安裝該檔案（儘管可以選擇安裝）。 您可能會想要將檔案複製至建築師可存取的位置，或視需要從安裝套件擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight Controlled Experies Guide。

**程式檔案的權限**

>[!NOTE]
>
>對程式檔案的權限不正確會導致安裝感測器時遇到的大多數問題。 請確定您設定的權限完全符合本節所述。
>
>預設情況下，tar檔案中的程式檔案具有以下權限。 根據系統的配置方式，在提取檔案時，這些設定可能會更改（未被遮罩）。 若要將權限重設為建議的預設設定，請使用下方的chmod命令。 檢查您已安裝檔案的目錄是否至少允許此訪問級別。

<table id="table_F4A46DBDE0874133B616235C32B6D9F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案 </th> 
   <th colname="col2" class="entry"> 預設權限 </th> 
   <th colname="col3" class="entry"> chmod命令 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> rwx -x -x </td> 
   <td colname="col3"> <p>chmod 711 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> rw-rw-r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> rwx -x -x </td> 
   <td colname="col3"> chmod 711 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> rw-rw-r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> rw-rw-r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
 </tbody> 
</table>

## 編輯感測器配置檔案 {#section-de0eb4a646394b61abb6cd5a2b706de0}

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

## 將收集器添加到Web應用程式 {#section-c5b83ae4ebce430aa764f951e849b333}

對於WebSphere伺服器，收集器在servlet容器中作為篩選器操作。

要將收集器添加到Web應用程式中，請開啟Sensor捕獲事件的Web伺服器的web.xml檔案。

如果感測器正在捕獲伺服器電腦上多個Web伺服器的資料，則必須對每個Web伺服器執行以下過程。

1. 使用文本編輯器，開啟Sensor捕獲事件的Web伺服器的httpd.conf檔案。
1. 將下列元素 `<filter>` 和元 `<filter-mapping>` 素添加到描述符檔案中。 如果您未在/etc目錄中安裝txlogd.conf，則需要在元素中輸入此檔案的正確路 `<param-value>` 徑。

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

1. 重新啟動Web應用程式。 收集器已載入應用程式，並將開始收集事件資料並將其寫入磁碟隊列。

## 聲明收集器和共用對象檔案的位置 {#section-b9c298fa645f4670b2503647d967846f}

編輯Websphere啟動指令碼以聲明J2EECollector.jar和libvisual_sciences.so檔案的位置。

1. 在Websphere /bin目錄中開啟setupCmdLine.sh檔案。
1. 在定義$WAS_CLASSPATH變數的行後，添加以下行：

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. 在定義$WAS_LIBPATH變數的大小寫塊後，添加以下行：

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. 儲存setupCmdLine.sh檔案。

## 測試感測器 {#section-0dae181ef8884f10a57f6cfda8500969}

驗證收集器是否正在收集事件資料，而傳送器正在將它傳送至目標Insight Server。

>[!NOTE]
>
>若要確認發射器可以成功傳送事件資料至Insight Server，請在您開始下列測試前，先確定目標Insight Server已安裝並執行。

1. 如果發射器尚未運行，請使用以下命令重新啟動它：

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. 開啟瀏覽器（在任何電腦上），並從運行感測器的Web伺服器請求一個頁面（請務必選擇感測器監視的頁面）。
1. 在您發出請求後，請檢查傳送器的主控台，以取得指出傳送事件資料至目標Insight伺服器的訊息。
1. 如果感測器未成功傳輸資料，請驗證：

   * 目標Insight伺服器正在執行。
   * 在txtlogd.conf中可以正確設定ServerAddress和ServerPort參數。 如果您使用伺服器名稱指定ServerAddress，請改用其數值IP位址。
   * CertName參數的值與目標Insight Server的數位憑證上顯示的公用名稱完全相符。

## 將發射器添加到系統啟動指令碼 {#section-19a38f27c9f44adf88f8910f5ed483a3}

有關自動將發射器載入到系統啟動指令碼的資訊。

為確保發射器在Web伺服器電腦重新啟動時自動載入，請將以下命令（將啟動發射器）添加到系統啟動指令碼：

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令將發射器作為守護程式啟動。 發射器生成的操作消息和錯誤消息將寫入syslog。

## 擷取其他資料 {#section-bb1c2bccba9b4bc0b52abdbb4f9d42d7}

所有平台的感測器都可以收集HTTP請求和回應標頭中可用的任何資料。

J2EE平台的Sensors提供了收集其他平台無法使用的資料的機制。 J2EE平台的收集器（J2EE收集器）位於應用程式層，可讓它收集僅適用於應用程式且不應透過頁面標籤或標題公開的敏感資料。

>[!NOTE]
>
>雖然頁面標籤和頁首修改可隱藏資料，但使用瀏覽器外掛程式工具檢查頁面原始碼或檢視頁首的人，仍可使用它。

例如，J2EE收集器可用來擷取頁面上所顯示連結的每次點按成本(CPC)資料、頁面上的敏感合作夥伴資訊，以及許多其他資料點。 J2EE環境可讓您輕鬆修改WEBAPP，以使用我們的收集器類別擷取此自訂資料。

當J2EE平台的感測器收到請求時，它會叫用匯入appendToLog函式的收集器類別。 appendToLog函式會附加至初始請求中appendToLog函式中指定的查詢字串參數。 這會導致初始請求的URI包含與所擷取資料的名稱和值相對應的其他查詢字串名稱——值配對。 例如，當特定廣告位置或點進連結的值為20美分時，CPC=20會附加至初始請求。 Insight Server會將這些值處理至資料集以進行分析。 此收集方法的另一個好處是，它允許收集其他資料，而不會建立額外的記錄項目，就像使用頁面標籤方法所建立的一樣。

如需處理的詳細資訊，請參閱資料集設定指南。

要從頁面中捕獲其他資料，請執行以下操作：

1. 將下列程式碼新增至您要擷取資料的。jsp頁面頂端：

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. 使用收集器對象的appendToLog()方法，將所需的名稱——值對附加到請求的。jsp頁的查詢字串。 下列範例會將&quot;A=1&quot;和&quot;B=2&quot;附加至要求的。jsp頁面的/index.jsp頁面查詢字串：

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

