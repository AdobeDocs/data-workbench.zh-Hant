---
description: 依預設，新建立的標籤會將關聯目錄中的子檔案夾顯示為階層式下拉式子目錄，而非子標籤。
title: 將子檔案夾顯示為子索引標籤
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# 將子檔案夾顯示為子索引標籤{#display-subfolders-as-subtabs}

依預設，新建立的標籤會將關聯目錄中的子檔案夾顯示為階層式下拉式子目錄，而非子標籤。

通過將&#x200B;*工作配置檔案名*\Workspaces\*tab name資料夾*放置在Data Workbench安裝目錄中，可以將子資料夾顯示為子頁籤（如下例所示）。[!DNL empty folder.useTabs]

以下示例顯示[!DNL Custom]頁籤及下拉子目錄。

![](assets/client-sub.png)

如果將[!DNL empty folder.useTabs]檔案放在Workspaces\Custom資料夾中，則Custom資料夾內的所有子資料夾都以子頁籤的形式顯示在[!DNL Worktop]中，如以下示例所示：

![](assets/client-sub2.png)

**若要將子檔案夾顯示為[!DNL Worktop]**

>[!NOTE]
>
>每個目錄級別都必須有[!DNL Tab Name.useTabs]檔案，子資料夾的內容才能顯示為子頁籤，而不是分層的下拉子目錄。

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Workspaces]**&#x200B;查看其內容。
1. 在&#x200B;*工作配置檔案名稱*&#x200B;列中，按一下右鍵[!DNL folder.useTabs]檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Copy]**。
1. 在[!DNL User]欄中，以滑鼠右鍵按一下「工作區\*tab name*」檔案夾，然後按一下「**[!UICONTROL Paste]**」。 該標籤中的子檔案夾現在會顯示為子標籤。
1. （可選）要使此更改對工作配置檔案的所有用戶可用，請按一下右鍵[!DNL User]列中[!DNL new folder.useTabs]檔案的白色複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > &lt; a3/>。**[!UICONTROL working profile name]**
