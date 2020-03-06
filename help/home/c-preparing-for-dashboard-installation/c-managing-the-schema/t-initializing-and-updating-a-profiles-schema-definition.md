---
description: 'null'
solution: Analytics
title: 初始化和更新配置檔案的方案定義
topic: Data workbench
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 初始化和更新配置檔案的方案定義{#initializing-and-updating-a-profile-s-schema-definition}

1. 開啟 **[!UICONTROL Schema Builder]** 要設定的配置檔案。
1. 從 **[!UICONTROL Loading]** Insight描述檔擷取結構時，將會顯示訊息。 載入架構的時間長度取決於所載入描述檔的複雜性。
1. 完成後，您將會在左窗格中看到 **[!UICONTROL Insight Schema]** 與右窗格中 **[!UICONTROL Dashboard Schema]** 的差異摘要。 此摘要將出現在窗口的左下部 **[!UICONTROL Schema Builder]** 分。

   >[!NOTE]
   >
   >首次設定架構時，每個度量、維度和篩選器的列出方式會與控制面板的架構不同。 這是因為儀表板方案對象目前不存在。

   ![](assets/schema_builder2.png)

1. 按一下按 **[!UICONTROL Synchronize with Schema]** 鈕，將「分析結構」檢視中的所有量度、維度和篩選器與「控制面板結構」檢視同步。
1. 完成時，您應該會看到一則訊息，指出找不到任何差異：

   ![](assets/diff_found.png)

1. 如果控制面板結構有任何錯誤（例如重複的量度和維度），則您必須先手動更正這些錯誤，才能儲存。

   >[!NOTE]
   >
   >您可以從控制面板的使用者中，選擇 **[!UICONTROL Dashboard Schema]** 性移除任何您不想要顯示的量度、維度或篩選器。 您會收到警告，指出「控制面板結構」中不存在項目，但不會阻止您儲存。

1. 準備就緒後，按 **[!UICONTROL Save]** 一下以儲存您對控制面板架構所做的變更。
1. 控制面板系統會使用此架構定義來填入控制面板介面的使用者可用的維度、量度和篩選器。
