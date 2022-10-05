---
description: 在Web伺服器系列上安裝和配置Sensor的說明，這些Web伺服器是從在Linux或Solaris電腦上運行的原始Netscape Enterprise Web Server演變而來的。 包括Linux或Solaris上的Netscape Enterprise 、 iPlanet 、 Sun ONE和Sun Java System Server。
title: Linux 或 Solaris 上的 Netscape Enterprise
uuid: 47ea614c-d45c-4ab4-a8fe-ed9227da4582
exl-id: bd2e50b9-94fe-4f05-b227-11e83eb0a665
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 1%

---

# Linux 或 Solaris 上的 Netscape Enterprise{#netscape-enteprise-on-linux-or-solaris}

{{eol}}

在Web伺服器系列上安裝和配置Sensor的說明，這些Web伺服器是從在Linux或Solaris電腦上運行的原始Netscape Enterprise Web Server演變而來的。 包括Linux或Solaris上的Netscape Enterprise 、 iPlanet 、 Sun ONE和Sun Java System Server。

Sensor的程式檔案將打包在安裝檔案中，您可從Adobe下載站點獲取該檔案。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案(或從Adobe代表處獲取)，然後再開始執行以下步驟。

Sensor支援以下在RedHat Linux 7.x或更高版本或Sun Solaris SPARC 2.6或更高版本下運行的伺服器：

* Netscape Enterprise Server 3.6或更高版本
* iPlanet Web Server 4.0或更新版本

Sensor支援在RedHat Linux 7.x或更高版本或Sun Solaris 8.x或更高版本下運行的伺服器：

* Sun ONE Web Server 6.0或更高版本
* Sun Java System Web Server 6.1或更高版本

Sensor支援在Sun Solaris x86 9或更高版本下運行的這些伺服器：

* Sun Java System Web Server 6.1或更高版本

>[!NOTE]
>
>此系列Web伺服器的安裝檔案在Adobe下載站點上列為「Netscape Solaris感測器」或「Netscape LINUX Sensor」。

要安裝和配置Sensor，必須執行以下步驟：

## 安裝程式檔案 {#section-2f3e85083b4f4aa989a85997330e86ae}

提取和安裝Sensor程式檔案的過程。

1. 以根用戶或具有根權限的用戶身份登錄。
1. 使用以下命令解壓縮安裝檔案：

   ```
   gunzip installationFilename.tar.gz 
   
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
   <td colname="col1"> aol_visual_sciences.so </td> 
   <td colname="col2"> 收集器載入模組。 </td> 
   <td colname="col3"> <i>/usr/local/aolserver/ visual_sciences</i> </td> 
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

## 將收集器新增至AOL伺服器 {#section-c5b83ae4ebce430aa764f951e849b333}

對於AOLServer，收集器是您載入到Web伺服器進程中的動態共用對象。

若要將收集器新增至您的AOL伺服器，您必須依照下列說明編輯伺服器的設定檔案，然後重新啟動您的AOL伺服器。 伺服器的配置檔案通常名為nsd.tcl，位於安裝AOL伺服器的目錄中。

1. 在文字編輯器中開啟設定檔案，並找到下列區段：

   ```
   ns_section "ns/server/${servername}/modules" 
   ```

1. 新增下列行。 (新增為單一陳述式。 忽略下面顯示的換行。)

   ```
   ns_param aol_visual_sciences /usr/local/aolserver/visual_sciences/aol_visual_sciences.so 
   ```

1. 建立新區段，如下所示。

   ```
   ns_section "ns/server/${servername}/module/aol_visual_sciences"
   ```

1. 新增行至此新區段：

   ```
   ns_param    VisualSciencesConfig    /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >這些行區分大小寫。 請按上方顯示的方式輸入。

1. 重新啟動AOL伺服器。 收集器已載入，並將開始收集事件資料並將其寫入磁碟隊列。

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
