---
description: Insight Server(InsightServer64.exe)可讓您從事件資料或查閱資料定義自訂維度。
title: 關於延伸維度
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# 關於延伸維度{#about-extended-dimensions}

Insight Server(InsightServer64.exe)可讓您從事件資料或查閱資料定義自訂維度。

您定義的任何自訂維度都稱為延伸維度。 您可以使用它們來建立視覺效果、建立延伸量度或執行分析，以了解與您的業務管道相關的操作和問題。 您可以在[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案中定義數種擴展維。

擴展維表示日誌欄位值與父維之間的關係。 父維度可以是任何使用者定義的可數維度。 請參閱[可數Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)。 在[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案中定義維時，可指定父級。 維的父級與其級別相同。 例如，如果您定義父項為「工作階段」的維，則該維是工作階段層級維。

>[!NOTE]
>
>日誌欄位值可以來自日誌([!DNL .vsl])檔案或其他事件資料源中可用的固有值，也可以來自通過使用轉換建立的擴展日誌欄位。

若要將延伸維度新增至視覺效果，請從[!DNL Select Dimension]功能表內的「延伸」清單中存取。 例如，若要將延伸維度新增至圖表視覺效果，您可以在工作區內以滑鼠右鍵按一下，然後按一下「**[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt; a4/>>*」。 **[!UICONTROL dimension name]**&#x200B;若要在Data Workbench介面中組織擴充維度的清單，您可以將擴充維度移至您建立的子資料夾。 請參閱&#x200B;*Data Workbench使用手冊*&#x200B;的管理介面一章。 若您這麼做，子資料夾的名稱也會出現在功能表中，如新增視覺效果>圖表>延伸> &lt;*子資料夾名稱*> > &lt;*維度名稱*>。

若要查看已針對資料集設定檔定義的所有維度以及每個維度的緩衝大小，請開啟Data Workbench中的[!DNL Detailed Status]介面，按一下&#x200B;**[!UICONTROL Performance]**，然後按一下&#x200B;**[!UICONTROL Dimensions]**&#x200B;以展開節點。 控制查詢時間的緩衝區大小以MB表示。 有關[!DNL Detailed Status]介面的詳細資訊，請參閱伺服器管理和安裝指南。
