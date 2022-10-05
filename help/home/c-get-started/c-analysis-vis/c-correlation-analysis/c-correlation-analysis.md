---
description: 統計關聯度量有意義的關係，以通過高級資料挖掘來識別機會。
title: 關聯矩陣
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
exl-id: 79c23bb9-2b4b-4fe0-bfdb-52721fbbdf0c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# 關聯矩陣{#correlation-matrix}

{{eol}}

統計關聯度量有意義的關係，以通過高級資料挖掘來識別機會。

使用 [Pearsons相關係數](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c), 「關聯矩陣」會提供您相關資訊，以便更好地識別行銷活動中的後續步驟、改善網站設計，或繼續深入客戶分析以取得其他關聯相依性。

## 建立關聯矩陣 {#section-87ed12ccc1af4196a1b6534e621c4cbb}

「關聯矩陣」會比較可數或不可數維度的量度。 然後，矩陣可經過修改，透過顏色挑選來突顯視覺效果內的關聯，或以文字圖、熱度圖或兩者皆呈現。

1. 開啟關聯矩陣。

   按一下右鍵 [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. 將會開啟維度表格。

   ![](assets/correlation_matrix_2.png)

   選取維度，例如 [!DNL Time] > [!DNL Day of the Week] 。 關聯表格會開啟，列和欄中會顯示矩陣角落所識別的維度，以及該維度的相關量度。 針對「星期」維度， **[!UICONTROL Visits]** 是相關聯的量度。

   ![](assets/correlation_matrix_1.png)

   關聯為1.000，因為您會比較量度本身（這反映出完美但無法使用的關聯）。

1. 變更其中一個量度。

   按一下滑鼠右鍵並選取 **[!UICONTROL Change Metric]** 變更列或欄中的量度。 這會設定兩個值量度之間的關聯。

   在此範例中，請變更 **[!UICONTROL Visits]** 量度 **[!UICONTROL Internal Searches]**. 按一下滑鼠右鍵並選取 [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. 新增更多量度至關聯矩陣。

   在量度欄或列中按一下滑鼠右鍵。 例如，從「量度」功能表新增 [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error].

   ![](assets/correlation_matrix_11.png)

   新量度會顯示在具有關聯數的欄中。 您可以新增其他量度，例如 **[!UICONTROL Email Signups]**，以建置表格。

   ![](assets/correlation_matrix_6.png)

   或新增量度至列，以比較欄中的量度。

   ![](assets/correlation_matrix_add_metric.png)

1. （選用）新增維度元素以限制量度。

   在工作區中按一下滑鼠右鍵，然後選取 **[!UICONTROL Table]**. 從開啟的維度表格中，按Ctrl + Alt並將元素拖曳至欄或列中的量度上。 元素會以方括弧顯示在量度旁。

   例如，對於 **[!UICONTROL Visits]** 量度，您可以選取 **[!UICONTROL Country]** as **[!UICONTROL New Zealand]**.

   ![](assets/correlation_matrix_dim_element.png)

   請注意，選取維度元素時，關聯會根據選取的維度元素而變更所有量度。 維度視窗關閉後，只有「紐西蘭」的造訪量度才會受限。

   >[!NOTE]
   >
   >如果以維度限制變更量度(按一下滑鼠右鍵並選取 **[!UICONTROL Change Metric]**)，則會遺失限制量度的維度元素。 您需要再次新增維度元素。

1. 建立 [二進位篩選](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c) 以進一步限制量度。 以滑鼠右鍵按一下表格中的量度，然後從功能表選取「二進位篩選」。

## 關聯規劃和分析目標 {#section-cc322da60b7e417ba29e72b0afeb6f79}

以下是建立關聯矩陣的一般目標。

**針對指定的維度識別兩個量度之間的關係**. 在此範例中，矩陣是以核心維度「星期」為基礎建立，與「內部搜尋」、「登入」和「調查顯示」量度事件相比，具有「造訪」、「電子郵件註冊」和「登入錯誤」等量度。

**建立聚焦分析的假設**. 執行關聯分析後，下一步是尋找量度的相依性和關聯。 例如，了解內部搜尋對電子郵件註冊有影響，可提供路徑來預測該關係，並修改行銷活動或網站導覽設計。

**識別量度以包含更進階的資料挖掘演算法**. 在大多數情況下，關鍵量度會被識別，因為它們會被看到影響多個關聯。 您現在可以取用這些關鍵量度，並套用至其他資料挖掘分析，以獲得更深入的分析。

## 關聯矩陣功能附註 {#section-ef3626c665ea468a9ecdad624b4132f5}

**篩選和選取表格中的維度元素會比較相同值**. 例如，使用「一週的某天」維度，然後按一下該核心維度的元素，例如按一下「周的某天」維度表格中的特定一天，會以100%呈現一對一的相符項目，因而無法提供可用的關聯。 因為根維度是一週的某天，所以在周的某天維度表格中進行的任何選取都會將矩陣變更為一對一關聯。

![](assets/correlation_matrix_10.png)

不過，1到1關聯（當所有元素都選取了單一項目時）僅在該特定日期。 如果您進行多個選取，則不一定會維持1到1的關聯，而且無論選取一週中的1天或1+天，都不一定會產生100%符合。

**統計關聯不等於關聯資料模型**，此元件為Adobe Analytics產品的歷史參考資料。 Data Workbench中的統計關聯以 [皮爾森關聯模型](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c).

**在散布圖中顯示關聯**. 以滑鼠右鍵按一下散布圖上的標題，然後選擇 [!DNL Display Correlation] 從 [!DNL Visualization] 功能表。 「關聯」值將顯示在散布圖的右上部。

>[!NOTE]
>
>如果應用程式無法執行Pearsons相關計算，則散布圖和Pearsons矩陣將顯示「計算錯誤」。 這通常是因為資料不足，而可能導致方程式嘗試將數值除以0。
