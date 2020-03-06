---
description: 將報表入口網站映射至虛擬目錄(IIS 6.0)的步驟。
solution: Analytics
title: 將報告門戶映射到虛擬目錄(IIS 6.0)
topic: Data workbench
uuid: e09d23d7-09de-4180-8260-60527f47aa98
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 將報告門戶映射到虛擬目錄(IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

將報表入口網站映射至虛擬目錄(IIS 6.0)的步驟。

將映射 [!DNL Report Portal] 到IIS 6.0上的虛擬目錄涉及三個不同的任務：

1. [編輯配置檔案](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [將配置檔案導入IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [在IIS上啟用Active Server Pages(ASP)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

您必須完成這三項任務。

## To Edit the Configuration File {#section-eaf1c58935074cfa840dac33e1286520}

1. 在安裝的 [!DNL Report Portal] 機器上，在記事本等文字編輯器中開啟\*PortalName*\ReportPortalSetup.xml。

1. 使用編輯器的尋找與取代功能，將字串&quot;VSVirtualPortalName&quot;全域取代（全部取代）為入口網站的名稱。 例如，如果您想使用&quot;VisualReportPortal&quot;做為名稱 [!DNL Report Portal]，則會搜尋&quot;VSVirtualPortalName&quot;，並將它取代為&quot;VisualReportPortal&quot;。
1. 在此檔案中找到下列元素：

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. 將此元素的屬 [!DNL Path] 性設為儲存報表集輸出之目 [!DNL Report Server] 錄的實體位置。

   輸出資料夾可位於任何位置、可命名任何項目，並包含每個報表集的子資料夾。

   >[!NOTE]
   >
   >此目錄必須與您在報表集檔案的「輸出根」參數中 [!DNL Report.cfg] 指定的目錄相同。 如需詳細資訊，請 [參閱設定Report.cfg檔案](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d)。

   下列程式碼範例顯示如何在將報 [!DNL Path] 表儲存為時設定屬性 [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >必須正確設 [!DNL Path] 定屬性。

1. 如果您變更了元素 [!DNL Path] 的預設 [!DNL Output] 值，請從 [!DNL profiles.xml] \PortalName *\PortalFiles\Output folder to the output directory that you specified in Step 4*&#x200B;移動檔案。 在上述範例中，您會移至 [!DNL profiles.xml] 中 [!DNL E:\VSReport\ReportOutput]。

1. 通過搜索所 [!DNL Path] 有其他元素的實例並用 [!DNL IIsWebVirtualDir] 正確的路徑替換每個實例，驗證所有其 [!DNL C:\Inetpub\wwwroot] 他元素的屬性都映射到正確的位置。

1. 儲存檔案。如果要保留原始檔案，可以使用新名稱保存配置檔案。

## 將配置檔案導入IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. 在安裝的計 [!DNL Report Portal] 算機上，使用 **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** >啟動IIS Manager **[!UICONTROL Internet Information Systems (IIS) Manager]**。

1. 選擇 **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 按一下右鍵 **[!UICONTROL Default Web Site]** 並選擇 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** （從檔案）。

1. 選擇文 **[!UICONTROL ReportPortalSetup.xml]** 件並按一下 **[!UICONTROL Read File]**。

1. 驗證是否列出了6個虛擬目錄，如 [!DNL Report Portal] 下例所示。

   ![](assets/rptPort_dia_VirDirs.png)

   如果您未看到6個虛擬目錄，或者收到錯誤消息，請按一下並檢 **[!UICONTROL Cancel]** 查配置檔案中是否有錯誤。

1. 選擇清單中的第一個虛擬目錄（其他五個虛擬目錄的父目錄）並按一下 **[!UICONTROL OK]**。 IIS將導入映射並將虛擬目錄添加到預設網站。

   請確定生成的目錄結構有一個父資料夾（與入口相同名稱）和五個子目錄，如下例所示。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 按一下每個虛擬目錄，確保IIS可以找到它所代表的物理目錄。 如果IIS顯示錯誤，請按一下右鍵虛擬目錄名稱並驗證該 [!DNL Local Path] 欄位指向正確的物理目錄。

## 在IIS上啟用活動伺服器頁(ASP) {#section-a7725ec2afc64ffc854c5bd8c5c31802}

若要使 [!DNL Report Portal]用，IIS上必須啟用ASP。 （預設情況下，安裝IIS 6.0時禁用ASP。）請按下列步驟驗證IIS上是否啟用了ASP。

1. 在「IIS管理器」窗口中，選擇 **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**。
1. 驗證擴 [!DNL Active Server Pages] 展名是否設定為 [!DNL Allowed]。

   ![](assets/report_aspenable.png)

1. 如果其狀態為「禁止」，請選 **[!UICONTROL Active Server Pages]** 取並按一下 **[!UICONTROL Allow]**。
1. 關閉IIS管理器。

