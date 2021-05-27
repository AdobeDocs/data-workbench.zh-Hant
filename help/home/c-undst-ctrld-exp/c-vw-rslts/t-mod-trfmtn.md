---
description: 現在x實驗欄位已可供使用，您必須建立延伸維度以在資料集中加入x實驗欄位，以便在Insight中檢視結果。
solution: Analytics,Analytics
title: 修改 Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# 修改 Transformation.cfg{#modifying-transformation-cfg}

現在x實驗欄位已可供使用，您必須建立延伸維度以在資料集中加入x實驗欄位，以便在Insight中檢視結果。

要執行此操作，必須將新維添加到[!DNL Transformation.cfg]檔案中。

如果計畫運行多個實驗，還必須將新的分割轉換添加到[!DNL Transformation.cfg]檔案中。 此分割轉換會分隔不同的實驗和群組名稱，以便更容易解讀資訊。 為避免在之後需要新增其他實驗時再次重新處理資料，Adobe建議您新增分割轉換，即使您目前不打算執行多個實驗亦然。

以下過程包括建立新的分割轉換和擴展尺寸。 如果不想添加拆分轉換，只需跳過步驟5-7。

**要修改Transformation.cfg**

1. 在[!DNL Insight]中，以在工作區內按一下滑鼠右鍵並按一下「**[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**」 ，或在「[!DNL Admin]」標籤上開啟「設定檔管理」工作區，以開啟[!DNL Profile Manager]。
1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示其內容。
1. 按一下右鍵[!DNL Transformation.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。
1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出現[!DNL Transformation.cfg]窗口。
1. 按一下&#x200B;**[!UICONTROL Transformation]**&#x200B;以顯示其內容。
1. 按一下右鍵&#x200B;**[!UICONTROL Transformations]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Split]**。
1. 依照下列範例，完成逗號轉換的新分割：

   ![步驟資訊](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >您可以在「名稱」欄位中輸入任何值。

1. 按一下右鍵&#x200B;**[!UICONTROL Extended Dimensions]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**。
1. 填入新維度，如下列範例所示：

   ![步驟資訊](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 您可以在「名稱」欄位中輸入任何值。
   >* 如果未包括Split轉換，則必須在[!DNL Input]欄位中鍵入&quot;x-experient&quot;。


1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL Transformation.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL profile name]**&#x200B;以保存對工作配置檔案進行的本地更改。

   >[!NOTE]
   >
   >資料集會立即開始重新轉換。

   如需[!DNL Transformation.cfg]和延伸維度的詳細資訊，請參閱&#x200B;*資料集組態指南*。
