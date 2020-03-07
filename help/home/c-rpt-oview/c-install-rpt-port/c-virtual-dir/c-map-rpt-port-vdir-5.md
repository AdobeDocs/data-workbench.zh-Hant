---
description: 將報告門戶映射到虛擬目錄(IIS 5.0)的步驟。
solution: Analytics
title: 將報告門戶映射到虛擬目錄(IIS 5.0)
topic: Data workbench
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 將報告門戶映射到虛擬目錄(IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

將報告門戶映射到虛擬目錄(IIS 5.0)的步驟。

1. 在安裝電腦上，使用> > [!DNL Report Portal] > **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]****[!UICONTROL Internet Information Services]****[!UICONTROL Start]****[!UICONTROL Administrative Tools]****[!UICONTROL Internet Information Services]**>啟動IIS Manager。

1. 選擇 **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 按一下滑鼠右 **[!UICONTROL Default Web Site]** 鍵並選取 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**。

1. 開啟時 [!DNL Virtual Directory Wizard] ，按一下 **[!UICONTROL Next]**。

1. 完成以下步驟以定義根虛擬目錄 [!DNL Report Portal]:

   1. 當系統提示輸入別名時，鍵入別名 [!DNL Report Portal]，然後按一下 **[!UICONTROL Next]**。 例如，如果要使用&quot;Portal&quot;作為名稱，請將別名 [!DNL Report Portal]&quot;Portal&quot;分配給虛擬目錄。 完成後，請按一下 **[!UICONTROL Next]**。

   1. 當系統提示輸入物理路徑時，瀏覽並選擇&lt; *>目&#x200B;**[!UICONTROL PortalName]**錄，然後按一下***[!UICONTROL \PortalASP]****[!UICONTROL Next]**。

      範例: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. 當系統提示您輸入權限時，請確認下列選項已啟用：

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Click **[!UICONTROL Next]**, then click **[!UICONTROL Finish]**. 您建立的虛擬目錄將顯示在「預設網站」下，如下例所示。
   ![](assets/RptPort_scrn_VirDirManual.png)

1. 按一下右鍵剛建立的虛擬目錄，然後選擇 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**。

1. 使用 [!DNL Virtual Directory] 嚮導為以下每個物理目錄建立別名。 這樣做會為每個物理資源建立一個名稱正確的虛擬目錄。

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 建立此別名。.. </th> 
   <th colname="col2" class="entry"> 對於此物理資源。.. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 核心 </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>範例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>範例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>範例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 影像 </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>範例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> <p>報表伺服器儲存報表集 <span class="keyword"> 輸出之目錄的實際位置</span> 。 輸出資料夾可位於任何位置、可命名任何項目，並包含每個報表集的子資料夾。 </p> <p>這必須是您在報表集的 <span class="filepath"> Report.cfg檔案中，在「輸出根」參數中指定的相同目錄</span> 。 如需詳細資訊，請參 <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> 閱設定Report.cfg檔案</a>。 </p> <p>預設位置為\<i>PortalName</i>\PortalFiles\Output。 </p> <p>範例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>PortalName <i></i>\PortalFiles\Output directory contains the <span class="filepath"></span> profiles.xml檔案，必須移至您為此別名指定的輸出目錄。 </p> <p>Path屬性的設 <span class="wintitle"> 定至關重要</span> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 完成後，驗證IIS是否顯示6個新的虛擬目錄。 請確定目錄結構有一個父資料夾（與入口資料夾同名）和五個子資料夾，如下所示。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 完成後，請轉至 [編輯會話配置檔案](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) ，以繼續安裝過程。

