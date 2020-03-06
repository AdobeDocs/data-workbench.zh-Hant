---
description: 有關在AIX 5.1或更高版本上安裝和配置Sensor for WebSphere 5.x的詳細說明。
solution: Insight
title: AIX上的WebSphere
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AIX上的WebSphere{#websphere-on-aix}

有關在AIX 5.1或更高版本上安裝和配置Sensor for WebSphere 5.x的詳細說明。

您可從Adobe下 [!DNL Sensor] 載網站取得的安裝檔案中，封裝您的程式檔。 如果您尚未擁有特定網頁伺服 [!DNL Sensor] 器的安裝檔案，請先下載（或從您的Adobe代表取得），然後再開始進行下列程式。

>[!NOTE]
>
>WebSphere [!DNL Sensor] 伺服器不支援受控實驗。 如需有關受控實驗的詳細資訊，請參 *閱資料工作台受控實驗指南。*

## 安裝程式檔案 {#section-86f69127278c41bc90b97b68bb40bc6e}

將Sensor程式檔案解壓並安裝到伺服器電腦的過程。

1. 以root用戶或具有root權限的用戶身份登錄。
1. 使用以下命令解壓縮安裝檔案並解壓縮：

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. 將解壓縮的程式檔案複製到下表中標識的目錄：

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 目標目錄 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> 收集器負載模組 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> 收集器載入模組庫 </td> 
   <td colname="col3"> WebSphere /lib目錄 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> 發射器程式 </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--或-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 感測器配置檔案 </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用於驗證Insight Server在連線程式中呈現之數位憑證的憑證 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安裝套件包含名為TestEnperity.xls的試算表檔案。 這個試算表是建築師用來設定受控實驗的工具。 感測器本身不使用此檔案，因此無需在運行感測器的電腦上安裝該檔案（儘管您可以選擇這樣做）。 您可能會想要將檔案複製至建築師可存取的位置，或視需要從安裝套件擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight Controlled Experies Guide。

**程式檔案的權限**

對程式檔案的權限不正確會導致安裝感測器時遇到的大多數問題。

請確定您設定的權限完全符合本節所述。

預設情況下，tar檔案中的程式檔案具有以下權限。 根據系統的配置方式，在提取檔案時，這些設定可能會更改（未被遮罩）。

若要將權限重設為建議的預設設定，請使用下方的chmod命令。

>[!NOTE]
>
>檢查您已安裝檔案的目錄是否至少允許此級別的訪問。

| 檔案 | 預設權限 | chmod命令 |
|---|---|---|
| libvisual_sciences.so | rwx -x -x | chmod 711 |
| J2EECollector.jar | rw-rw-r— | chmod 664 |
| txlogd | rwx -x -x | chmod 711 |
| txlogd.conf | rw-rw-r— | chmod 664 |
| trust_ca_cert.pem | rw-rw-r— | chmod 664 |

如果要使用除建議預設值之外的權限，請查看Sensor UNIX檔案權限中的資訊，以確保您瞭解這些檔案的使用方式。

## 編輯感測器配置檔案 {#section-283c8a92fa8841c1b6034e5f834ef4e7}

txlogd.conf檔案包含感測器的配置參數。

您必須編輯檔案，以指定磁碟隊列的大小、Insight Server的地址以及將附加到此感測器生成的資料的ID等。

配置檔案包含必需參數和可選參數。

* 必需參數是安裝感測器時必須指定的設定。 沒有這些設定，感測器無法成功運行。
* 可選參數是預設為預先定義值（您可修改）或啟用可選功能的設定。

**要編輯配置檔案**

1. 在文字編輯器中開啟/etc/txlogd.conf檔案，並設定所需參數以及任何所需的可選參數。
1. 儲存並關閉檔案。

## 啟動發射器並建立磁碟隊列 {#section-63285a2328604f20a2cb31b3d5cb80e6}

配置txlogd.conf檔案後建立磁碟隊列的過程。

1. 如果磁碟隊列所在的目錄尚不存在，請建立該目錄。 確保目錄為收集器模組和發射器程式提供對檔案的讀／寫訪問。

1. 在安裝感測器的電腦上，執行以下命令以啟動發射器：

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * 此命令中的&quot;i&quot;選項以交互模式啟動發射器。 此模式在螢幕上顯示發射器消息，還允許您使用鍵盤命令與發射器交互。
   * &quot;c&quot;選項指示發射器建立磁碟隊列。
   * &quot;f&quot;選項指定配置檔案的位置。

1. 驗證發射器是否已在QueueFile參數中指定的位置和QueueSize參數中指定的大小中建立磁碟隊列。
1. 如果未正確建立隊列，請鍵入Ctrl+C以終止發射器，然後執行以下操作：

   1. 檢查txtlogd.conf檔案並驗證QueueFile和QueueSize參數設定正確。
   1. 檢查分配了磁碟隊列的設備是否工作，並且有足夠的空間容納QueueSize參數中指定的大小的檔案。
   1. 進行任何必要的更正並重複此步驟。

## 將收集器添加到Web應用程式 {#section-d17297b1193f4e3cb150fb41f754ef12}

對於WebSphere伺服器，收集器在servlet容器中作為篩選器操作。

若要將收集器新增至Web應用程式，請將篩選器新增至Web應用程式的web.xml部署描述檔，然後重新啟動Web應用程式。

1. 使用文本編輯器，開啟Sensor捕獲事件的Web伺服器的web.xml檔案。
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

## 聲明收集器和共用對象檔案的位置 {#section-e641f08999d34a648aaee2111b69ca25}

編輯Websphere啟動指令碼以聲明J2EECollector.jar和libvisual_sciences.so檔案位置的過程。

1. 在Websphere /bin目錄中開啟setupCmdLine.sh檔案。
1. 在定義$WAS_CLASSPATH變數的行後，添加以下行：

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. 在定義$WAS_LIBPATH變數的大小寫塊後，添加以下行：

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Save the [!DNL setupCmdLine.sh] file.

## 測試感測器 {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

啟動傳送器並驗證它是否可成功連接至Insight Server並傳送事件資料至它的程式。

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

## 將發射器添加到系統啟動指令碼 {#section-23bb905100d04f018af93873dd4d5f68}

確保發射器在Web伺服器電腦重新啟動時自動載入的資訊。

將以下命令（啟動發射器）添加到系統啟動指令碼。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令將發射器作為守護程式啟動。 發射器生成的操作消息和錯誤消息將寫入syslog。

## 擷取其他資料 {#section-d5ccf8ee50914a87938e0c17480757e6}

所有平台的感測器都可以收集HTTP請求和回應標頭中可用的任何資料。

J2EE平台的Sensors提供了收集其他平台無法使用的資料的機制。 J2EE平台的收集器（J2EE收集器）位於應用程式層，可讓它收集僅適用於應用程式且不應透過頁面標籤或標題公開的敏感資料。

>[!NOTE]
>
>雖然頁面標籤和頁首修改可隱藏資料，但使用瀏覽器外掛程式工具檢查頁面原始碼或檢視頁首的人，仍可使用它。

例如，J2EE收集器可用來擷取頁面上所顯示連結的每次點按成本(CPC)資料、頁面上的敏感合作夥伴資訊，以及許多其他資料點。 J2EE環境可讓您輕鬆修改WEBAPP，以使用我們的收集器類別擷取此自訂資料。

當J2EE平台的感測器收到請求時，它會叫用匯入appendToLog函式的收集器類別。 appendToLog函式會附加至初始請求中appendToLog函式中指定的查詢字串參數。 這會導致初始請求的URI包含與所擷取資料的名稱和值相對應的其他查詢字串名稱——值配對。 例如，當特定廣告位置或點進連結的值為20美分時，CPC=20會附加至初始請求。 Insight Server會將這些值處理至資料集以進行分析。 此收集方法的另一個好處是，它允許收集其他資料，而不會建立額外的記錄項目，就像使用頁面標籤方法所建立的一樣。

如需有關處理的詳細資訊，請參閱資 *料集設定指南*。

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

