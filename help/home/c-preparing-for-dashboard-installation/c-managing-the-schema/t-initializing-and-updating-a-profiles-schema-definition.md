---
description: 初始化和更新設定檔的結構定義
title: 初始化和更新設定檔的結構定義
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# 初始化和更新設定檔的結構定義{#initializing-and-updating-a-profile-s-schema-definition}

{{eol}}

1. 開啟 **[!UICONTROL Schema Builder]** 針對您要設定的設定檔。
1. A **[!UICONTROL Loading]** 訊息會在從Insight設定檔擷取架構時顯示。 載入架構的時間長度取決於要載入的設定檔的複雜度。
1. 完成後，您會看到 **[!UICONTROL Insight Schema]** 在左窗格中， **[!UICONTROL Dashboard Schema]** 在右窗格中。 此摘要會顯示在 **[!UICONTROL Schema Builder]** 窗口。

   >[!NOTE]
   >
   >首次設定結構時，每個量度、維度和篩選器的列出與控制面板的結構不同。 這是因為儀表板架構對象目前不存在。

   ![](assets/schema_builder2.png)

1. 按一下 **[!UICONTROL Synchronize with Schema]** 按鈕，將「分析結構」檢視中的所有量度、維度和篩選器與「控制面板結構」檢視同步。
1. 完成時，您應會看到訊息，指出找不到任何差異：

   ![](assets/diff_found.png)

1. 如果控制面板結構發生任何錯誤（例如重複的量度和維度），則您必須先手動修正，才能儲存。

   >[!NOTE]
   >
   >您可以從 **[!UICONTROL Dashboard Schema]** 不想向控制面板的使用者顯示。 您會收到警告，指出控制面板結構中不存在項目，但不會阻止您儲存。

1. 準備就緒後，按一下 **[!UICONTROL Save]** 以儲存對控制面板結構的變更。
1. 控制面板系統會使用此結構定義來填入控制面板介面的一般使用者可用的維度、量度和篩選器。
