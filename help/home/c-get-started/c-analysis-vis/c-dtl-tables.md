---
description: 詳細資料表格可讓您檢視關於資料子集的其他資訊，該子集由您在其他視覺效果中所做的選取所定義。
title: 詳細資料表格
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
exl-id: d7f0b768-f341-41e8-904b-ec98a25f7aa9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---

# 詳細資料表格{#detail-table}

詳細資料表格可讓您檢視關於資料子集的其他資訊，該子集由您在其他視覺效果中所做的選取所定義。

您看到的其他資訊是所有可用資料的取樣。

![](assets/vis_details.png)

下表描述了詳細資訊表的元素。

<table id="table_C88C7F7F5AEA4820B908923E45CC0A62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col02" class="entry"> 色彩 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>層級 </p> </td> 
   <td colname="col02"> <p>粉紅色 </p> </td> 
   <td colname="col2"> <p>您要檢視其詳細屬性和量度資訊的任何可數維度。 級別前面有可用元素數中顯示的元素數，例如6/444表示可能的444中有6個元素顯示。 在上述範例中，訪客層級表示提供的所有詳細資料都是根據訪客。 「頁面檢視」層級表示提供的所有詳細資料都是根據頁面檢視。 如果您想要分析具有不同可數父項的資料，同時檢視多個層級就很實用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>屬性 </p> </td> 
   <td colname="col02"> <p>綠色 </p> </td> 
   <td colname="col2"> <p>任何具有此層級的一對多或一對一維度，例如「城市對訪客」。 每一列都顯示與您選取之層級的每個元素相關的元素。 在上述範例中，網域和城市屬性會列出每個範例訪客的網域和城市。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>量度 </p> </td> 
   <td colname="col02"> <p>藍色 </p> </td> 
   <td colname="col2"> <p>關於您選取之層級的量度詳細資料。 在上述範例中，將層級設為「訪客」時，「頁面檢視」量度會顯示個別訪客的頁面檢視次數，而「頁面檢視」層級則提供這些頁面檢視各自的詳細資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

假設您正在處理網站資料，且想要了解訪客在特定時間範圍內造訪之特定城市和特定網域的哪些頁面。

首先，您需要建立一個視覺效果以顯示您感興趣的時間範圍，然後您需要選取該時間範圍。 現在您可以新增詳細資料表格，以檢視資料集中訪客樣本數目的所需詳細資料。

若要檢視上述詳細資訊，您必須完成下列步驟：

1. 按一下右鍵詳細資訊表中的，然後按一下&#x200B;**[!UICONTROL Add Level]** > **[!UICONTROL Visitor]**。
1. 按一下右鍵詳細資訊表中的，然後按一下&#x200B;**[!UICONTROL Add Level]** > **[!UICONTROL Page View]**。
1. 按一下右鍵&#x200B;**[!UICONTROL Visitors]**&#x200B;級標題，然後按一下&#x200B;**[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL Domain]**。
1. 在「訪客」層級標題內按一下滑鼠右鍵，然後按一下「**[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL City]**」。
1. 在「訪客」層級標題內按一下滑鼠右鍵，然後按一下「**[!UICONTROL Add Metric]** > **[!UICONTROL Page Views]**」。
1. 在「頁面檢視」層級標題內按一下滑鼠右鍵，然後按一下「**[!UICONTROL Add Attribute]** > **[!UICONTROL Page]** > **[!UICONTROL Page]**」。

下列範例工作區顯示您指定時間範圍內網站六名訪客的隨機抽樣的相關詳細資料。

![](assets/client-tab1.png)

## 添加級別{#section-f948d3361fd84906ac4d9ebce520bfd0}

* 在詳細資料表中按一下右鍵，然後按一下&#x200B;**[!UICONTROL Add Level]** > *&lt;**[!UICONTROL dimension name]**>*。

![](assets/mnu_DetailsTable_AddLevel.png)

## 刪除{#section-a8c820e0b656451e98e5ea75373edefc}級別

* 按一下右鍵現有級別標題，然後按一下&#x200B;**[!UICONTROL Remove Level]** > *&lt;**[!UICONTROL dimension name]**>*。

![](assets/mnu_DetailsTable_Level.png)

## 新增屬性和量度{#section-cdda2df3c9a448d5b9770686c8b8efb3}

* 按一下右鍵屬性或度量標題，然後按一下&#x200B;**[!UICONTROL Add Attribute]** > ***[!UICONTROL attribute name]***&#x200B;或&#x200B;**[!UICONTROL Add Metric]** > ***[!UICONTROL metric name]**>*。

![](assets/mnu_DetailsTable.png)

## 移除屬性和量度{#section-4002ac957a2846678f9940270987d651}

* 按一下右鍵要刪除的列，然後按一下&#x200B;**[!UICONTROL Remove Attribute]** > *&lt;**[!UICONTROL attribute name]**>*&#x200B;或&#x200B;**[!UICONTROL Remove Metric]** > ***[!UICONTROL metric name]**>*。

![](assets/mnu_DetailsTable.png)

## 匯出至 Microsoft Excel {#section-a9eaba63c88a4598836a34669ba8cac1}

有關導出窗口的資訊，請參閱[導出窗口資料](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)。
