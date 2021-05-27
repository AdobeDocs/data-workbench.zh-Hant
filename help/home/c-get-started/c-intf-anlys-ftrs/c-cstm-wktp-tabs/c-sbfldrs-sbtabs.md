---
description: 依預設，新建立的索引標籤會將關聯目錄內的子資料夾顯示為階層式下拉式子目錄，而非子索引標籤。
title: 將子檔案夾顯示為子索引標籤
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# 將子檔案夾顯示為子索引標籤{#display-subfolders-as-subtabs}

依預設，新建立的索引標籤會將關聯目錄內的子資料夾顯示為階層式下拉式子目錄，而非子索引標籤。

通過將[!DNL empty folder.useTabs]檔案放在&#x200B;*工作配置檔案名稱*\Workspaces\*tab名稱資料夾*內，可將子資料夾顯示為子頁簽（如以下示例所示）。

下列範例顯示[!DNL Custom]標籤及其下拉式子目錄。

![](assets/client-sub.png)

如果將[!DNL empty folder.useTabs]檔案放在Workspaces\Custom資料夾中，則Custom資料夾中的所有子資料夾都會在[!DNL Worktop]中顯示為子頁簽，如以下示例所示：

![](assets/client-sub2.png)

**若要將子檔案夾顯示為[!DNL Worktop]**

>[!NOTE]
>
>每個目錄級別必須有[!DNL Tab Name.useTabs]檔案，子資料夾的內容才能顯示為子頁簽，而不是分層的下拉子目錄。

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Workspaces]**&#x200B;以查看其內容。
1. 在&#x200B;*工作設定檔名稱*&#x200B;欄中，以滑鼠右鍵按一下其中一個[!DNL folder.useTabs]檔案的勾號，然後按一下&#x200B;**[!UICONTROL Copy]**。
1. 在[!DNL User]欄中按一下右鍵Workspaces\*tab name*資料夾，然後按一下&#x200B;**[!UICONTROL Paste]**。 該索引標籤內的子資料夾現在會顯示為子索引標籤。
1. （可選）要使工作配置檔案的所有用戶都能使用此更改，請在[!DNL User]列中按一下右鍵[!DNL new folder.useTabs]檔案的白勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**。
