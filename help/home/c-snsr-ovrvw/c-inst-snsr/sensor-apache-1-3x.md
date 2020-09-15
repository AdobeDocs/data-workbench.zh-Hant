---
description: 有關在RedHat Linux 7.x或更高版本、SUSE Linux 9.x或更高版本、Sun Solaris SPARC 2.6或更高版本、Sun Solaris x86 9或更高版本、FreeBSD 4或更高版本或Mac OS X PowerPC上安裝和配置Apache Server 1.3.x的詳細說明。
title: Linux、Sun Solaris、FreeBSD 或 Mac OS X 上的 Apache Server 1.3.x
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---


# Linux、Sun Solaris、FreeBSD 或 Mac OS X 上的 Apache Server 1.3.x{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

有關在RedHat Linux 7.x或更高版本、SUSE Linux 9.x或更高版本、Sun Solaris SPARC 2.6或更高版本、Sun Solaris x86 9或更高版本、FreeBSD 4或更高版本或Mac OS X PowerPC上安裝和配置Apache Server 1.3.x的詳細說明。

感測器的程式檔案將打包在您從Adobe下載站點獲得的安裝檔案中。 如果您尚未擁有特定Web伺服器的感測器安裝檔案，請先下載該檔案（或從Adobe代表處獲取），然後開始執行以下步驟。

要安裝和配置感測器，必須執行以下高級步驟：

## 安裝程式檔案 {#section-aae323e252394212bf4096d65fdd280c}

將感測器程式檔案解壓並安裝到伺服器電腦的說明。

1. 以root用戶或具有root權限的用戶身份登錄。
1. 使用以下命令解壓縮安裝檔案並解壓縮：

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
   <td colname="col2"> 收集器負載模組 </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
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

請確定您所設定的權限完全符合本節所述。

預設情況下，tar檔案中的程式檔案具有以下權限。 根據系統的配置方式，在提取檔案時，這些設定可能會更改（未被遮罩）。 若要將權限重設為建議的預設設定，請使用下方的chmod命令。 檢查您已安裝檔案的目錄是否至少允許此級別的訪問。

| 檔案 | 預設權限 | chmod命令 |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx -x -x | chmod 711 |
| txlogd.conf | rw-rw-r— | chmod 664 |
| trust_ca_cert.pem | rw-rw-r— | chmod 664 |

## Edit the Sensor configuration file {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

該文 [!DNL txlogd.conf] 件包含感測器的配置參數。

您必須編輯檔案，以指定磁碟隊列的大小、Insight Server的地址以及將附加到此感測器生成的資料的ID等。

配置檔案包含必需參數和可選參數。

* 必需參數是安裝感測器時必須指定的設定。 沒有這些設定，感測器無法成功運行。
* 可選參數是預設為預先定義值（您可修改）或啟用可選功能的設定。

編輯感測器配置檔案

1. 在文字編輯器中開啟/etc/txlogd.conf檔案，並設定所需參數以及任何所需的可選參數。
1. 儲存並關閉檔案。

## 啟動發射器並建立磁碟隊列 {#section-a453d912ec3d47aa8e40ccacf527119d}

配置txlogd.conf檔案後建立磁碟隊列的說明。

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

## 將收集器添加到Web伺服器 {#section-a7fb6425956f4f518ae3a7db091b33d2}

對於Apache伺服器，收集器是一個動態共用對象，您將其載入到Web伺服器進程中。

要將收集器添加到Web伺服器，必須按如下所述編輯httpd.conf檔案並重新啟動Web伺服器。

如果感測器正在捕獲伺服器電腦上多個Web伺服器的資料，則必須對每個Web伺服器執行以下過程。

1. 使用文本編輯器開啟Sensor [!DNL httpd.conf] 捕獲事件的Web伺服器的檔案。
1. 在檔案末尾添加以下行：

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >這些行區分大小寫。 請依上方顯示的方式輸入。

1. 重新啟動Web伺服器。 收集器隨Web伺服器載入，並將開始收集事件資料並將其寫入磁碟隊列。

## 測試感測器 {#section-83d9f60b39a6474f9c76bee3e19b2575}

啟動傳送器並驗證它是否能成功連接至Insight Server，並傳送事件資料至它。

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
   * 和 [!DNL ServerAddress] 參 [!DNL ServerPort] 數在中設定正確 [!DNL txtlogd.conf]。

   * 如果您使用 [!DNL ServerAddress] 伺服器名稱指定，請改用其數值IP位址。 參數的值與 [!DNL CertName] 目標Insight Server的數位憑證上顯示的公用名稱完全相符。

## 將發射器添加到系統啟動指令碼 {#section-4e1ffa6e043941ab91411d91d596477a}

確保發射器在Web伺服器電腦重新啟動時自動載入的資訊。

將以下命令（啟動發射器）添加到系統啟動指令碼。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令將發射器作為守護程式啟動。 發射器生成的操作消息和錯誤消息將寫入syslog。

>[!NOTE]
>
>某些Solaris用戶可能會遇到「無法獲取互斥鎖」錯誤。 要使感測器在這些系統上正常運行，需要在檔案/etc/system中添加或編輯以下行：
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>預設的Solaris設定為60。 根據使用Sensor（每個例項使用三個信號）進行的測試，Adobe建議您使用1024做為設定。 此數量足夠高，感測器可以與伺服器上任何其他可能需要信號的應用程式一起運行，但不會影響效能。 為支援此建議，請注意，Adrian Cockcroft在其《Sun Performance and Tuning》一書（Prentice Hall,1994年10月）中指出：「資料庫通常會使用大量共用記憶體和訊號量設定。 這些不會影響效能；只要它們足夠大，程式就會運行。」

