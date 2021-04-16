---
description: 統計關聯會測量有意義的關係，以透過進階資料挖掘來識別機會。
title: 關聯矩陣
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
exl-id: 79c23bb9-2b4b-4fe0-bfdb-52721fbbdf0c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# 關聯矩陣{#correlation-matrix}

統計關聯會測量有意義的關係，以透過進階資料挖掘來識別機會。

使用[Pearsons關聯繫數](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c)，關聯矩陣會提供您相關資訊，以更好地識別行銷活動的後續步驟、改善網站設計，或持續深入的客戶分析，以取得其他關聯相依性。

## 建立關聯矩陣{#section-87ed12ccc1af4196a1b6534e621c4cbb}

「關聯矩陣」會比較可計數或非可計數維度上的量度。 然後可修改矩陣，透過挑選顏色來反白標示視覺效果中的關聯，或將其轉換為文字地圖、熱圖或兩者。

1. 開啟關聯矩陣。

   按一下右鍵[!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]。 將開啟維表。

   ![](assets/correlation_matrix_2.png)

   從此菜單中選擇維，如[!DNL Time] > [!DNL Day of the Week]。 關聯表將會開啟，其中已識別的維度位於矩陣的角落，其關聯度量位於列與欄中。 對於「星期」維度，**[!UICONTROL Visits]**&#x200B;是相關的度量。

   ![](assets/correlation_matrix_1.png)

   關聯為1.000，因為您會比較量度本身（這反映完美但無法使用的關聯）。

1. 變更其中一個量度。

   按一下右鍵並選擇&#x200B;**[!UICONTROL Change Metric]**&#x200B;以更改行或列中的度量。 這會設定兩個值量度之間的關聯。

   在此範例中，將欄中的&#x200B;**[!UICONTROL Visits]**&#x200B;量度變更為&#x200B;**[!UICONTROL Internal Searches]**。 按一下右鍵並選擇[!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches]。

   ![](assets/correlation_matrix_change_metric.png)

1. 新增更多量度至關聯矩陣。

   在量度欄或列中按一下滑鼠右鍵。 例如，從「量度」功能表新增[!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error]。

   ![](assets/correlation_matrix_11.png)

   新量度會顯示在具有關聯數的欄中。 您可以新增其他量度，例如&#x200B;**[!UICONTROL Email Signups]**，以建立表格。

   ![](assets/correlation_matrix_6.png)

   或新增量度至列，以比較欄中的量度。

   ![](assets/correlation_matrix_add_metric.png)

1. （可選）新增維度元素以限制量度。

   在工作區中按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL Table]**。 在開啟的維度表格中，按Ctrl + Alt鍵並將元素拖曳至欄或列中的度量上。 元素會以方括弧顯示在量度旁。

   例如，對於&#x200B;**[!UICONTROL Visits]**&#x200B;量度，您可以選取&#x200B;**[!UICONTROL Country]**&#x200B;作為&#x200B;**[!UICONTROL New Zealand]**&#x200B;來限制量度。

   ![](assets/correlation_matrix_dim_element.png)

   請注意，當您選取維度元素時，關聯會根據選取的維度元素在所有度量中變更。 維度視窗關閉後，只有「紐西蘭」的「瀏覽」量度才會受到限制。

   >[!NOTE]
   >
   >如果變更具有維度約束的量度（透過按一下滑鼠右鍵並選取&#x200B;**[!UICONTROL Change Metric]**），則會遺失限制量度的維度元素。 您需要再次新增維度元素。

1. 建立[二進位篩選](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c)以進一步限制量度。 在表格中按一下滑鼠右鍵，然後從功能表選取「二進位篩選」。

## 關聯規劃和分析目標{#section-cc322da60b7e417ba29e72b0afeb6f79}

以下是建立關聯矩陣的一般目標。

**識別兩個量度對指定維度的關係**。在範例中，矩陣是以核心維度「一週中的某天」為基礎，與「內部搜尋」、「登入」和「調查顯示」度量事件相比，其中包含「瀏覽」、「電子郵件註冊」和「登入錯誤」度量。

**建立焦點分析的假設**。執行關聯分析後，您的下一步是尋找量度的相依性和關聯。 例如，瞭解內部搜尋對電子郵件註冊有影響，提供了預測該關係並修改行銷活動或網站導覽設計的路徑。

**識別要包含更進階資料挖掘演算法的量度**。在大多數情況下，關鍵量度會被識別，因為它們會影響多個關聯。 您現在可以取用這些關鍵量度，並將它們套用至其他資料挖掘分析，以獲得更深入的洞察。

## 關聯矩陣功能說明{#section-ef3626c665ea468a9ecdad624b4132f5}

**篩選和選取表格中的維度元素時，會比較類似值**。例如，使用「周」維度的「日」，然後按一下該核心維度的元素，例如按一下「周」維度表格中的特定日，會以100%呈現一對一的符合，而不提供任何可用的關聯。 由於根維度是「周的日」，因此在「周的日」維度表內所做的任何選擇都會將矩陣變更為一對一的關聯。

![](assets/correlation_matrix_10.png)

但是，1到1關聯（當所有元素都做成單一選取時）只在該特定日期。 如果您進行多項選擇，則不一定會維持1到1的關聯，而且無論選取一週中的1天或1天以上，都不一定會產生100%的比對。

**統計關聯不等於關聯資料模型**，即Adobe Analytics產品的歷史參考。資料工作台中的統計相關性基於[Pearson相關模型](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c)。

**在散布圖中顯示關聯**。在散布圖上按一下滑鼠右鍵，然後從[!DNL Visualization]選單選擇[!DNL Display Correlation]。 「關聯」值將顯示在「散布圖」的右上方區段。

>[!NOTE]
>
>如果應用程式無法執行Pearsons關聯計算，「散布圖」和「Pearsons」矩陣會顯示「計算錯誤」。 這通常是因為資料不足，這會導致方程式嘗試除以0。
