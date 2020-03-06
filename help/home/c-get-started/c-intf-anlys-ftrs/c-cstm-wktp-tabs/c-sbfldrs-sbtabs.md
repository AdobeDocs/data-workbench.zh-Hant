---
description: 依預設，新建立的標籤會將關聯目錄中的子檔案夾顯示為階層式下拉式子目錄，而非子標籤。
solution: Analytics
title: 將子檔案夾顯示為子標籤
topic: Data workbench
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 將子檔案夾顯示為子標籤{#display-subfolders-as-subtabs}

依預設，新建立的標籤會將關聯目錄中的子檔案夾顯示為階層式下拉式子目錄，而非子標籤。

您可以將子檔案夾顯示為子標籤（如下例所示），方法是將 [!DNL empty folder.useTabs] 檔案置於「資料工作台」安 *裝目錄中的*&#x200B;工作描述檔名稱\Workspaces\*tab name folder*中。

以下示例顯示帶有 [!DNL Custom] 下拉子目錄的頁籤。

![](assets/client-sub.png)

如果將檔案放 [!DNL empty folder.useTabs] 置在Workspaces\Custom資料夾中，則Custom資料夾內的所有子資料夾都會以子頁籤的形式顯示 [!DNL Worktop] ，如下例所示：

![](assets/client-sub2.png)

**若要將子檔案夾顯示為[!DNL Worktop]**

>[!NOTE]
>
>每個目錄級別都必須有 [!DNL Tab Name.useTabs] 一個檔案，子資料夾的內容才能顯示為子頁籤，而不是分層的下拉子目錄。

1. 在中，單 [!DNL Profile Manager]擊以 **[!UICONTROL Workspaces]** 查看其內容。
1. 在工作 *配置檔案名稱列* ，按一下右鍵其中一個檔案的複選標籤，然 [!DNL folder.useTabs] 後按一下 **[!UICONTROL Copy]**。
1. 在「工作區」\* [!DNL User] tab名稱*資料夾的欄中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Paste]**。 該標籤中的子檔案夾現在會顯示為子標籤。
1. （可選）要使此更改可供工作配置檔案的所有用戶使用，請按一下右鍵列中文 [!DNL new folder.useTabs] 件的白色複選 [!DNL User] 標籤，然後按一下 **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>。

