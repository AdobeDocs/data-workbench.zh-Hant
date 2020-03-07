---
description: 開啟功能可讓您在例如文字編輯器或網頁瀏覽器等外部應用程式中開啟檔案或URI等項目。
solution: Analytics
title: 設定開啟功能
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定開啟功能{#configure-open-functionality}

開啟功能可讓您在例如文字編輯器或網頁瀏覽器等外部應用程式中開啟檔案或URI等項目。

目前僅在應用程式中設定開 [!DNL Site] 啟功能，且僅用於開啟URI。 本節提供有關為配置開啟的URI功能的信 [!DNL Site]息。 如需為其他應用程式設定開啟功能或開啟其他項目的詳細資訊，請聯絡Adobe諮詢服務。

在中， [!DNL Site]您可以按一下右鍵頁面覆蓋或表格中的URI，以在為其格式化的應用程式中顯示URI。 例如，從URI表格視覺化，您可以按一下URI，在網頁瀏覽器中顯示網頁。

若要從視覺化開啟URI，您必須先編輯URI維度的檔 [!DNL Open URI.cfg] 案，以識別資料工作台用來開啟URI的位置和命名慣例。 若要以原生格式（如HTML）檢視URI，資料工作台必須擁有參考位置的存取權以及開啟該項目所需的應用程式。 例如，若要檢視網頁，資料工作台需要存取網際網路，並安裝網頁瀏覽器。

**要編輯開啟的URI.vw**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. 在URI資料夾中，按一下右鍵檔案旁的複選標 [!DNL Open URI.vw]記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。
1. 按一下右鍵新建立的複選標籤，然後 **[!UICONTROL Open]** 按一下> **[!UICONTROL in Insight]** if the file is a file [!DNL .cfg] or **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**[!DNL .vw] if it is a file（如果檔案是檔案）。
1. 按一 **[!UICONTROL Command]**&#x200B;下， **[!UICONTROL Parameters]** 然後檢視檔案的內容。
1. 視需要修 [!DNL Site] 改參數和Template參數：

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
   <td colname="col2"> <p>資料工作台用來尋找和開啟URI的參數。 </p> <p>範例： <span class="filepath"> http://%Site%%URI%</span> </p> <p>範例中顯示的預設範本會告訴「資料工作台」開啟網頁瀏覽器、尋找在「網站 <span class="wintitle"></span> 」參數中定義的位置，然後找出您嘗試開啟的URI維度元素。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 儲存檔案。
1. 要使此更改可供工作配置檔案的所有用戶使用，請按一下右鍵列中文 [!DNL .vw] 件的複選標 [!DNL User] 記並按一下 **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**。

