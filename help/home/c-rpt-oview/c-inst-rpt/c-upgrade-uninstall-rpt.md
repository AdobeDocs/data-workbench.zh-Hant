---
description: 有關升級和解除安裝報表伺服器軟體的資訊。
solution: Analytics
title: 升級和卸載報告伺服器
topic: Data workbench
uuid: 42f0d190-1a88-424d-be4b-90338144d287
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 升級和卸載報告伺服器{#upgrading-and-uninstalling-report-server}

有關升級和解除安裝報表伺服器軟體的資訊。

* [升級報告](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [解除安裝報表](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## 升級報表伺服器 {#section-95fea4bddad74616a8aea450dcdb2282}

如果您要升級 [!DNL Report Server] 至5.4版，可以使用說明升級軟 [!DNL Report Server] 體。 如果您使用 [!DNL Report Server] 3.6或更舊版本，請聯絡Adobe以取得升級協助。

若要升 [!DNL Report Server] 級5.4，請使用資料工作台將升級檔案複製至連線的資料工作台 [!DNL Report Server] 伺服器。 執行此動作後， [!DNL Report] 當伺服器執行個體連線至該伺服器並載入描述檔時，就會自動升級。

>[!NOTE]
>
>在升級 [!DNL Report Server]之前，請確定您已正確升級資料工作台伺服器軟體以及資料工作台伺服器上執行的設定檔。 如需詳細資訊，請聯絡Adobe諮詢服務。

要執行以下過程，首先必須獲取升級檔案 [!DNL Report Server]。

**升級至[!DNL Report Server]5.4及更新版本**

1. 備份此目錄下的所有檔案， [!DNL E:\Portal] 並刪除該目錄內的所有檔案和資料夾。
1. 將新內部版本的內容複製到中 [!DNL E:\Portal]。
1. 依照上 [!DNL global.asa]一節 [!DNL email.asp]中的說 [!DNL TopNavigation.xml] 明修改、修改和。

1. 從備份 [!DNL users.mdb] 中複製。

   >[!NOTE]
   >
   >如果您先前未產生。png輸出的報表，您必須進入個別的報表資料夾並修改，以包 [!DNL reports.xml] 含png的報表格式。 否則，可能會出現500錯誤。 您的原 [!DNL reports.xml] 稿看起來類似下列：

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   它需要修改為：

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. 在中 [!DNL report.cfg]，加入png的輸出格式並儲存。 未來，它應產生png格式的報表。

**升級至[!DNL Report Server]4.0**

1. 在資料工作台電腦上，將報表伺服器升級檔案複製至 [!DNL Temp\Software] 資料工作台安裝目錄的資料夾。
1. 啟動資料工作台並載入描述 [!DNL Configuration] 檔。
1. 按一下縮 **[!UICONTROL Configure Connection to Servers]** 圖。
1. 在中， [!DNL Servers Manager]以滑鼠右鍵按一下資料工作台伺服器圖示，然後按一下 **[!UICONTROL Server Files]**。

1. 在「軟體」資料夾中，開啟該 [!DNL Report Server] 資料夾。
1. 按一下右鍵 **[!UICONTROL Temp]** 的複選 [!DNL ReportServer.exe] 標籤並選 **[!UICONTROL Save to]** 擇> *&lt;**[!UICONTROL server name]**>*。

## 卸載報告伺服器 {#section-96eb3281c45a45c0a7065deaa6845c25}

**若要解除安裝[!DNL Report Server]**

1. 註銷服 [!DNL Report Windows] 務。

   1. 開啟命令提示，並導覽至您安裝資料工作台伺服器的資料夾中的bin子目錄(InsightServer64.exe)。範例: [!DNL D:\Adobe\Report\bin]
   1. 在命令提示符下，執行以下命令以停止Microsoft Windows下的服務並將其註銷： [!DNL visualreport /unregserver]

1. 刪除報告伺服器安裝目錄。

