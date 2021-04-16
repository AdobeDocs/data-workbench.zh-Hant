---
description: 資料集結構描述介面會顯示任何轉換資料集設定檔案中定義的擴充維度（可計數、簡單、多對多、數值、非正規和時間維度），並提供這些維度間關係的檢視。
title: 資料集結構介面
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
exl-id: a8d4cf02-4ff7-4fcc-9062-425c1fe1fb28
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 3%

---

# 資料集結構介面{#dataset-schema-interface}

資料集結構描述介面會顯示任何轉換資料集設定檔案中定義的擴充維度（可計數、簡單、多對多、數值、非正規和時間維度），並提供這些維度間關係的檢視。

此外，[!DNL Dataset Schema]介面還顯示您定義的任何派生維，以及配置為隱藏的任何擴展維。

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>您可以從架構圖中搜索維。 搜尋字串所找到的維度名稱會反白顯示，而父級類別的行會變更從屬子級維度中找到的任何點擊的色彩。 當您捲動時，「可計數」維度會保持可見，以提供可檢視的階層和內容。

**要使用介面解譯維類 [!DNL Dataset Schema] 型**

下表列出了尺寸類型及其名稱在[!DNL Dataset Schema]介面中顯示的顏色。 另外，也會記下範例尺寸的父項（來自上述範例）。

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension類型 </th> 
   <th colname="col2" class="entry"> 色彩 </th> 
   <th colname="col3" class="entry"> 範例Dimension與父項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 可計數 </td> 
   <td colname="col2"> 粉紅色 </td> 
   <td colname="col3"> <p>訪客——在此結構中，訪客是根可計數維。 </p> <p>作業階段——父代為訪客 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非正規 </td> 
   <td colname="col2"> 黃色 </td> 
   <td colname="col3"> 非正規頁面——父代為頁面檢視 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 衍生 </td> 
   <td colname="col2"> 藍色 </td> 
   <td colname="col3"> 下一頁——父代是頁面檢視 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多對多 </td> 
   <td colname="col2"> 粉紅色和綠色（父項的莖線為粉紅色，而尺寸名稱為綠色）。 </td> 
   <td colname="col3"> 搜尋詞——父代為工作階段 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 數值 </td> 
   <td colname="col2"> 綠色 </td> 
   <td colname="col3"> 完全頁面持續時間——父代為頁面檢視。 在此範例中，「精確頁面持續時間」是隱藏的數值維度。 請參閱此表中的隱藏維類型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 簡單 </td> 
   <td colname="col2"> 綠色 </td> 
   <td colname="col3"> 頁面——父代是頁面檢視 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間 </td> 
   <td colname="col2"> 綠色 </td> 
   <td colname="col3"> 小時——父代為會話 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 隱藏的尺寸是適當尺寸類型顏色的較深色版本。 例如，隱藏的數值維度是較深、較淺的綠色。 </td> 
   <td colname="col3"> 完全頁面持續時間——父代為頁面檢視 </td> 
  </tr> 
 </tbody> 
</table>

有關這些維類型的詳細資訊，請參閱&#x200B;*資料集配置指南*。

**顯示維度的預設視覺化**

* 在[!DNL Dataset Schema]介面中，按一下所需的維度。 顯示預設視覺化。 例如，如果預設可視化是顯示會話和選定維的表，並按一下URI維，則Data Workbench將按會話顯示一個具有URI的表。

   >[!NOTE]
   >
   >如果您想要變更顯示的預設視覺化，請參閱[資料集結構介面](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)。

**顯示維度的特定視覺化**

* 在[!DNL Dataset Schema]介面中，以滑鼠右鍵按一下所要的維度，然後按一下&#x200B;**[!UICONTROL Add Visualization]** > ***[!UICONTROL visualization type]**>*。
