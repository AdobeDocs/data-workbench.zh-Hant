---
description: Server Files Manager可讓您從任何授權的Data Workbench，遠端管理Data Workbench伺服器電腦，方法是存取產品安裝目錄中的所有目錄和檔案，包括設定和查閱檔案。
title: 伺服器檔案管理員
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 1%

---

# 伺服器檔案管理員{#server-files-manager}

Server Files Manager可讓您從任何授權的Data Workbench，遠端管理Data Workbench伺服器電腦，方法是存取產品安裝目錄中的所有目錄和檔案，包括設定和查閱檔案。

您可以使用[!DNL Admin]菜單訪問[!DNL Server Files Manager] ，也可以按一下右鍵[!DNL Servers Manager]中Data Workbench伺服器電腦的節點，然後按一下&#x200B;**[!UICONTROL Server Files]**。

![](assets/vis_FileManager.png)

>[!NOTE]
>
>您可以建立顯示選定目錄的新伺服器檔案管理器。 請參閱[建立新伺服器檔案管理器](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816)。

[!DNL Server Files Manager]的左欄列出檔案和資料夾名稱。 中心和右列中的複選標籤表示這些目錄和檔案在檔案結構中的駐留位置。

如果檔案位於產品的安裝目錄中，*伺服器名稱*(例如，Data Workbench伺服器)欄會包含複選標籤。 如果檔案駐留在&#x200B;*Data Workbench安裝目錄*\Temp目錄的Data Workbench用戶電腦上，則[!DNL Temp]列包含複選標籤。 複選標籤的顏色指示是否同時修改了位於不同位置的檔案。

* 伺服器名稱列中的紅色複選標籤表示資料夾或檔案駐留在Data Workbench伺服器電腦上。
* [!DNL Temp]欄中的紅色複選標籤表示檔案或資料夾的本地副本與Data Workbench伺服器電腦上的檔案或資料夾具有相同的修改日期和時間。
* [!DNL Temp]列中的白色複選標籤表示&#x200B;*Data Workbench安裝目錄*\Temp目錄中的檔案或資料夾具有與Data Workbench伺服器電腦上的檔案或資料夾不同的修改日期和時間。

下圖顯示了帶有紅色和白色複選標籤的[!DNL Server Files Manager]:

![](assets/vis_FileManager_RedWhiteChecks.png)

**要使用[!DNL Server Files Manager]**

您可以使用[!DNL Server Files Manager]來操控Data Workbench伺服器電腦上的目錄和檔案。

下表列出了使用[!DNL Server Files Manager]可完成的任務：

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要執行此任務…… </th> 
   <th colname="col2" class="entry"> 執行動作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>查看任何目錄中的檔案 </p> </td> 
   <td colname="col2"> <p>按一下目錄名稱可查看其內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>隱藏目錄的內容 </p> </td> 
   <td colname="col2"> <p>按一下目錄名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看有關目錄的詳細資訊 </p> </td> 
   <td colname="col2"> <p>按一下右鍵伺服器名稱或<span class="wintitle"> Temp</span>列中目錄旁的單元格。 您會看到下列資訊： </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">路徑. 目錄的路徑。 </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">目錄。 目錄的名稱。 </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">從. 目錄的位置，遠程或臨時。 </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">日期（僅限臨時欄）。 建立日期或本地副本的最後修訂日期。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>若要查看檔案的詳細資訊 </p> </td> 
   <td colname="col2"> <p>按一下右鍵伺服器名稱或<span class="wintitle"> Temp</span>列中檔案旁的複選標籤。 您會看到下列資訊： </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">路徑. 檔案的路徑。 </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">檔案. 檔案的名稱。 </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">從. 目錄的位置，遠程或臨時。 </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">日期. 檔案上次修訂的日期。 </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">大小. 檔案的大小。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要下載目錄到本地電腦 </p> </td> 
   <td colname="col2"> <p>按一下右鍵此目錄的<i>伺服器名稱</i>列中的複選標籤，然後按一下<span class="uicontrol">將目錄本地化</span>。 目錄的複選標籤顯示在<span class="wintitle"> Temp</span>列中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>若要下載檔案至您的本機電腦 </p> </td> 
   <td colname="col2"> <p>按一下右鍵此檔案<i>伺服器名稱</i>列中的複選標籤，然後按一下<span class="uicontrol"> Make Local</span>。 檔案的複選標籤將出現在<span class="wintitle"> Temp</span>列中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要將日誌檔案的最後一部分下載到本地電腦 </p> </td> 
   <td colname="col2"> <p>為避免下載整個日誌檔案（尤其是當您知道錯誤消息接近檔案結尾時），請按一下右鍵檔案伺服器名列中的複選標籤，按一下<span class="uicontrol"> Tail</span> ，然後選擇要下載的部分的大小。 檔案的複選標籤將出現在<span class="wintitle"> Temp</span>列中。 本機檔案只包含您指定的資料量，從檔案結尾開始。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>開啟目錄 </p> </td> 
   <td colname="col2"> <p>按一下右鍵<span class="wintitle"> Temp</span>列中目錄的複選標籤，然後按一下<span class="uicontrol"> Open</span> &gt; <span class="uicontrol">資料夾</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要開啟檔案 </p> </td> 
   <td colname="col2"> <p>按一下右鍵<span class="wintitle"> Temp</span>列中檔案的複選標籤，按一下<span class="uicontrol">開啟</span>，然後按一下<span class="uicontrol">Data Workbench</span>、<span class="uicontrol">記事本</span>或<span class="uicontrol">資料夾</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將目錄的本地副本保存到Data Workbench伺服器 </p> </td> 
   <td colname="col2"> <p>按一下右鍵<span class="wintitle"> Temp</span>列中目錄的複選標籤，然後按一下<span class="uicontrol">保存目錄到</span> &gt; <i><span class="uicontrol">配置檔案名稱</span></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將檔案的本地副本保存到Data Workbench伺服器 </p> </td> 
   <td colname="col2"> <p>按一下右鍵<span class="wintitle"> Temp</span>列中檔案的複選標籤，然後按一下<span class="uicontrol">保存到</span> &gt; <i><span class="uicontrol">配置檔案名</span></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刪除目錄或檔案的本地副本 </p> </td> 
   <td colname="col2"> <p>按一下右鍵<span class="wintitle"> Temp</span>列中目錄或檔案的複選標籤，然後按一下<span class="uicontrol">刪除</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在Microsoft Outlook中複製檔案並貼上為電子郵件附件 </p> </td> 
   <td colname="col2"> <p>在<span class="wintitle"> Temp</span>欄中按一下右鍵檔案的複選標籤，然後按一下<span class="uicontrol"> Copy</span>。 在電子郵件正文中，按Ctrl+v以附加檔案。 </p> </td> 
  </tr> 
 </tbody> 
</table>
