---
description: 有關在RedHat Linux 7.x或更高版本、SUSE Linux 9.x或更高版本、Sun Solaris SPARC 2.6或更高版本、Sun Solaris x86 9或更高版本、FreeBSD 4或更高版本或Mac OS X PowerPC上安裝和配置Apache Server 1.3.x的詳細說明。
title: Linux、Sun Solaris、FreeBSD 或 Mac OS X 上的 Apache Server 1.3.x
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---

# Linux、Sun Solaris、FreeBSD 或 Mac OS X 上的 Apache Server 1.3.x{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

{{eol}}

有關在RedHat Linux 7.x或更高版本、SUSE Linux 9.x或更高版本、Sun Solaris SPARC 2.6或更高版本、Sun Solaris x86 9或更高版本、FreeBSD 4或更高版本或Mac OS X PowerPC上安裝和配置Apache Server 1.3.x的詳細說明。

Sensor的程式檔案將打包在安裝檔案中，您可從Adobe下載站點獲取該檔案。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案(或從Adobe代表處獲取)，然後再開始執行以下步驟。

要安裝和配置Sensor，必須執行以下高級步驟：

## 安裝程式檔案 {#section-aae323e252394212bf4096d65fdd280c}

將Sensor的程式檔案解壓並安裝到伺服器電腦的說明。

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

<table id="table_A97CF630633C4543A742D96C302D1138"> 
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
   <td colname="col2"> 收集器載入模組 </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
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

預設情況下，tar檔案中的程式檔案具有以下權限。 根據系統配置方式，在解壓檔案時，這些設定可能會更改（未被遮罩）。 要將權限重置為建議的預設設定，請使用下面的chmod命令。 檢查您已安裝檔案的目錄是否至少允許此訪問級別。

| 檔案 | 預設權限 | chmod命令 |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx -x | chmod 711 |
| txlogd.conf | rw-rw-r | chmod 664 |
| trust_ca_cert.pem | rw-rw-r | chmod 664 |

## 編輯Sensor配置檔案 {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

此 [!DNL txlogd.conf] 檔案包含Sensor的配置參數。

您必須編輯檔案，以指定磁碟佇列的大小、Insight Server的位址，以及將附加至此感測器產生之資料的ID。

設定檔案包含必要參數和選用參數。

* 必需的參數是安裝Sensor時必須指定的設定。 沒有這些設定，Sensor將無法成功運行。
* 可選參數是預設為預定義值（您可以修改）或啟用可選功能的設定。

編輯Sensor配置檔案

1. 在文字編輯器中開啟/etc/txlogd.conf檔案，並設定所需的參數以及任何需要的選用參數。
1. 儲存並關閉檔案。

## 啟動發射器並建立磁碟隊列 {#section-a453d912ec3d47aa8e40ccacf527119d}

設定txlogd.conf檔案後建立磁碟佇列的指示。

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

## 將收集器添加到Web伺服器 {#section-a7fb6425956f4f518ae3a7db091b33d2}

對於Apache伺服器，收集器是您載入到Web伺服器進程中的動態共用對象。

若要將收集器新增至您的Web伺服器，您必須依照以下說明編輯httpd.conf檔案，然後重新啟動您的Web伺服器。

如果Sensor正在為伺服器電腦上的多個Web伺服器捕獲資料，則必須對每個Web伺服器執行以下過程。

1. 使用文字編輯器，開啟 [!DNL httpd.conf] 檔案，用於Sensor捕獲的事件。
1. 將下列行加入檔案結尾：

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >這些行區分大小寫。 請按上方顯示的方式輸入。

1. 重新啟動Web伺服器。 收集器已載入Web伺服器，並將開始收集事件資料並將其寫入磁碟隊列。

## 測試感測器 {#section-83d9f60b39a6474f9c76bee3e19b2575}

啟動傳送器，並確認其可以成功連線至Insight Server並傳送事件資料至它。

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
   * 此 [!DNL ServerAddress] 和 [!DNL ServerPort] 參數在中正確設定 [!DNL txtlogd.conf].

   * 如果您指定 [!DNL ServerAddress] 請使用伺服器名稱，嘗試改用其數值IP位址。 的值 [!DNL CertName] 參數完全符合目標Insight Server數位憑證上顯示的通用名稱。

## 將傳輸器添加到系統啟動指令碼 {#section-4e1ffa6e043941ab91411d91d596477a}

確保在重新啟動Web伺服器電腦時自動載入的資訊。

將以下命令（啟動發射器）添加到系統啟動指令碼中。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令將發送器作為守護程式啟動。 發送器生成的操作和錯誤消息將寫入syslog。

>[!NOTE]
>
>某些Solaris用戶可能遇到「無法獲取互斥鎖」錯誤。 要使Sensor在這些系統上正常工作，需要在檔案/etc/system中添加或編輯以下行：
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>預設的Solaris設定為60。 根據使用Sensor進行的測試（每個例項使用三個信號）,Adobe建議您使用1024作為設定。 此數量足夠高，Sensor可以與伺服器上任何其他可能需要信號的應用程式一起運行，但不會影響效能。 為支援這一建議，請注意，Adrian Cockcroft在其《Sun Performance and Tuning》（1994年10月，Prentice Hall）一書中指出：「資料庫往往使用大量共用記憶體和信號量設定。 這些不會影響效能；只要它們足夠大，這些計畫就會運行。」
