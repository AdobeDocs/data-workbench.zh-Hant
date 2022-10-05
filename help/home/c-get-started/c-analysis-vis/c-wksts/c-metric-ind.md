---
description: 您可以使用工作表來指出量度已達到定義的臨界值。
title: 建立量度指標
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
exl-id: 5713f3dd-85ef-407c-b21c-80e9b4390b6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 2%

---

# 建立量度指標{#create-a-metric-indicator}

{{eol}}

您可以使用工作表來指出量度已達到定義的臨界值。

此外，您也可以使用 [!DNL Report] 當量度在指定時間範圍內達到定義的臨界值時，自動產生和分發報表。

如需 [!DNL Report]，請參閱 *Data Workbench報表指南*.

* [上或下指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [檢查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**若要使用工作表建立量度指標**

1. 定義工作表的儲存格內容。

   1. 在欄A中，輸入所需量度的名稱(例如 [!DNL Visitors])。
   1. 在欄B中，輸入所需量度的值(例如 [!DNL =Visitors])。
   1. 在欄C中，輸入量度的低臨界值。
   1. 在欄D中，輸入量度的高臨界值。
   1. 在列E中，輸入相應的公式。 如需範例，請參閱 [上或下指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba) 或 [檢查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
   1. 在公式儲存格（欄E）中，按一下滑鼠右鍵，然後按一下 **[!UICONTROL Format]** > **[!UICONTROL Indicator]**，然後按一下下列其中一項：

      * **[!UICONTROL None]**:列出確切的計算，而非指標。
      * **[!UICONTROL Check]**:使用勾號或X來指出值高於或低於您設定的臨界值，視您的公式而定。 請參閱 [檢查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
      * **[!UICONTROL Up or Down]**:使用向上或向下箭頭指示值是否低於低閾值（向下箭頭）、高閾值（向上箭頭）或低閾值和高閾值之間（空白）。 請參閱 [上或下指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba).

1. 對您要建立指標的其他量度重複步驟1。

產生的工作表看起來會類似下列範例：

![](assets/vis_Worksheet_Alerts.png)

## 向上或向下指示器 {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

若 [!DNL Up] 或 [!DNL Down indicator]，請使用下列公式：

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

例如︰[!DNL =(b2-c2)/(d2-c2)*2-1]

將此公式與 [!DNL Up] 或 [!DNL Down indicator]:

* 如果量度值介於低臨界值和高臨界值之間，公式會評估為介於–1和1之間的數字（僅限）。 工作表中不會顯示向上或向下箭頭。
* 如果量度值小於或等於低臨界值，公式會評估小於或等於–1的值。 量度指標變更為向下箭頭。
* 如果量度值大於或等於高臨界值，公式會評估為大於或等於1的數字。 量度指標變更為上箭頭。

以下工作表說明了示例公式 [!DNL =(b2-c2)/(d2-c2)*2-1] 會顯示：

![](assets/vis_Worksheet_Alerts_UpDown.png)

## 檢查指示器 {#section-98c5298a74f34dcbaaf151549fcc7090}

若 [!DNL Check indicator]，則會使用公式，指出當量度值高於或低於您指定的臨界值時，是否要收到通知。 例如：

* 如果想在值低於您設定的臨界值時收到通知，可使用下列格式：

   * [!DNL threshold - metric]

      例如︰[!DNL =(c2-b2)]

* 如果您想在值超過您設定的臨界值時收到通知，可使用下列公式：

   * [!DNL metric - threshold]

      例如︰[!DNL =(b3-c3)]

顯示複選標籤時，公式計算為正數。 顯示X時，公式會評估為負數。

使用 [!DNL Check indicator]:

* 如果公式指示將度量值保持在閾值以上是理想的，則當度量值大於或等於閾值時顯示複選標籤，當值小於閾值時顯示X。
* 如果公式指示將度量值保持在閾值以下是可取的，則當度量值小於或等於閾值時顯示複選標籤，當值大於閾值時顯示X。

以下工作表說明了示例公式 [!DNL =(c2-b2)] 和 [!DNL =(b3-c3)] 會顯示：

![](assets/vis_Worksheet_Alerts_Check.png)
