---
description: You must add the x-experiment field to the Log Processing.cfg file, which is used to create an extended dimension.
solution: Analytics
title: 修改 Log Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# 修改 Log Processing.cfg{#modifying-log-processing-cfg}

You must add the x-experiment field to the Log Processing.cfg file, which is used to create an extended dimension.

請參閱 [修改Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6)。

**To modify Log Processing.cfg**

1. 在 [!DNL Insight]，開啟 [!DNL Profile Manager] 通過在工作區中按一下右鍵並按一下 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**，或在 [!DNL Admin] 頁籤。
1. 在 [!DNL Profile Manager]按一下 **[!UICONTROL Dataset]** 顯示其內容。
1. Right-click the check mark next to [!DNL Log Processing.cfg] and click **[!UICONTROL Make Local]**. 此檔案的複選標籤出現在 [!DNL User] 的雙曲餘切值。
1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 的 [!DNL Log Processing.cfg] 的上界。
1. 按一下 **[!UICONTROL Fields]** 顯示其內容。
1. 按一下右鍵當前清單中的最後一個欄位，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Field]**。
1. 在新建立的欄位中鍵入x-experite，如下例所示：

   ![步驟資訊](assets/logprocessing.png)

1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. 在 [!DNL Profile Manager]，按一下右鍵的複選標籤 [!DNL Log Processing.cfg] 的 [!DNL User] 列，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* 保存對工作配置檔案所做的更改。

   >[!NOTE]
   >
   >The dataset begins reprocessing immediately.

   有關日誌處理和欄位的詳細資訊，請參閱 *資料集配置指南*。
