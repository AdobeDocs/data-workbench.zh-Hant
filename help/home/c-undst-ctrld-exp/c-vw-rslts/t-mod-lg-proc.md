---
description: 您必須將x-experience欄位新增至Log Processing.cfg檔案，以建立延伸維度。
solution: Analytics,Analytics
title: 修改 Log Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# 修改 Log Processing.cfg{#modifying-log-processing-cfg}

您必須將x-experience欄位新增至Log Processing.cfg檔案，以建立延伸維度。

請參閱[修改Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6)。

**修改Log Processing.cfg的方式**

1. 在[!DNL Insight]中，以在工作區內按一下滑鼠右鍵並按一下「**[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**」 ，或在「[!DNL Admin]」標籤上開啟「設定檔管理」工作區，以開啟[!DNL Profile Manager]。
1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示其內容。
1. 按一下右鍵[!DNL Log Processing.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。
1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出現[!DNL Log Processing.cfg]窗口。
1. 按一下&#x200B;**[!UICONTROL Fields]**&#x200B;以顯示其內容。
1. 按一下右鍵當前清單中的最後一個欄位，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Field]**。
1. 在新建立的欄位中鍵入x-experience，如以下示例所示：

   ![步驟資訊](assets/logprocessing.png)

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL Log Processing.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*&#x200B;以保存對工作配置檔案進行的本地更改。

   >[!NOTE]
   >
   >資料集會立即開始重新處理。

   如需記錄處理和欄位的詳細資訊，請參閱&#x200B;*資料集設定指南*。
