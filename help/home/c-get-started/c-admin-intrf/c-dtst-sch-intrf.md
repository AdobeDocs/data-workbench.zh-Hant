---
description: 「資料集結構」介面會顯示任何轉換資料集組態檔中所定義的延伸維度（可數、簡單、多對多、數值、非正規和時間維度），並提供這些維度間關係的檢視。
title: 資料集結構介面
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
exl-id: a8d4cf02-4ff7-4fcc-9062-425c1fe1fb28
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 3%

---

# 資料集結構介面{#dataset-schema-interface}

{{eol}}

「資料集結構」介面會顯示任何轉換資料集組態檔中所定義的延伸維度（可數、簡單、多對多、數值、非正規和時間維度），並提供這些維度間關係的檢視。

此外， [!DNL Dataset Schema] 介面顯示您已定義的任何衍生維度，以及任何已設定為隱藏的延伸維度。

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>您可以從架構圖中搜尋維度。 搜尋字串找到的維度名稱會反白顯示，而父類的行會變更子維度中找到的任何點擊的顏色。 當您捲動以提供可檢視的階層和內容時，可數維度會保持可見。

**要使用 [!DNL Dataset Schema] 介面**

下表列出維度類型和其名稱出現在 [!DNL Dataset Schema] 介面。 也會說明範例維度的父項（來自上述範例）。

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension類型 </th> 
   <th colname="col2" class="entry"> 色彩 </th> 
   <th colname="col3" class="entry"> 範例Dimension和父項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 可數 </td> 
   <td colname="col2"> 粉紅色 </td> 
   <td colname="col3"> <p>訪客 — 在此結構中，訪客是根可數維度。 </p> <p>工作階段 — 父代為訪客 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非正規 </td> 
   <td colname="col2"> 黃色 </td> 
   <td colname="col3"> 非正規頁面 — 上層是頁面檢視 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 衍生 </td> 
   <td colname="col2"> 藍色 </td> 
   <td colname="col3"> 下一頁 — 上層是頁面檢視 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多對多 </td> 
   <td colname="col2"> 粉紅色和綠色（父項的莖為粉色，而維度名稱為綠色）。 </td> 
   <td colname="col3"> 搜尋詞 — 父項為工作階段 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 數值 </td> 
   <td colname="col2"> 綠色 </td> 
   <td colname="col3"> 確切的頁面持續時間 — 上層是頁面檢視。 在此範例中，「確切頁面持續時間」是隱藏的數值維度。 請參閱此表中的「隱藏」維類型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 簡單 </td> 
   <td colname="col2"> 綠色 </td> 
   <td colname="col3"> 頁面 — 上層是頁面檢視 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間 </td> 
   <td colname="col2"> 綠色 </td> 
   <td colname="col3"> 小時 — 父代為會話 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 隱藏的維是適當的維類型顏色的較深版本。 例如，隱藏的數值維度是較深、較淺的綠色。 </td> 
   <td colname="col3"> 確切的頁面持續時間 — 上層是頁面檢視 </td> 
  </tr> 
 </tbody> 
</table>

如需這些維度類型的詳細資訊，請參閱 *資料集組態指南*.

**顯示維度的預設視覺效果**

* 在 [!DNL Dataset Schema] 介面，按一下所需的維度。 預設視覺效果隨即顯示。 例如，如果預設視覺效果為顯示「會話」和選定維的表，並按一下URI維，則Data Workbench將按「會話」顯示一個具有URI的表。

   >[!NOTE]
   >
   >如果您想要變更顯示的預設視覺效果，請參閱 [資料集結構介面](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**顯示維度的特定視覺效果**

* 在 [!DNL Dataset Schema] 介面，以滑鼠右鍵按一下所需的維度，然後按一下 **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
