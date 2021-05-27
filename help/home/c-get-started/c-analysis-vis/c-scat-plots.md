---
description: 散布圖在格線上繪製資料維度（例如頁面或城市）的元素，其中x軸和y軸代表不同的量度。
title: 2D 散佈圖
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
exl-id: 340f8c18-ce47-4f3a-aba4-3d6124505313
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# 2D 散佈圖{#d-scatter-plots}

散布圖在格線上繪製資料維度（例如頁面或城市）的元素，其中x軸和y軸代表不同的量度。

散布圖在嘗試以兩個不同的量度來了解大量不同項目之間的關係時非常有用。 在下列範例中，散布圖以訪客數和各自的保留率顯示每個城市。

![](assets/vis_ScatterPlot_City.png)

散布圖可讓您快速查看離群值。 例如，鹽湖城的每位訪客的保留率均高於平均。

散布圖也可用來顯示資料的一致性。 在下列範例中，散布圖顯示具有特定長度工作階段的訪客數量。

![](assets/vis_ScatterPlot_SessionDuration.png)

散布圖上每個點的大小由半徑量度決定。 每個Adobe應用程式的預設半徑量度不同。 例如，在[!DNL Site]中，半徑量度預設為以「工作階段」為基礎。 您可以變更半徑量度，讓散布圖中的點代表任何可用量度。 如需執行此操作的步驟，請參閱[變更半徑量度](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a)點的顏色是根據工作區中開啟的顏色圖例。 有關顏色圖例的詳細資訊，請參閱[顏色圖例](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)。

## 選擇點{#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**要選擇單點**

* 按一下該點。

**要向您的選擇添加其他點或點組**

* 按住Ctrl鍵並按一下某個點，或按住Ctrl鍵並拖曳至多個點。

**從選取項中刪除點或點組**

* 按住Shift鍵並按一下某個點，或按住Shift鍵並拖動幾個點。

## 更改維{#section-796cd962ef3f476caa89d99083782ed1}

* 以滑鼠右鍵按一下圖表頂端的維度標籤，然後按一下&#x200B;**[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*。

## 變更量度{#section-44b8be9215cd4039b1eeb98ae1b31445}

**變更散布圖x或y軸上顯示的量度**

* 以滑鼠右鍵按一下您要變更之量度的標籤，然後按一下&#x200B;**[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*。

## 更改半徑度量{#section-fd80576d583c430cb469daf12e39aa2a}

**變更散布圖的半徑量度**

以滑鼠右鍵按一下圖表頂端的維度標籤，然後按一下&#x200B;**[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*。

![](assets/mnu_ScatterPlot_Change.png)
