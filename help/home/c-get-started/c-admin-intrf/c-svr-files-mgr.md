---
description: 「伺服器檔案管理員」可讓您從任何授權的資料工作台遠端管理資料工作台伺服器電腦，讓您存取產品安裝目錄中的所有目錄和檔案，包括設定和查閱檔案。
solution: Analytics
title: 伺服器檔案管理員
topic: Data workbench
uuid: 62625b9d-587f-4a78-8328-2270869909f8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 伺服器檔案管理員{#server-files-manager}

「伺服器檔案管理員」可讓您從任何授權的資料工作台遠端管理資料工作台伺服器電腦，讓您存取產品安裝目錄中的所有目錄和檔案，包括設定和查閱檔案。

您也可以使 [!DNL Server Files Manager] 用功能表 [!DNL Admin] 以及在中以滑鼠右鍵按一下資料工作台伺服器電腦的節點，然後按 [!DNL Servers Manager] 一下來存取 **[!UICONTROL Server Files]**。

![](assets/vis_FileManager.png)

>[!NOTE]
>
>您可以建立顯示選定目錄的新伺服器檔案管理器。 請參 [閱建立新伺服器檔案管理器](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816)。

列出檔案和 [!DNL Server Files Manager] 資料夾名稱的左列。 中心和右列中的複選標籤表示這些目錄和檔案在檔案結構中的駐留位置。

如果檔案位於產品的安裝目錄中，則 *伺服器名稱* （例如資料工作台伺服器）欄會包含核取標籤。 如果檔案位於「資料工作台」使用者電腦的「 *資料工作台」安裝目錄*\Temp目錄中，則 [!DNL Temp] 欄會包含核取標籤。 複選標籤的顏色指示是否同時修改了位於不同位置的檔案。

* 伺服器名稱欄中的紅色勾號表示資料夾或檔案位於資料工作台伺服器電腦上。
* 列中的紅色複選標 [!DNL Temp] 記表示檔案或資料夾的本地副本與資料工作台伺服器電腦上的檔案或資料夾具有相同的修改日期和時間。
* 列中的白色複選標 [!DNL Temp] 記表示 *Data Workbench安裝目錄*\Temp目錄中的檔案或資料夾具有與資料工作台伺服器電腦上的檔案或資料夾不同的修改日期和時間。

下圖顯示帶有 [!DNL Server Files Manager] 紅色和白色複選標籤的：

![](assets/vis_FileManager_RedWhiteChecks.png)

**要使用[!DNL Server Files Manager]**

您可以使用來 [!DNL Server Files Manager] 操控資料工作台伺服器電腦上的目錄和檔案。

下表列出了可使用完成的任務 [!DNL Server Files Manager]:

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
   <td colname="col2"> <p>按一下右鍵伺服器名稱或臨時列中目錄旁的單 <span class="wintitle"> 元格</span> 。 您會看到下列資訊： </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">路徑. 目錄的路徑。 </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">目錄。 目錄的名稱。 </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">從. 目錄的位置，遠程或臨時。 </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">日期（僅限臨時欄）。 建立日期或本地副本的最後修訂日期。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>若要查看檔案的詳細資訊 </p> </td> 
   <td colname="col2"> <p>按一下右鍵伺服器名稱或臨時列中檔案旁的複選 <span class="wintitle"> 標籤</span> 。 您會看到下列資訊： </p> <p> 
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
   <td colname="col2"> <p>按一下右鍵此目錄的伺服器名 <i>稱列中的複選標籤</i> ，然後按一下 <span class="uicontrol"> 「將目錄本地化」</span>。 目錄的複選標籤將顯示在「臨時 <span class="wintitle"> 」列中</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>若要下載檔案至您的本機電腦 </p> </td> 
   <td colname="col2"> <p>按一下右鍵此檔案的伺服器名 <i>稱列中的複選標籤</i> ，然後按一下 <span class="uicontrol"> Make Local</span>。 檔案的複選標籤會顯示在「臨 <span class="wintitle"> 時</span> 」列中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要將日誌檔案的最後一部分下載到本地電腦 </p> </td> 
   <td colname="col2"> <p>為避免下載整個日誌檔案（尤其是當您知道錯誤消息接近檔案結尾時），請按一下右鍵檔案伺服器名列中的複選標籤，按一下 <span class="uicontrol"> Tail</span>，然後選擇要下載的部分的大小。 檔案的複選標籤會顯示在「臨 <span class="wintitle"> 時</span> 」列中。 本機檔案只包含您指定的資料量，從檔案結尾開始。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>開啟目錄 </p> </td> 
   <td colname="col2"> <p>按一下右鍵「臨時」列中目錄的複選標籤 <span class="wintitle"> ，然後按一下「</span> 開啟 <span class="uicontrol"> &gt;資料夾</span> 」 <span class="uicontrol"></span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要開啟檔案 </p> </td> 
   <td colname="col2"> <p>按一下右鍵「 <span class="wintitle"> Temp</span> 」列中檔案的複選標籤，按一下「 <span class="uicontrol"> Open</span>」(開啟 <span class="uicontrol"> )，然後按一下「</span>Workbench data」(記事本、記事本或資料夾中的Notepad <span class="uicontrol"></span><span class="uicontrol"></span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將目錄的本機副本儲存至資料工作台伺服器 </p> </td> 
   <td colname="col2"> <p>按一下右鍵「臨時 <span class="wintitle"> 」列中的目錄，然後按一下「</span> Save To <span class="uicontrol"> &gt;</span> Profile name <i>&gt;<span class="uicontrol"> &lt;Check Mark」(將配置檔案名稱保存到</span>&gt;&lt;Check Name</i>&gt;)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將檔案的本機副本儲存至資料工作台伺服器 </p> </td> 
   <td colname="col2"> <p>按一下右鍵「臨時」列中檔案的複選標籤，然後按一下 <span class="wintitle"> 「保存到</span> &gt; <span class="uicontrol"> &lt;配置檔案名</span><i><span class="uicontrol"></span></i>&gt;」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刪除目錄或檔案的本地副本 </p> </td> 
   <td colname="col2"> <p>按一下右鍵「臨時」列中目錄或檔案的複選標籤，然後單 <span class="wintitle"> 擊</span> 「刪除 <span class="uicontrol"> 」</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在Microsoft Outlook中複製檔案並貼上為電子郵件附件 </p> </td> 
   <td colname="col2"> <p>按一下右鍵「臨時」列中檔案的複選標 <span class="wintitle"> 記</span> ，然後按一下 <span class="uicontrol"> 「複製」</span>。 在電子郵件正文中，按Ctrl+v以附加檔案。 </p> </td> 
  </tr> 
 </tbody> 
</table>

