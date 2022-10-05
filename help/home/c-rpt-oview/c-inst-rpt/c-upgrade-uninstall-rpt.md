---
description: 升級和解除安裝報表伺服器軟體的相關資訊。
title: 升級和解除安裝報表伺服器
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 2%

---

# 升級和解除安裝報表伺服器{#upgrading-and-uninstalling-report-server}

{{eol}}

升級和解除安裝報表伺服器軟體的相關資訊。

* [升級報告](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [解除安裝報表](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## 升級報表伺服器 {#section-95fea4bddad74616a8aea450dcdb2282}

如果您要升級至 [!DNL Report Server] 5.4，您可以使用指示來升級您的 [!DNL Report Server] 軟體。 如果您使用 [!DNL Report Server] 3.6或更舊版本，請聯絡Adobe以取得升級協助。

升級 [!DNL Report Server] 5.4，使用data workbench將升級檔案複製至其所在的data workbench伺服器 [!DNL Report Server] 連線。 做完之後， [!DNL Report] 伺服器執行個體在連線至該伺服器並載入設定檔時會自動升級。

>[!NOTE]
>
>升級前 [!DNL Report Server]，請確定您已正確升級data workbench伺服器軟體以及data workbench伺服器上執行的設定檔。 如需詳細資訊，請連絡Adobe諮詢服務。

要執行以下過程，首先必須獲取 [!DNL Report Server].

**升級至 [!DNL Report Server] 5.4及更新版本**

1. 備份下的所有檔案 [!DNL E:\Portal] 並刪除此目錄中的所有檔案和資料夾。
1. 將新組建的內容複製至 [!DNL E:\Portal].
1. 修改 [!DNL global.asa], [!DNL email.asp]，和 [!DNL TopNavigation.xml] 如前一節所述。

1. 複製 [!DNL users.mdb] 從你的後備。

   >[!NOTE]
   >
   >如果您先前未產生.png輸出的報表，則需前往個別報表資料夾並修改 [!DNL reports.xml] 納入png的報表格式。 否則，您可能會收到500錯誤。 您的原始 [!DNL reports.xml] 會如下所示：

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

   需要修改為：

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

1. 在 [!DNL report.cfg]，包含png和save的輸出格式。 日後應會產生png格式的報表。

**升級至 [!DNL Report Server] 4.0**

1. 在Data Workbench電腦上，將報表伺服器升級檔案複製到 [!DNL Temp\Software] 資料夾（位於安裝data workbench的目錄中）。
1. 啟動Data Workbench並載入 [!DNL Configuration] 設定檔。
1. 按一下 **[!UICONTROL Configure Connection to Servers]** 縮圖。
1. 在 [!DNL Servers Manager]，請以滑鼠右鍵按一下data workbench伺服器圖示，然後按一下 **[!UICONTROL Server Files]**.

1. 在「軟體」資料夾中，開啟 [!DNL Report Server] 檔案夾。
1. 以滑鼠右鍵按一下 **[!UICONTROL Temp]** 選中標籤 [!DNL ReportServer.exe] 選取 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 解除安裝報表伺服器 {#section-96eb3281c45a45c0a7065deaa6845c25}

**卸載[!DNL Report Server]**

1. 註銷 [!DNL Report Windows] 服務。

   1. 開啟命令提示字元，並導覽至您安裝Data Workbench伺服器(InsightServer64.exe)之資料夾中的bin子目錄。 範例：[!DNL D:\Adobe\Report\bin]
   1. 在命令提示符下，執行以下命令以停止並註銷Microsoft Windows下的服務： [!DNL visualreport /unregserver]

1. 刪除Report Server安裝目錄。
