---
description: 初始化和更新設定檔的結構定義
title: 初始化和更新設定檔的結構定義
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# 初始化和更新設定檔的結構定義{#initializing-and-updating-a-profile-s-schema-definition}

1. 開啟要設定的配置檔案的&#x200B;**[!UICONTROL Schema Builder]**。
1. 從Insight描述檔擷取架構時，會顯示&#x200B;**[!UICONTROL Loading]**&#x200B;訊息。 載入架構的時間長度取決於所載入描述檔的複雜性。
1. 完成後，您將看到左窗格中&#x200B;**[!UICONTROL Insight Schema]**&#x200B;和右窗格中&#x200B;**[!UICONTROL Dashboard Schema]**&#x200B;之間差異的摘要。 此摘要將出現在&#x200B;**[!UICONTROL Schema Builder]**&#x200B;窗口的左下部。

   >[!NOTE]
   >
   >首次設定架構時，每個度量、維度和篩選器的列出方式會與控制面板的架構不同。 這是因為儀表板方案對象目前不存在。

   ![](assets/schema_builder2.png)

1. 按一下&#x200B;**[!UICONTROL Synchronize with Schema]**&#x200B;按鈕，將「分析結構」檢視中的所有度量、維度和篩選器與「控制面板結構」檢視同步。
1. 完成時，您應該會看到一則訊息，指出找不到任何差異：

   ![](assets/diff_found.png)

1. 如果控制面板結構有任何錯誤（例如重複的量度和維度），則您必須先手動更正這些錯誤，才能儲存。

   >[!NOTE]
   >
   >您可以從&#x200B;**[!UICONTROL Dashboard Schema]**&#x200B;中選擇性移除您不想出現在控制面板使用者面前的任何量度、維度或篩選器。 您會收到警告，指出「控制面板結構」中不存在項目，但不會阻止您儲存。

1. 準備就緒後，按一下&#x200B;**[!UICONTROL Save]**&#x200B;以儲存您對控制面板架構所做的變更。
1. 控制面板系統會使用此架構定義來填入控制面板介面的使用者可用的維度、量度和篩選器。
