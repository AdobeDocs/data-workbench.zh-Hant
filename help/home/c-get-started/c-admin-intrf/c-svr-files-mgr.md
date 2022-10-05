---
description: 「伺服器檔案管理器」允許您通過提供對產品安裝目錄中所有目錄和檔案（包括配置和查找檔案）的訪問，從任何授權Data Workbench遠程管理和管理Data Workbench伺服器電腦。
title: 伺服器檔案管理員
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 1%

---

# 伺服器檔案管理員{#server-files-manager}

{{eol}}

「伺服器檔案管理器」允許您通過提供對產品安裝目錄中所有目錄和檔案（包括配置和查找檔案）的訪問，從任何授權Data Workbench遠程管理和管理Data Workbench伺服器電腦。

您可以存取 [!DNL Server Files Manager] 使用 [!DNL Admin] ，也可以按一下右鍵Data Workbench伺服器電腦的節點 [!DNL Servers Manager] 按一下 **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>您可以建立顯示所選目錄的新伺服器檔案管理器。 請參閱 [建立新的伺服器檔案管理器](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

的左欄 [!DNL Server Files Manager] 列出檔案和資料夾名稱。 中央和右側列中的勾號表示這些目錄和檔案在檔案結構中的位置。

如果檔案位於產品的安裝目錄中，則 *伺服器名稱* (例如，Data Workbench伺服器)欄包含勾號。 如果檔案位於Data Workbench用戶的電腦上， *Data Workbench安裝目錄*\Temp目錄， [!DNL Temp] 列包含複選標籤。 檢查標籤的顏色指示是否同時修改了駐留在不同位置的檔案。

* 伺服器名稱列中的紅色複選標籤表示資料夾或檔案駐留在Data Workbench伺服器電腦上。
* 中的紅色勾號 [!DNL Temp] 列指示檔案或資料夾的本地副本具有與Data Workbench伺服器電腦上的檔案或資料夾相同的修改日期和時間。
* 此 [!DNL Temp] 欄指示 *Data Workbench安裝目錄*\Temp目錄的修改日期和時間與Data Workbench伺服器電腦上的檔案或資料夾不同。

下圖顯示 [!DNL Server Files Manager] 帶有紅色和白色的勾號：

![](assets/vis_FileManager_RedWhiteChecks.png)

**要使用[!DNL Server Files Manager]**

您可以使用 [!DNL Server Files Manager] 操作Data Workbench伺服器電腦上的目錄和檔案。

下表列出可使用 [!DNL Server Files Manager]:

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
   <td colname="col2"> <p>按一下目錄名稱以檢視其內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>隱藏目錄的內容 </p> </td> 
   <td colname="col2"> <p>按一下目錄名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要查看有關目錄的詳細資訊 </p> </td> 
   <td colname="col2"> <p>按一下右鍵伺服器名稱或 <span class="wintitle"> 臨時</span> 欄。 您會看到下列資訊： </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">路徑. 目錄的路徑。 </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">目錄。 目錄的名稱。 </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">從. 目錄、遠程或臨時的位置。 </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">日期（僅限臨時欄）。 建立日期或本地副本的上次修訂日期。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>若要查看檔案的詳細資訊 </p> </td> 
   <td colname="col2"> <p>在伺服器名稱或 <span class="wintitle"> 臨時</span> 欄。 您會看到下列資訊： </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">路徑. 檔案的路徑。 </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">檔案. 檔案的名稱。 </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">從. 目錄、遠程或臨時的位置。 </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">日期. 檔案的最後修訂日期。 </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">大小. 檔案的大小。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將目錄下載到本地電腦 </p> </td> 
   <td colname="col2"> <p>以滑鼠右鍵按一下 <i>伺服器名稱</i> 欄，然後按一下 <span class="uicontrol"> 將目錄設為本地</span>. 目錄的複選標籤會顯示在 <span class="wintitle"> 臨時</span> 欄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將檔案下載到本地電腦 </p> </td> 
   <td colname="col2"> <p>以滑鼠右鍵按一下 <i>伺服器名稱</i> 欄，然後按一下 <span class="uicontrol"> 使本地</span>. 檔案的勾選記號會顯示在 <span class="wintitle"> 臨時</span> 欄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將日誌檔案的最後一部分下載到本地電腦 </p> </td> 
   <td colname="col2"> <p>要避免下載整個日誌檔案（尤其是當您知道錯誤消息接近檔案結尾時），請按一下右鍵該檔案的「伺服器名稱」列中的複選標籤，按一下 <span class="uicontrol"> 尾部</span>，然後選取您要下載的部分大小。 檔案的勾選記號會顯示在 <span class="wintitle"> 臨時</span> 欄。 本機檔案僅包含您指定的資料量，從檔案結尾開始。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>開啟目錄 </p> </td> 
   <td colname="col2"> <p>按一下右鍵中目錄的複選標籤 <span class="wintitle"> 臨時</span> 欄，按一下 <span class="uicontrol"> 開啟</span> &gt; <span class="uicontrol"> 資料夾</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>開啟檔案 </p> </td> 
   <td colname="col2"> <p>以滑鼠右鍵按一下 <span class="wintitle"> 臨時</span> 欄，按一下 <span class="uicontrol"> 開啟</span>，然後按一下 <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> 記事本</span>，或 <span class="uicontrol"> 資料夾</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將目錄的本地副本保存到Data Workbench伺服器 </p> </td> 
   <td colname="col2"> <p>按一下右鍵中目錄的複選標籤 <span class="wintitle"> 臨時</span> 欄，按一下 <span class="uicontrol"> 將目錄保存到</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將檔案的本機副本儲存至Data Workbench伺服器 </p> </td> 
   <td colname="col2"> <p>以滑鼠右鍵按一下 <span class="wintitle"> 臨時</span> 欄，按一下 <span class="uicontrol"> 儲存至</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刪除目錄或檔案的本地副本 </p> </td> 
   <td colname="col2"> <p>按一下右鍵中目錄或檔案的複選標籤 <span class="wintitle"> 臨時</span> 欄，按一下 <span class="uicontrol"> 移除</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在Microsoft Outlook中複製檔案並貼上為電子郵件附件 </p> </td> 
   <td colname="col2"> <p>以滑鼠右鍵按一下 <span class="wintitle"> 臨時</span> 欄，按一下 <span class="uicontrol"> 複製</span>. 在電子郵件內文中，按Ctrl+v附加檔案。 </p> </td> 
  </tr> 
 </tbody> 
</table>
