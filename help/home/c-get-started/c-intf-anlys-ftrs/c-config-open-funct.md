---
description: 開啟功能允許您在諸如文本編輯器或Web瀏覽器的外部應用程式中開啟諸如文檔或URI之類的項。
title: 設定開啟功能
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# 設定開啟功能{#configure-open-functionality}

{{eol}}

開啟功能允許您在諸如文本編輯器或Web瀏覽器的外部應用程式中開啟諸如文檔或URI之類的項。

目前僅在 [!DNL Site] 應用程式和僅用於開啟URI。 本節提供有關為 [!DNL Site]. 如需為其他應用程式或開啟其他項目設定開啟功能的相關資訊，請聯絡Adobe諮詢服務。

在 [!DNL Site]，可以從頁面覆蓋或表格按一下右鍵URI，以在格式化應用程式中顯示URI。 例如，從URI表視覺效果中，可以按一下URI以在Web瀏覽器中顯示網頁。

若要從視覺效果開啟URI，您必須先編輯 [!DNL Open URI.cfg] URI維的檔案，用於標識Data Workbench用於開啟URI的位置和命名約定。 要以本機格式查看URI(如HTML),Data Workbench必須有權訪問引用的位置以及開啟該項目所需的應用程式。 例如，若要檢視網頁，Data Workbench需要存取網際網路並安裝網頁瀏覽器。

**要編輯開啟URI.vw**

1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. 在URI資料夾中，以滑鼠右鍵按一下 [!DNL Open URI.vw]按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。
1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]** 如果檔案是 [!DNL .cfg] 檔案或 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** 如果是 [!DNL .vw] 檔案。
1. 按一下 **[!UICONTROL Command]**，然後 **[!UICONTROL Parameters]** 來查看檔案的內容。
1. 修改 [!DNL Site] 參數和範本參數（視需要）:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 對於此參數…… </th>
   <th colname="col2" class="entry"> 提供此資訊…… </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>網站 </p> </td>
   <td colname="col2"> <p>要開啟的URI的位置。 </p> <p>範例：mysite.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>範本 </p> </td>
   <td colname="col2"> <p>Data Workbench應用於查找和開啟URI的參數。 </p> <p>範例： <span class="filepath"> https://%Site%%URI%</span> </p> <p>範例中顯示的預設範本會告訴Data Workbench要開啟網頁瀏覽器，尋找中定義的位置 <span class="wintitle"> 網站</span> 參數，然後找到您嘗試開啟的URI維元素。 </p> </td>
  </tr>
 </tbody>
</table>

1. 儲存檔案。
1. 若要將此變更提供給工作設定檔的所有使用者，請以滑鼠右鍵按一下 [!DNL .vw] 檔案 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
