---
description: Insight Server(InsightServer64.exe)可讓您根據事件資料或查閱資料定義自訂維度。
solution: Analytics
title: 關於擴展尺寸
topic: Data workbench
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 關於擴展尺寸{#about-extended-dimensions}

Insight Server(InsightServer64.exe)可讓您根據事件資料或查閱資料定義自訂維度。

您定義的任何自訂維度都稱為延伸維度。 您可以使用它們來建立視覺化、建立擴充量度或執行分析，以瞭解與您的業務通道相關的運作和問題。 可在檔案或檔案中定義幾種 [!DNL Transformation.cfg] 擴展尺 [!DNL Transformation Dataset Include] 寸。

擴展維表示日誌欄位值與父維之間的關係。 父維度可以是任何使用者定義的可計數維度。 請參 [閱可計數維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)。 在檔案或檔案中定義尺寸時，可 [!DNL Transformation.cfg] 以指定父 [!DNL Transformation Dataset Include] 項。 維的父級與其級別相同。 例如，如果定義具有父代「會話」的維，則該維是會話級維。

>[!NOTE]
>
>日誌欄位值可以來自日誌( [!DNL .vsl])檔案或其他事件資料源中的固有值，也可以來自通過使用轉換建立的擴展日誌欄位。

若要將擴充維度新增至視覺化，請從功能表的「擴充」清單存取 [!DNL Select Dimension] 它。 例如，若要將延伸維度新增至圖形視覺化，您可在工作區中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*。 如果您想要在資料工作台介面中組織擴充維度的清單，可以將擴充維度移至您建立的子檔案夾。 請參閱「資料工作台使用指南」 *的「管理介面」一章*。 如果您這麼做，子檔案夾的名稱也會出現在功能表中，如「新增視覺化>圖形>延伸> &lt;子檔案夾名稱&#x200B;*> > &lt;*&#x200B;維度名稱&#x200B;**>」。

若要查看為資料集描述檔定義的所有維度以及每個維度的緩衝區大小，請在資料工作台中開啟介面並按一下 [!DNL Detailed Status] , **[!UICONTROL Performance]****[!UICONTROL Dimensions]** 然後展開節點。 控制查詢時間的緩衝區大小以MB表示。 有關該介面的詳細信 [!DNL Detailed Status] 息，請參閱《伺服器管理和安裝指南》。
