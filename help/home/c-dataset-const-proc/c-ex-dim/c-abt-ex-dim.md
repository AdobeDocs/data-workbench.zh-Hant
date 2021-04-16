---
description: Insight Server(InsightServer64.exe)可讓您根據事件資料或查閱資料定義自訂維度。
title: 關於延伸維度
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# 關於延伸維度{#about-extended-dimensions}

Insight Server(InsightServer64.exe)可讓您根據事件資料或查閱資料定義自訂維度。

您定義的任何自訂維度都稱為延伸維度。 您可以使用它們來建立視覺化、建立擴充量度或執行分析，以瞭解與您的業務通道相關的運作和問題。 您可以在[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案中定義數種類型的擴充尺寸。

擴展維表示日誌欄位值與父維之間的關係。 父維度可以是任何使用者定義的可計數維度。 請參閱[可計數Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)。 在[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案中定義維時，可指定父項。 維的父級與其級別相同。 例如，如果定義具有父代「會話」的維，則該維是會話級維。

>[!NOTE]
>
>日誌欄位值可以來自日誌([!DNL .vsl])檔案或其他事件資料源中的固有值，也可以來自通過使用轉換建立的擴展日誌欄位。

若要將擴充維度新增至視覺化，請從[!DNL Select Dimension]功能表的「擴充」清單存取該維度。 例如，若要將延伸維度新增至圖形視覺化，請在工作區中按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > ***[!UICONTROL dimension name]**>*。 如果您想要在資料工作台介面中組織擴充維度的清單，可以將擴充維度移至您建立的子檔案夾。 請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的「管理介面」一章。 如果您這麼做，子檔案夾的名稱也會出現在功能表中，如「新增視覺化>圖形>延伸> *子資料夾名稱*> > *維度名稱*」中。

若要查看已為資料集配置檔案定義的所有維以及每個維的緩衝區大小，請開啟資料工作台中的[!DNL Detailed Status]介面，然後按一下&#x200B;**[!UICONTROL Performance]** ，然後按一下&#x200B;**[!UICONTROL Dimensions]**&#x200B;展開節點。 控制查詢時間的緩衝區大小以MB表示。 有關[!DNL Detailed Status]介面的詳細資訊，請參閱《Server Administration and Installation》（伺服器管理和安裝）指南。
