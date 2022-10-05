---
description: 安裝和配置Sensor for J2EE實現的詳細說明，這些Sensor在RedHat Linux 7.x或更高版本、Sun Solaris SPARC 2.6或更高版本或Sun Solaris x86 9或更高版本上運行。
title: RedHat Linux 或 Sun Solaris 上的 JBoss、Tomcat 和 WebLogic Server
uuid: 7977fb9b-1737-4e1d-80c6-aabf968974dd
exl-id: 09c2f266-2ecc-42fc-98b6-b91f8883af0c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1823'
ht-degree: 1%

---

# RedHat Linux 或 Sun Solaris 上的 JBoss、Tomcat 和 WebLogic Server{#jboss-tomcat-and-weblogic-servers-on-redhat-linux-or-sun-solaris}

{{eol}}

安裝和配置Sensor for J2EE實現的詳細說明，這些Sensor在RedHat Linux 7.x或更高版本、Sun Solaris SPARC 2.6或更高版本或Sun Solaris x86 9或更高版本上運行。

Sensor的程式檔案將打包在安裝檔案中，您可從Adobe下載站點獲取該檔案。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案(或從Adobe代表處獲取)，然後再開始執行以下步驟。

支援的J2EE實施包括：

* JBoss Server 3.2.x或更新版本
* Apache Jakarta Tomcat Server 4.1或更新版本
* WebLogic Server 6.x或更新版本

要安裝和配置Sensor，必須執行以下步驟：

## 安裝程式檔案 {#section-2f3e85083b4f4aa989a85997330e86ae}

提取和安裝Sensor程式檔案的過程。

1. 以根用戶或具有根權限的用戶身份登錄。
1. 使用以下命令解壓縮安裝檔案：

   * 在Linux上：

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * 在Solaris上：

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
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
>安裝套件包含名為TestExperience.xls的試算表檔案。 這個試算表是一種工具，建築師們用來配置受控實驗。 Sensor本身不使用此檔案，因此不需要在運行Sensor的電腦上安裝該檔案（儘管您可以選擇安裝）。 您可能會想要將檔案複製到架構師可存取的位置，或視需要從安裝套件中擷取檔案。 如需受控實驗的詳細資訊，請參閱Insight受控實驗指南。

**程式檔案的權限**

>[!NOTE]
>
>安裝Sensor時，程式檔案權限不正確會導致大部分問題。 請務必依照本節所述完全設定權限。
>
>預設情況下，tar檔案中的程式檔案具有以下權限。 根據系統配置方式，在解壓檔案時，這些設定可能會更改（未被遮罩）。 要將權限重置為建議的預設設定，請使用下面的chmod命令。 檢查您已安裝檔案的目錄是否至少允許此訪問級別。

| 檔案 | 預設權限 | chmod命令 |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx -x | chmod 711 |
| txlogd.conf | rw-r— r— | chmod 664 |
| trust_ca_cert.pem | rw-r— r— | chmod 664 |

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
       <param-value>/etc/txlogd.conf</param-value> 
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

## 測試感測器 {#section-0dae181ef8884f10a57f6cfda8500969}

確認收集器正在收集事件資料，而傳送器正在將其傳送至目標Insight Server。

>[!NOTE]
>
>若要確認傳輸器可成功將事件資料傳送至Insight Server，請確定目標Insight Server已安裝且執行，然後您才開始進行下列測試。

1. 如果傳輸器尚未運行，請使用以下命令重新啟動它：

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. 開啟瀏覽器（在任何電腦上），並從Sensor正在運行的Web伺服器中請求一個頁面（請務必選擇Sensor正在監視的頁面）。
1. 在您發出請求後，請檢查傳送器的主控台，以取得指出其正在傳送事件資料至目標Insight Server的訊息。
1. 如果感測器未成功傳輸資料，請驗證：

   * 目標Insight Server正在執行。
   * 在txtlogd.conf中正確設定ServerAddress和ServerPort參數。 如果您使用伺服器名稱指定了伺服器地址，請嘗試改用其數值IP地址。
   * CertName參數的值與目標Insight Server數位憑證上顯示的通用名稱完全相符。

## 將發射器添加到系統啟動指令碼 {#section-19a38f27c9f44adf88f8910f5ed483a3}

有關自動將發射器載入到系統啟動指令碼的資訊。

要確保發送器在重新啟動Web伺服器電腦時自動載入，請將以下命令（啟動發送器）添加到系統啟動指令碼中：

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令將發送器作為守護程式啟動。 發送器生成的操作和錯誤消息被寫入 [!DNL syslog].

預設的Solaris設定為60。 根據使用Sensor進行的測試（每個例項使用三個信號）,Adobe建議您使用1024作為設定。 此數量足夠高，Sensor可以與伺服器上任何其他可能需要信號的應用程式一起運行，但不會影響效能。 為支援這一建議，請注意，Adrian Cockcroft在其《Sun Performance and Tuning》（1994年10月，Prentice Hall）一書中指出：「資料庫往往使用大量共用記憶體和信號量設定。 這些不會影響效能；只要它們足夠大，這些計畫就會運行。」

## 擷取其他資料 {#section-9483b663cbd0432daaca50c1089c7fca}

所有平台的感測器都可以收集HTTP要求和回應標題中可用的任何資料。

J2EE平台的感測器提供了一種收集其他平台上不可用資料的機制。 J2EE平台（J2EE收集器）的收集器位於應用程式層上，這使它能夠收集僅應用程式可用、不應通過頁面標籤或標題公開的敏感資料。

>[!NOTE]
>
>雖然頁面標籤和標題修改可隱藏資料，但使用瀏覽器外掛程式工具檢查頁面原始碼或查看標題的使用者仍可使用資料。

例如，J2EE收集器可用來擷取頁面上所顯示連結、頁面上敏感合作夥伴資訊和許多其他資料點的每次點按成本(CPC)資料。 J2EE環境可讓您輕鬆修改WEBAPP，以使用我們的收集器類別擷取此自訂資料。

當J2EE平台的感測器收到請求時，它調用匯入appendToLog函式的收集器類。 appendToLog函式會將appendToLog函式中指定的查詢字串參數附加到初始請求中。 這會導致初始請求的URI包含與正在捕獲的資料的名稱和值相對應的其他查詢字串名稱值對。 例如，當特定廣告版位或點進連結的值為20美分時，CPC=20會附加至初始請求。 Insight Server會將這些值處理至資料集中以進行分析。 此收集方法的另一個優點是，它可以收集其他資料，而不會建立額外的記錄項目，使用頁面標籤方法可能會建立這些項目。

如需處理的詳細資訊，請參閱資料集設定指南。

**從頁面擷取其他資料**

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
