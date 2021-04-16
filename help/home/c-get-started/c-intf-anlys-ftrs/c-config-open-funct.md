---
description: 開啟功能可讓您在例如文字編輯器或網頁瀏覽器等外部應用程式中開啟檔案或URI等項目。
title: 設定開啟功能
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# 設定開啟功能{#configure-open-functionality}

開啟功能可讓您在例如文字編輯器或網頁瀏覽器等外部應用程式中開啟檔案或URI等項目。

開啟功能當前僅在[!DNL Site]應用程式中配置，並且僅用於開啟URI。 本節提供有關為[!DNL Site]配置開啟URI功能的資訊。 如需為其他應用程式設定開啟功能或開啟其他項目的詳細資訊，請連絡Adobe諮詢服務。

在[!DNL Site]中，您可以按一下右鍵頁面覆蓋或表格中的URI，在為其格式化的應用程式中顯示URI。 例如，從URI表格視覺化，您可以按一下URI，在網頁瀏覽器中顯示網頁。

要從可視化中開啟URI，首先必須編輯URI維的[!DNL Open URI.cfg]檔案，以標識Data Workbench用於開啟URI的位置和命名約定。 要以其原生格式（如HTML）查看URI,Data Workbench必須有權訪問引用位置和開啟該項目所需的應用程式。 例如，若要檢視網頁，Data Workbench需要存取網際網路，並安裝網頁瀏覽器。

**要編輯開啟的URI.vw**

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**。
1. 在URI資料夾中，按一下右鍵[!DNL Open URI.vw]檔案旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。
1. 按一下右鍵新建的複選標籤，如果檔案是[!DNL .cfg]檔案，則按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**；如果檔案是[!DNL .vw]檔案，則按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。
1. 按一下&#x200B;**[!UICONTROL Command]** ，然後按一下&#x200B;**[!UICONTROL Parameters]**&#x200B;查看檔案內容。
1. 視需要修改[!DNL Site]參數和Template參數：

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
   <td colname="col2"> <p>Data Workbench應用於定位和開啟URI的參數。 </p> <p>範例：<span class="filepath"> http://%Site%%URI%</span> </p> <p>範例中顯示的預設範本會告訴Data Workbench開啟Web瀏覽器、尋找<span class="wintitle"> Site</span>參數中定義的位置，然後找出您嘗試開啟的URI維度元素。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 儲存檔案。
1. 要使此更改對工作配置檔案的所有用戶可用，請按一下右鍵[!DNL User]列中[!DNL .vw]檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL working profile name]**。
