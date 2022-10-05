---
description: 您必須將x-experience欄位新增至Log Processing.cfg檔案，以建立延伸維度。
solution: Analytics
title: 修改 Log Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# 修改 Log Processing.cfg{#modifying-log-processing-cfg}

{{eol}}

您必須將x-experience欄位新增至Log Processing.cfg檔案，以建立延伸維度。

請參閱 [修改Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**修改Log Processing.cfg的方式**

1. 在 [!DNL Insight]，開啟 [!DNL Profile Manager] 在工作區中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**，或在 [!DNL Admin] 標籤。
1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Dataset]** 來顯示其內容。
1. 以滑鼠右鍵按一下旁的核取記號 [!DNL Log Processing.cfg] 按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。
1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 此 [!DNL Log Processing.cfg] 的上界。
1. 按一下 **[!UICONTROL Fields]** 來顯示其內容。
1. 以滑鼠右鍵按一下目前清單中的最後一個欄位，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. 在新建立的欄位中鍵入x-experience，如以下示例所示：

   ![步驟資訊](assets/logprocessing.png)

1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.
1. 在 [!DNL Profile Manager]，按一下右鍵的複選標籤 [!DNL Log Processing.cfg] 在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* 以儲存本機對工作設定檔進行的變更。

   >[!NOTE]
   >
   >資料集會立即開始重新處理。

   如需記錄處理和欄位的詳細資訊，請參閱 *資料集組態指南*.
