---
description: Insight Server(InsightServer64.exe)可讓您從事件資料或查閱資料定義自訂維度。
title: 關於延伸維度
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# 關於延伸維度{#about-extended-dimensions}

{{eol}}

Insight Server(InsightServer64.exe)可讓您從事件資料或查閱資料定義自訂維度。

您定義的任何自訂維度都稱為延伸維度。 您可以使用它們來建立視覺效果、建立延伸量度或執行分析，以了解與您的業務管道相關的操作和問題。 您可以在 [!DNL Transformation.cfg] 檔案或 [!DNL Transformation Dataset Include] 檔案。

擴展維表示日誌欄位值與父維之間的關係。 父維度可以是任何使用者定義的可數維度。 請參閱 [可數Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). 在 [!DNL Transformation.cfg] 檔案或 [!DNL Transformation Dataset Include] 檔案。 維的父級與其級別相同。 例如，如果您定義父項為「工作階段」的維，則該維是工作階段層級維。

>[!NOTE]
>
>記錄欄位值可來自記錄( [!DNL .vsl])檔案或其他事件資料來源，或透過使用轉換建立的延伸記錄欄位。

若要將延伸維度新增至視覺效果，請從 [!DNL Select Dimension] 功能表。 例如，若要將延伸維度新增至圖表視覺效果，您可以在工作區內以滑鼠右鍵按一下，然後按一下 **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. 若要在Data Workbench介面中組織擴充維度的清單，您可以將擴充維度移至您建立的子資料夾。 請參閱 *Data Workbench使用手冊*. 若您這麼做，子檔案夾的名稱也會顯示在功能表中，如「新增視覺效果>圖表>延伸> &lt;」中&#x200B;*子資料夾名稱*> > &lt;*維度名稱*>。

若要查看已針對資料集設定檔定義的所有維度，以及每個維度的緩衝區大小，請開啟 [!DNL Detailed Status] 在data workbench介面中，按一下 **[!UICONTROL Performance]**，然後 **[!UICONTROL Dimensions]** 來展開節點。 控制查詢時間的緩衝區大小以MB表示。 如需 [!DNL Detailed Status] 介面，請參閱《伺服器管理和安裝指南》。
