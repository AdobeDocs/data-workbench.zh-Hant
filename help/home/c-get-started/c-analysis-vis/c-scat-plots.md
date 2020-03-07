---
description: 散布圖會以圖形方式顯示資料維度的元素（例如「頁面」或「城市」），而X軸和Y軸代表不同的度量。
solution: Analytics
title: 2D散布圖
topic: Data workbench
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 2D散布圖{#d-scatter-plots}

散布圖會以圖形方式顯示資料維度的元素（例如「頁面」或「城市」），而X軸和Y軸代表不同的度量。

散布圖在嘗試透過兩個不同的度量瞭解大量不同項目之間的關係時很有用。 在下列範例中，散布圖會依訪客數量和各自的保留率來顯示每個城市。

![](assets/vis_ScatterPlot_City.png)

散布圖可讓您快速查看離群點。 例如，鹽湖城的每位訪客的平均留住率高於。

散布圖也可用來顯示資料的一致性。 在下列範例中，散布圖顯示具有特定長度作業的訪客數。

![](assets/vis_ScatterPlot_SessionDuration.png)

散布圖上每個點的大小由半徑度量決定。 每個Adobe應用程式的預設半徑量度都不同。 例如，在中， [!DNL Site]半徑度量預設是以「工作階段」為基礎。 您可以變更半徑量度，讓散布圖中的點代表任何可用量度。 如需執行此動作的步驟，請參 [閱變更半徑量度](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) 。點的色彩是以在工作區中開啟的色彩圖例為基礎。 有關顏色圖例的詳細資訊，請參 [閱顏色圖例](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)。

## 選取點 {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**若要選取單一點**

* 按一下該點。

**要將另一個點或點組添加到選區**

* 按住Ctrl鍵並按一下某個點，或按住Ctrl鍵並拖曳多個點。

**從選取範圍移除點或點組**

* 按住Shift鍵並按一下某個點，或按住Shift鍵並拖曳數個點。

## 變更維度 {#section-796cd962ef3f476caa89d99083782ed1}

* 按一下右鍵圖形頂部的尺寸標籤，然後按一下 **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*。

## 變更量度 {#section-44b8be9215cd4039b1eeb98ae1b31445}

**若要變更散布圖x或y軸上顯示的量度**

* 以滑鼠右鍵按一下您要變更之量度的標籤，然後按一下 **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*。

## 變更半徑量度 {#section-fd80576d583c430cb469daf12e39aa2a}

**若要變更散布圖的半徑量度**

按一下右鍵圖形頂部的尺寸標籤，然後按一下 **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*。

![](assets/mnu_ScatterPlot_Change.png)

