---
description: 安裝和配置在AIX 5.1或更新版本上運行的WebSphere 5.x感測器的詳細說明。
title: AIX 上的 WebSphere
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
exl-id: e560d265-dc84-4ff2-ac86-7a2ac5261451
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 0%

---

# AIX 上的 WebSphere{#websphere-on-aix}

{{eol}}

安裝和配置在AIX 5.1或更新版本上運行的WebSphere 5.x感測器的詳細說明。

的程式檔案 [!DNL Sensor] 會封裝在您從Adobe下載網站取得的安裝檔案中。 如果您尚未擁有 [!DNL Sensor] 安裝檔案，請先下載(或從Adobe代表處取得)，然後再開始下列程式。

>[!NOTE]
>
>此 [!DNL Sensor] 對於WebSphere伺服器，不支援受控實驗。 如需受控實驗的相關資訊，請參閱 *Data Workbench受控實驗指南。*

## 安裝程式檔案 {#section-86f69127278c41bc90b97b68bb40bc6e}

將Sensor的程式檔案解壓並安裝到伺服器電腦的過程。

1. 以根用戶或具有根權限的用戶身份登錄。
1. 使用以下命令解壓縮安裝檔案：

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
   <td colname="col2"> 收集器載入模組 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> 收集器載入模組庫 </td> 
   <td colname="col3"> WebSphere /lib目錄 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> 發射機程式 </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--或-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 感測器配置檔案 </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用於驗證Insight Server在連線程式期間所提供數位憑證的憑證 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安裝套件包含名為TestExperience.xls的試算表檔案。 這個試算表是一種工具，建築師們用來配置受控實驗。 Sensor本身不使用此檔案，因此不需要在運行Sensor的電腦上安裝該檔案（儘管您可以選擇安裝）。 您可能會想要將檔案複製到架構師可存取的位置，或視需要從安裝套件中擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight受控實驗指南。

**程式檔案的權限**

安裝Sensor時，程式檔案權限不正確會導致大部分問題。

請務必依照本節所述完全設定權限。

預設情況下，tar檔案中的程式檔案具有以下權限。 根據系統配置方式，在解壓檔案時，這些設定可能會更改（未被遮罩）。

要將權限重置為建議的預設設定，請使用下面的chmod命令。

>[!NOTE]
>
>檢查您已安裝檔案的目錄是否至少允許此訪問級別。

| 檔案 | 預設權限 | chmod命令 |
|---|---|---|
| libvisual_sciences.so | rwx -x | chmod 711 |
| J2EECollector.jar | rw-rw-r | chmod 664 |
| txlogd | rwx -x | chmod 711 |
| txlogd.conf | rw-rw-r | chmod 664 |
| trust_ca_cert.pem | rw-rw-r | chmod 664 |

如果您想使用建議預設值以外的權限，請查看Sensor UNIX File Permissions（感測器UNIX檔案權限）中的資訊，以確保您了解這些檔案的使用方式。

## 編輯感測器配置檔案 {#section-283c8a92fa8841c1b6034e5f834ef4e7}

txlogd.conf檔案包含Sensor的配置參數。

您必須編輯檔案，以指定磁碟佇列的大小、Insight Server的位址，以及將附加至此感測器產生之資料的ID。

設定檔案包含必要參數和選用參數。

* 必需的參數是安裝Sensor時必須指定的設定。 沒有這些設定，Sensor將無法成功運行。
* 可選參數是預設為預定義值（您可以修改）或啟用可選功能的設定。

**要編輯配置檔案**

1. 在文字編輯器中開啟/etc/txlogd.conf檔案，並設定所需的參數以及任何需要的選用參數。
1. 儲存並關閉檔案。

## 啟動發射器並建立磁碟隊列 {#section-63285a2328604f20a2cb31b3d5cb80e6}

配置txlogd.conf檔案後建立磁碟隊列的過程。

1. 如果磁碟隊列所在的目錄尚未存在，請建立它。 確保目錄為收集器模組和發送器程式提供對檔案的讀/寫訪問。

1. 在安裝Sensor的電腦上，執行以下命令以啟動發射器：

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * 此命令中的「i」選項會以互動模式啟動傳送器。 此模式在螢幕上顯示發射器消息，還允許您使用鍵盤命令與發射器交互。
   * &quot;c&quot;選項會引導傳送器建立磁碟佇列。
   * 「f」選項指定配置檔案的位置。

1. 驗證發送器已在QueueFile參數中指定的位置和QueueSize參數中指定的大小中建立磁碟隊列。
1. 如果未正確建立佇列，請輸入Ctrl+C以終止傳送器，然後執行下列動作：

   1. 檢查txtlogd.conf檔案，並驗證QueueFile和QueueSize參數設定正確。
   1. 檢查分配給磁碟隊列的設備是否正常運行，並且有足夠的空間容納在QueueSize參數中指定的大小的檔案。
   1. 進行任何必要的更正，並重複此過程。

## 將收集器添加到Web應用程式 {#section-d17297b1193f4e3cb150fb41f754ef12}

對於WebSphere伺服器，收集器在Servlet容器中作為篩選器操作。

要將收集器添加到Web應用程式中，請將篩選器添加到Web應用程式的web.xml部署描述符中，然後重新啟動Web應用程式。

1. 使用文本編輯器，開啟Sensor捕獲的Web伺服器的web.xml檔案。
1. 新增下列項目 `<filter>` 和 `<filter-mapping>` 元素。 若您未在/etc目錄中安裝txlogd.conf，您必須在 `<param-value>` 元素。

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

1. 重新啟動Web應用程式。 收集器已載入應用程式，並將開始收集事件資料並將其寫入磁碟隊列。

## 聲明收集器和共用對象檔案的位置 {#section-e641f08999d34a648aaee2111b69ca25}

編輯Websphere啟動指令碼以聲明J2EECollector.jar和libvisual_sciences.so檔案的位置的過程。

1. 在Websphere /bin目錄中開啟setupCmdLine.sh檔案。
1. 在定義$WAS_CLASSPATH變數的行後，添加以下行：

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. 在定義$WAS_LIBPATH變數的大小寫塊後，添加以下行：

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. 儲存 [!DNL setupCmdLine.sh] 檔案。

## 測試感測器 {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

啟動傳送器並確認其可成功連線至Insight Server並傳送事件資料至此程式。

>[!NOTE]
>
>若要確認傳輸器可成功將事件資料傳送至Insight Server，請確定目標Insight Server已安裝且執行，然後您才開始進行下列測試。

1. 如果傳輸器尚未運行，請使用以下命令重新啟動它：

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. 開啟瀏覽器（在任何電腦上），並從Sensor正在運行的Web伺服器中請求一個頁面（請務必選擇Sensor正在監視的頁面）。
1. 在您發出請求後，請檢查傳送器的主控台，以取得指出其正在傳送事件資料至目標Insight Server的訊息。
1. 如果Sensor未成功傳輸資料，請驗證：

   * 目標Insight Server正在執行。
   * 在txtlogd.conf中正確設定ServerAddress和ServerPort參數。 如果您使用伺服器名稱指定了伺服器地址，請嘗試改用其數值IP地址。
   * CertName參數的值與目標Insight Server數位憑證上顯示的通用名稱完全相符。

## 將傳輸器添加到系統啟動指令碼 {#section-23bb905100d04f018af93873dd4d5f68}

確保在重新啟動Web伺服器電腦時自動載入的資訊。

將以下命令（啟動發射器）添加到系統啟動指令碼中。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令將發送器作為守護程式啟動。 發送器生成的操作和錯誤消息將寫入syslog。

## 擷取其他資料 {#section-d5ccf8ee50914a87938e0c17480757e6}

所有平台的感測器都可以收集HTTP要求和回應標題中可用的任何資料。

J2EE平台的感測器提供了一種收集其他平台上不可用資料的機制。 J2EE平台（J2EE收集器）的收集器位於應用程式層上，這使它能夠收集僅應用程式可用、不應通過頁面標籤或標題公開的敏感資料。

>[!NOTE]
>
>雖然頁面標籤和標題修改可隱藏資料，但使用瀏覽器外掛程式工具檢查頁面原始碼或查看標題的使用者仍可使用資料。

例如，J2EE收集器可用來擷取頁面上所顯示連結、頁面上敏感合作夥伴資訊和許多其他資料點的每次點按成本(CPC)資料。 J2EE環境可讓您輕鬆修改WEBAPP，以使用我們的收集器類別擷取此自訂資料。

當J2EE平台的感測器收到請求時，它調用匯入appendToLog函式的收集器類。 appendToLog函式會將appendToLog函式中指定的查詢字串參數附加到初始請求中。 這會導致初始請求的URI包含與正在捕獲的資料的名稱和值相對應的其他查詢字串名稱值對。 例如，當特定廣告版位或點進連結的值為20美分時，CPC=20會附加至初始請求。 Insight Server會將這些值處理至資料集中以進行分析。 此收集方法的另一個優點是，它可以收集其他資料，而不會建立額外的記錄項目，使用頁面標籤方法可能會建立這些項目。

如需處理的詳細資訊，請參閱 *資料集組態指南*.

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
