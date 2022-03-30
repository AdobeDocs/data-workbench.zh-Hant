---
description: 既然x實驗欄位可用，則必須建立擴展維以將x實驗欄位包含在資料集中，這允許您在Insight中查看結果。
solution: Analytics
title: 修改 Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# 修改 Transformation.cfg{#modifying-transformation-cfg}

既然x實驗欄位可用，則必須建立擴展維以將x實驗欄位包含在資料集中，這允許您在Insight中查看結果。

為此，必須向 [!DNL Transformation.cfg] 的子菜單。

如果計畫運行多個實驗，還必須向 [!DNL Transformation.cfg] 的子菜單。 此分割轉換將不同的實驗和組名分開，以便更容易理解資訊。 為了避免在以後需要添加其他實驗時再次重新處理資料，Adobe建議您添加剝離轉換，即使您當前不打算運行多個實驗。

以下過程包括建立新的分割轉換和擴展尺寸。 如果不想添加拆分轉換，只需跳過步驟5-7。

**修改Transformation.cfg**

1. 在 [!DNL Insight]，開啟 [!DNL Profile Manager] 通過在工作區中按一下右鍵並按一下 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**，或在 [!DNL Admin] 頁籤。
1. 在 [!DNL Profile Manager]按一下 **[!UICONTROL Dataset]** 顯示其內容。
1. 按一下右鍵旁邊的複選標籤 [!DNL Transformation.cfg] 按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤出現在 [!DNL User] 的雙曲餘切值。
1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 的 [!DNL Transformation.cfg] 的上界。
1. 按一下 **[!UICONTROL Transformation]** 顯示其內容。
1. 按一下右鍵 **[!UICONTROL Transformations]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Split]**。
1. 完成對逗號轉換的新拆分，如下例所示：

   ![步驟資訊](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >可以在「名稱」(Name)欄位中輸入任何值。

1. 按一下右鍵 **[!UICONTROL Extended Dimensions]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**。
1. 完成新尺寸，如下例所示：

   ![步驟資訊](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 可以在「名稱」(Name)欄位中輸入任何值。
   >* 如果未包括拆分轉換，則必須在 [!DNL Input] 的子菜單。


1. 按一下右鍵 **[!UICONTROL (modified)]** 按一下 **[!UICONTROL Save]**。
1. 在 [!DNL Profile Manager]，按一下右鍵的複選標籤 [!DNL Transformation.cfg] 的 [!DNL User] 列，然後按一下 **[!UICONTROL Save to]** > **[!UICONTROL profile name]** 保存對工作配置檔案所做的更改。

   >[!NOTE]
   >
   >資料集立即開始重新轉換。

   有關 [!DNL Transformation.cfg] 和擴展維，請參見 *資料集配置指南*。
