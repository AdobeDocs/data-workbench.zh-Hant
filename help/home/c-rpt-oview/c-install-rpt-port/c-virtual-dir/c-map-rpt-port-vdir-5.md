---
description: 將報告門戶映射到虛擬目錄(IIS 5.0)的步驟。
title: 將 Report Portal 對應到虛擬目錄 (IIS 5.0)
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
exl-id: 20d8e9ea-c5b6-4a1b-9b15-557cc71ad5d9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# 將 Report Portal 對應到虛擬目錄 (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

將報告門戶映射到虛擬目錄(IIS 5.0)的步驟。

1. 在安裝[!DNL Report Portal]的電腦上，使用&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**&#x200B;或&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**&#x200B;啟動IIS管理器。

1. 選擇 **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 按一下右鍵&#x200B;**[!UICONTROL Default Web Site]**&#x200B;並選擇&#x200B;**[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**。

1. 開啟[!DNL Virtual Directory Wizard]時，按一下&#x200B;**[!UICONTROL Next]**。

1. 完成以下步驟以定義[!DNL Report Portal]的根虛擬目錄：

   1. 當提示輸入別名時，鍵入[!DNL Report Portal]的名稱，然後按一下&#x200B;**[!UICONTROL Next]**。 例如，如果要使用&quot;Portal&quot;作為[!DNL Report Portal]的名稱，請將別名&quot;Portal&quot;分配給虛擬目錄。 完成後，請按一下 **[!UICONTROL Next]**。

   1. 當提示輸入物理路徑時，瀏覽並選擇&#x200B;***[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]**&#x200B;目錄，然後按一下&#x200B;**[!UICONTROL Next]**。

      範例：[!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. 當系統提示您輸入權限時，請確認下列選項已啟用：

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. 按一下「**[!UICONTROL Next]**」，然後按一下「**[!UICONTROL Finish]**」。您建立的虛擬目錄將顯示在「預設網站」下，如下例所示。

   ![](assets/RptPort_scrn_VirDirManual.png)

1. 按一下右鍵剛建立的虛擬目錄，然後選擇&#x200B;**[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**。

1. 使用[!DNL Virtual Directory]嚮導為以下每個物理目錄建立別名。 這樣做會為每個物理資源建立一個名稱正確的虛擬目錄。

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 建立此別名。.. </th> 
   <th colname="col2" class="entry"> 對於此物理資源。.. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Core </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>範例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>範例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>範例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 影像 </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>範例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> <p><span class="keyword">報告伺服器</span>保存報告集輸出的目錄的物理位置。 輸出資料夾可位於任何位置、可命名任何項目，並包含每個報表集的子資料夾。 </p> <p>此目錄必須與您在<span class="filepath"> Report.cfg</span>檔案中為報表集指定的輸出根目錄相同。 如需詳細資訊，請參閱<a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d">設定Report.cfg檔案</a>。 </p> <p>預設位置為\<i>PortalName</i>\PortalFiles\Output。 </p> <p>範例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p><i>PortalName</i>\PortalFiles\Output directory contains the <span class="filepath"> profiles.xml</span>檔案，必須移至您為此別名指定的輸出目錄。 </p> <p><span class="wintitle">路徑</span>屬性必須正確設定。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 完成後，驗證IIS是否顯示6個新的虛擬目錄。 請確定目錄結構有一個父資料夾（與入口資料夾同名）和五個子資料夾，如下所示。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 完成後，轉至[編輯會話配置檔案](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)以繼續安裝過程。
