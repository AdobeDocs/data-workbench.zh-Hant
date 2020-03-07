---
description: 有關在Web伺服器系列上安裝和配置感測器的說明，這些Web伺服器系列是從運行在Linux或Solaris電腦上的原始Netscape Enterprise Web Server演變而來。 包括Linux或Solaris上的Netscape Enterprise、iPlanet、Sun ONE和Sun Java System Servers。
title: Linux或Solaris上的Netscape Enterprise
uuid: 47ea614c-d45c-4ab4-a8fe-ed9227da4582
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Linux或Solaris上的Netscape Enterprise{#netscape-enteprise-on-linux-or-solaris}

有關在Web伺服器系列上安裝和配置感測器的說明，這些Web伺服器系列是從運行在Linux或Solaris電腦上的原始Netscape Enterprise Web Server演變而來。 包括Linux或Solaris上的Netscape Enterprise、iPlanet、Sun ONE和Sun Java System Servers。

感測器的程式檔案將打包在您從Adobe下載站點獲得的安裝檔案中。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案（或從Adobe代表處獲取），然後開始執行以下步驟。

感測器支援以下在RedHat Linux 7.x或更高版本或Sun Solaris SPARC 2.6或更高版本下運行的伺服器：

* Netscape Enterprise Server 3.6或更新版本
* iPlanet Web Server 4.0或更新版本

感測器支援在RedHat Linux 7.x或更高版本或Sun Solaris 8.x或更高版本下運行的這些伺服器：

* Sun ONE Web Server 6.0或更高版本
* Sun Java System Web Server 6.1或更新版本

感測器支援在Sun Solaris x86 9或更高版本下運行的這些伺服器：

* Sun Java System Web Server 6.1或更新版本

>[!NOTE]
>
>此Web伺服器系列的安裝檔案在Adobe下載站點上列為「Netscape Solaris感測器」或「Netscape LINUX感測器」。

要安裝和配置感測器，必須執行以下步驟：

## 安裝程式檔案 {#section-2f3e85083b4f4aa989a85997330e86ae}

解壓並安裝感測器程式檔案的過程。

1. 以root用戶或具有root權限的用戶身份登錄。
1. 使用以下命令解壓縮安裝檔案並解壓縮：

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
>預設情況下，tar檔案中的程式檔案具有以下權限。 根據系統的配置方式，在提取檔案時，這些設定可能會更改（未被遮罩）。 若要將權限重設為建議的預設設定，請使用下方的chmod命令。 檢查您已安裝檔案的目錄是否至少允許此級別的訪問。

| 檔案 | 預設權限 | chmod命令 |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx -x -x | chmod 711 |
| txlogd.conf | rw-r— r— | chmod 664 |
| trust_ca_cert.pem | rw-r— r— | chmod 664 |

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

## 將收集器添加到AOL伺服器 {#section-c5b83ae4ebce430aa764f951e849b333}

對於AOLServer，收集器是一個動態共用對象，您將其載入到Web伺服器進程中。

要將收集器添加到AOL伺服器，必須按如下所述編輯伺服器的配置檔案並重新啟動AOL伺服器。 通常，伺服器的設定檔名為nsd.tcl，並位於AOL Server安裝的目錄中。

1. 在文本編輯器中開啟配置檔案並找到以下部分：

   ```
   ns_section "ns/server/${servername}/modules" 
   ```

1. 新增下列行。 (新增為單一陳述式。 忽略下面顯示的換行文字。)

   ```
   ns_param aol_visual_sciences /usr/local/aolserver/visual_sciences/aol_visual_sciences.so 
   ```

1. 按如下方式建立新部分。

   ```
   ns_section "ns/server/${servername}/module/aol_visual_sciences"
   ```

1. 在此新區段中，添加以下行：

   ```
   ns_param    VisualSciencesConfig    /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >這些行區分大小寫。 請依上方顯示的方式輸入。

1. 重新啟動AOL伺服器。 收集器已載入，並將開始收集事件資料並將其寫入磁碟隊列。

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

此命令將發射器作為守護程式啟動。 發送器生成的操作和錯誤消息被寫入 [!DNL syslog]。

預設的Solaris設定為60。 根據使用Sensor（每個例項使用三個信號）進行的測試，Adobe建議您使用1024做為設定。 此數量足夠高，感測器可以與伺服器上任何其他可能需要信號的應用程式一起運行，但不會影響效能。 為支援此建議，請注意，Adrian Cockcroft在其《Sun Performance and Tuning》一書（Prentice Hall,1994年10月）中指出：「資料庫通常會使用大量共用記憶體和訊號量設定。 這些不會影響效能；只要它們足夠大，程式就會運行。」
