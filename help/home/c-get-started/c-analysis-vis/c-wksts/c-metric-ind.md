---
description: 您可以使用工作表來指出量度已達到定義的臨界值。
solution: Analytics
title: 建立量度指標
topic: Data workbench
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 建立量度指標{#create-a-metric-indicator}

您可以使用工作表來指出量度已達到定義的臨界值。

此外，當量度在指定時 [!DNL Report] 間範圍內達到定義的臨界值時，您可以使用自動產生和分發報表。

如需詳細資訊，請 [!DNL Report]參閱「資 *料工作台報表指南」*。

* [向上或向下指示燈](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [檢查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**若要使用工作表建立量度指標**

1. 定義工作表的儲存格內容。

   1. 在欄A中，輸入所要量度的名稱(例如 [!DNL Visitors])。
   1. 在欄B中，輸入所需量度的值(例如 [!DNL =Visitors])。
   1. 在欄C中，輸入量度的低臨界值。
   1. 在欄D中，輸入量度的高臨界值。
   1. 在列E中，輸入適當的公式。 如需範例，請參 [閱向上或向下指示](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)[燈或檢查指示燈](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)。
   1. 在公式儲存格（欄E）中，按一下滑鼠右鍵並按一下 **[!UICONTROL Format]** > **[!UICONTROL Indicator]**，然後按一下下列其中一項：

      * **[!UICONTROL None]**:列出精確計算，而非指示符。
      * **[!UICONTROL Check]**:使用複選標籤或X來指出值高於或低於您設定的臨界值，視您的公式而定。 請參閱 [檢查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)。
      * **[!UICONTROL Up or Down]**:使用向上或向下箭頭指示值是否低於低閾值（向下箭頭）、高閾值（向上箭頭）或低閾值和高閾值（空白）。 請參 [閱向上或向下指示燈](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)。

1. 對您要建立指標的其他量度重複步驟1。

產生的工作表看起來類似下列範例：

![](assets/vis_Worksheet_Alerts.png)

## 向上或向下指示燈 {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

對於或 [!DNL Up] ，請 [!DNL Down indicator]使用下列公式：

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

例如︰[!DNL =(b2-c2)/(d2-c2)*2-1]

搭配使用此公式與或時，每個量度可能會有三 [!DNL Up] 種結果 [!DNL Down indicator]:

* 如果量度值介於低臨界值和高臨界值之間，公式會評估為-1和1（獨家）之間的數字。 向上或向下箭頭不會顯示在工作表中。
* 如果量度值小於或等於低臨界值，公式會評估為小於或等於-1的值。 量度指標會變更為向下箭頭。
* 如果量度值大於或等於高臨界值，公式會評估為大於或等於1的數值。 量度指標會變更為向上箭頭。

以下工作表說明了示例公式 [!DNL =(b2-c2)/(d2-c2)*2-1] 的顯示方式：

![](assets/vis_Worksheet_Alerts_UpDown.png)

## 檢查指示器 {#section-98c5298a74f34dcbaaf151549fcc7090}

對於 [!DNL Check indicator]，您會使用公式來指出當量度值高於或低於您指定的臨界值時，您是否要收到通知。 例如：

* 如果您想在值低於您設定的臨界值時收到通知，可使用下列格式：

   * [!DNL threshold - metric]

      例如︰[!DNL =(c2-b2)]

* 如果您想在值高於您設定的臨界值時收到通知，可使用下列公式：

   * [!DNL metric - threshold]

      例如︰[!DNL =(b3-c3)]

顯示複選標籤時，公式會評估為正數。 顯示X時，公式會評估為負數。

使用下列項目時，每個量度可能會有兩種結果 [!DNL Check indicator]:

* 如果公式指出將量度值維持在臨界值以上是必要的，當量度值大於或等於臨界值時會顯示核取標籤，當值小於臨界值時會顯示X。
* 如果公式指出將量度值保持在臨界值之下是必要的，當量度值小於或等於臨界值時，會顯示核取標籤，當值大於臨界值時，會顯示X。

以下工作表說明了示例公式 [!DNL =(c2-b2)] 和 [!DNL =(b3-c3)] 顯示內容：

![](assets/vis_Worksheet_Alerts_Check.png)

