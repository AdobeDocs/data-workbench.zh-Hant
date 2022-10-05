---
description: 依預設，新建立的索引標籤會將關聯目錄內的子資料夾顯示為階層式下拉式子目錄，而非子索引標籤。
title: 將子檔案夾顯示為子索引標籤
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# 將子檔案夾顯示為子索引標籤{#display-subfolders-as-subtabs}

{{eol}}

依預設，新建立的索引標籤會將關聯目錄內的子資料夾顯示為階層式下拉式子目錄，而非子索引標籤。

您可以放置 [!DNL empty folder.useTabs] 檔案 *工作設定檔名稱*\Workspaces\*標籤名稱資料夾*，在Data Workbench安裝目錄中。

下列範例顯示 [!DNL Custom] 下拉式子目錄的標籤。

![](assets/client-sub.png)

若您將 [!DNL empty folder.useTabs] 檔案在Workspaces\Custom資料夾中， Custom資料夾中的所有子資料夾都顯示在 [!DNL Worktop] 作為子標籤，如下列範例所示：

![](assets/client-sub2.png)

**若要將子檔案夾顯示為[!DNL Worktop]**

>[!NOTE]
>
>每個目錄級別必須具有 [!DNL Tab Name.useTabs] 子資料夾內容的檔案，以顯示為子標籤，而非階層式下拉式子目錄。

1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Workspaces]** 來檢視其內容。
1. 在 *工作設定檔名稱* 欄，按一下右鍵其中一個 [!DNL folder.useTabs] 檔案，按一下 **[!UICONTROL Copy]**.
1. 在 [!DNL User] 「工作區」(Workspaces)\*頁簽名稱*資料夾的列，然後按一下 **[!UICONTROL Paste]**. 該索引標籤內的子資料夾現在會顯示為子索引標籤。
1. （可選）若要讓此變更可供工作設定檔的所有使用者使用，請以滑鼠右鍵按一下 [!DNL new folder.useTabs] 檔案 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>。
