---
description: 將Report Portal對應到虛擬目錄(IIS 6.0)的步驟。
title: 將 Report Portal 對應到虛擬目錄 (IIS 6.0)
uuid: e09d23d7-09de-4180-8260-60527f47aa98
exl-id: 39335705-7391-49af-a63d-c0fe4ca3f8f0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 3%

---

# 將 Report Portal 對應到虛擬目錄 (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

{{eol}}

將Report Portal對應到虛擬目錄(IIS 6.0)的步驟。

對應 [!DNL Report Portal] 到IIS 6.0上的虛擬目錄涉及三個不同的任務：

1. [編輯配置檔案](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [將配置檔案導入IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [在IIS上啟用活動伺服器頁(ASP)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

您必須完成所有三項任務。

## 要編輯配置檔案 {#section-eaf1c58935074cfa840dac33e1286520}

1. 在 [!DNL Report Portal] 已安裝，請在文本編輯器（如記事本）中開啟\*PortalName*\ReportPortalSetup.xml。

1. 使用編輯器的「尋找並取代」功能，將字串&quot;VSVirtualPortalName&quot;全域取代（全部取代）為入口網站的名稱。 例如，如果您想使用&quot;VisualReportPortal&quot;作為 [!DNL Report Portal]，您會搜尋&quot;VSVirtualPortalName&quot;，並將其取代為&quot;VisualReportPortal&quot;。
1. 在此檔案中找出下列元素：

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. 設定此元素的 [!DNL Path] 屬性至其中的目錄的物理位置 [!DNL Report Server] 儲存報表集的輸出。

   輸出資料夾可位於任何位置、可命名任何項目，且包含每個報表集的子資料夾。

   >[!NOTE]
   >
   >此目錄必須與 [!DNL Report.cfg] 檔案。 如需詳細資訊，請參閱 [設定Report.cfg檔案](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d).

   下列程式碼範例顯示如何設定 [!DNL Path] 屬性 [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >關鍵是 [!DNL Path] 屬性設定正確。

1. 如果您變更預設值 [!DNL Path] 的 [!DNL Output] 元素，移動 [!DNL profiles.xml] 檔案 *\PortalName*\PortalFiles\Output資料夾到您在步驟4中指定的輸出目錄。 在上例中，您會移動 [!DNL profiles.xml] to [!DNL E:\VSReport\ReportOutput].

1. 確認 [!DNL Path] 屬性 [!DNL IIsWebVirtualDir] 元素會透過搜尋 [!DNL C:\Inetpub\wwwroot] 用正確的路徑來替換。

1. 儲存檔案。如果要保留原始檔案，可以使用新名稱保存配置檔案。

## 將配置檔案導入IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. 在 [!DNL Report Portal] ，請使用 **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. 選擇 **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 按一下右鍵 **[!UICONTROL Default Web Site]** 選取 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** （從檔案）。

1. 選取 **[!UICONTROL ReportPortalSetup.xml]** 按一下 **[!UICONTROL Read File]**.

1. 驗證是否為您的 [!DNL Report Portal] 如下列範例所示。

   ![](assets/rptPort_dia_VirDirs.png)

   如果您沒有看到六個虛擬目錄，或者如果您收到錯誤消息，請按一下 **[!UICONTROL Cancel]** 並檢查配置檔案中是否有錯誤。

1. 選擇清單中的第一個虛擬目錄（其他五個虛擬目錄的父目錄），然後按一下 **[!UICONTROL OK]**. IIS導入映射並將虛擬目錄添加到預設網站。

   請確保生成的目錄結構有一個父資料夾（名稱與門戶相同）和五個子目錄，如以下示例所示。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 按一下每個虛擬目錄，以確保IIS可以找到它所代表的物理目錄。 如果IIS顯示錯誤，請按一下右鍵虛擬目錄名並驗證 [!DNL Local Path] 欄位指向正確的物理目錄。

## 在IIS上啟用活動伺服器頁(ASP) {#section-a7725ec2afc64ffc854c5bd8c5c31802}

使用 [!DNL Report Portal]，則必須在IIS上啟用ASP。 （預設情況下，安裝IIS 6.0時會禁用ASP。） 請使用以下過程來驗證IIS上是否啟用了ASP。

1. 在「IIS管理器」窗口中，選擇 **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**.
1. 確認 [!DNL Active Server Pages] 擴充功能設為 [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. 如果禁止其狀態，請選擇 **[!UICONTROL Active Server Pages]** 按一下 **[!UICONTROL Allow]**.
1. 關閉IIS管理器。
