---
description: 既然x實驗欄位已可用，您必須建立擴充維度以在資料集中包含x實驗欄位，以便在Insight中檢視結果。
solution: Analytics,Analytics
title: 修改 Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# 修改 Transformation.cfg{#modifying-transformation-cfg}

既然x實驗欄位已可用，您必須建立擴充維度以在資料集中包含x實驗欄位，以便在Insight中檢視結果。

若要這麼做，您必須在[!DNL Transformation.cfg]檔案中新增維度。

如果您計畫執行多個實驗，也必須將新的分割轉換新增至[!DNL Transformation.cfg]檔案。 此分割轉換可分隔不同的實驗和群組名稱，讓資訊更容易解讀。 為避免在日後需要新增其他實驗時重新處理資料，Adobe建議您新增分割變形，即使您目前不打算執行多個實驗亦然。

以下過程包括建立新的分割變形和擴展尺寸。 如果不想添加拆分轉換，只需跳過步驟5-7。

**要修改Transformation.cfg**

1. 在[!DNL Insight]中，在工作區內按一下右鍵並按一下&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** ，或在[!DNL Admin]頁籤上開啟「配置檔案管理」工作區，以開啟[!DNL Profile Manager]。
1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示其內容。
1. 按一下右鍵[!DNL Transformation.cfg]旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。
1. 按一下右鍵新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出現[!DNL Transformation.cfg]窗口。
1. 按一下&#x200B;**[!UICONTROL Transformation]**&#x200B;以顯示其內容。
1. 按一下右鍵&#x200B;**[!UICONTROL Transformations]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Split]**。
1. 按逗號轉換完成新分割，如以下範例所示：

   ![步驟資訊](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >您可以在「名稱」欄位中輸入任何值。

1. 按一下右鍵&#x200B;**[!UICONTROL Extended Dimensions]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**。
1. 完成新維，如下例所示：

   ![步驟資訊](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 您可以在「名稱」欄位中輸入任何值。
   >* 如果未包含分割變形，則必須在[!DNL Input]欄位中輸入&quot;x-experity&quot;。


1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL Transformation.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL profile name]**&#x200B;保存對工作配置檔案進行的本地更改。

   >[!NOTE]
   >
   >資料集會立即開始重新轉換。

   有關[!DNL Transformation.cfg]和擴展維的詳細資訊，請參閱&#x200B;*資料集配置指南*。
