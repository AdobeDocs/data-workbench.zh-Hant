---
description: 「資料集結構」介面會顯示任何「轉換資料集設定」檔案中定義的延伸維度（可數、簡單、多對多、數值、非正規和時間維度），以及這些維度之間的關係。
title: 資料集結構
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
exl-id: b80e6e8e-9147-46ec-8602-2d7e5d33f077
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 3%

---

# 資料集結構{#dataset-schema}

「資料集結構」介面會顯示任何「轉換資料集設定」檔案中定義的延伸維度（可數、簡單、多對多、數值、非正規和時間維度），以及這些維度之間的關係。

此外，[!DNL Dataset Schema]介面還顯示您已定義的任何派生維，以及配置為隱藏的任何擴展維。

![](assets/vis_DatasetSchema_Example.png)

本節將討論以下主題：

* [若要使用資料集結構介面解譯維度類型](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [顯示維度的預設視覺效果](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [顯示維度的特定視覺效果](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## 使用資料集結構介面{#section-16a0a12b11334c07bec558c0b7d260b1}解譯Dimension類型

下表列出了維類型及其名稱在[!DNL Dataset Schema]介面中顯示的顏色。 也會說明範例維度的父項（來自上述範例）。

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
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
   <td colname="col3"> <p>訪客 — 在此結構中，訪客是根可數維度。 </p> <p> 工作階段 — 父代為訪客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非正規 </td> 
   <td colname="col2"> 黃色 </td> 
   <td colname="col3"> 非正規頁面 — 上層是頁面檢視。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 衍生 </td> 
   <td colname="col2"> 藍色 </td> 
   <td colname="col3"> 下一頁 — 上層是頁面檢視。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多對多 </td> 
   <td colname="col2"> 粉紅色和綠色（父項的莖為粉色，而維度名稱為綠色）。 </td> 
   <td colname="col3"> 搜尋詞 — 父項為工作階段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 數值 </td> 
   <td colname="col2"> 綠色 </td> 
   <td colname="col3"> 確切頁面持續時間 — 上層是頁面檢視在此範例中，確切頁面持續時間是隱藏的數值維度。 請參閱此表中的「隱藏」維類型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 簡單 </td> 
   <td colname="col2"> 綠色 </td> 
   <td colname="col3"> 頁面 — 上層是頁面檢視。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間 </td> 
   <td colname="col2"> 綠色 </td> 
   <td colname="col3"> 小時 — 父代為會話。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 隱藏的維是適當的維類型顏色的較深版本。 例如，隱藏的數值維度是較深、較淺的綠色。 </td> 
   <td colname="col3"> 確切的頁面持續時間 — 上層是頁面檢視。 </td> 
  </tr> 
 </tbody> 
</table>

## 顯示Dimension{#section-1bbb73a5cbb34ffb844eb1932db85318}的預設視覺效果

* 在[!DNL Dataset Schema]介面中，按一下所需的維度。 預設視覺效果隨即顯示。 例如，如果預設視覺效果是顯示「工作階段」和所選維度的表格，然後按一下URI維度，Data Workbench會依「工作階段」顯示一個具有URI的表格。

>[!NOTE]
>
>如果您想要變更顯示的預設視覺效果，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的設定介面和分析功能一章。

## 顯示Dimension{#section-d46626df90bc4c44ae60c4b71eaeac7f}的特定視覺效果

* 在[!DNL Dataset Schema]介面中，以滑鼠右鍵按一下所需的維度，然後按一下&#x200B;**[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*。
