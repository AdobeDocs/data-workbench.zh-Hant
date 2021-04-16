---
description: 在Data Workbench安裝目錄的「工作區」(Workspaces)資料夾內，folder.lock檔案指定是否鎖定該特定資料夾中的工作區，而工作區name.lock檔案指定是否鎖定特定工作區。
title: Folder.lock 和 workspace.lock 檔案
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Folder.lock 和 workspace.lock 檔案{#folder-lock-and-workspace-lock-files}

在Data Workbench安裝目錄的「工作區」(Workspaces)資料夾內，folder.lock檔案指定是否鎖定該特定資料夾中的工作區，而工作區name.lock檔案指定是否鎖定特定工作區。

鎖定整個資料夾時，可以在「工作區」(Workspaces)資料夾級別或子資料夾（頁籤）級別鎖定它們。 您也可以鎖定或解除鎖定所有資料夾（在「工作區」資料夾級別），然後指定特定子資料夾（使用[!DNL folder.lock]檔案）或特定工作區（使用&#x200B;*工作區名稱*.lock檔案）的例外情況。

[!DNL Profile Manager]的下列範例會反白顯示三個元素：

* 主Workspaces資料夾的[!DNL folder.lock]檔案
* [!DNL Monthly Numbers.vw]工作區檔案的[!DNL Monthly Numbers.lock]檔案

* Workspaces\Custom子資料夾的[!DNL folder.lock]檔案

![](assets/wsp_Locking_lockFiles.png)

在此示例中，[!DNL Workspaces folder.lock]檔案設定為鎖定，這將鎖定此Data Workbench實例中的所有工作區。 Workspaces\Custom子資料夾[!DNL folder.lock]檔案設定為解鎖，這將解鎖[!DNL Custom]頁籤上的所有工作區。 最後，[!DNL Monthly Numbers.lock]檔案會設為鎖定，這會鎖定「每月數字」工作區。

## 建立。lock檔案{#section-c4f78b4b43c347368a376904effb41d2}

您可以使用[!DNL Profile Manager]或[!DNL Workspaces Manager]中的[!DNL Create menu]選項來建立[!DNL new folder.lock]檔案。 您也可以將現有的[!DNL .lock]檔案複製並貼至適當的檔案夾，變更檔案名稱（僅限&#x200B;*工作區名稱*.lock檔案），並視需要變更檔案中的設定，以建立[!DNL folder.lock]或&#x200B;*工作區名稱*.lock檔案。

**建立新folder.lock檔案**

1. 在Data Workbench中，在工作區中按一下右鍵並按一下&#x200B;**[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**&#x200B;以開啟[!DNL Workspaces Manager]。
1. 按一下要為其建立[!DNL folder.lock]檔案的資料夾。
1. 在該資料夾的[!DNL User]欄中，以滑鼠右鍵按一下儲存格，然後按一下&#x200B;**[!UICONTROL Create]** > **[!UICONTROL folder.lock]**。 出現[!DNL new folder.lock]檔案。 [!DNL New folder.lock] 檔案預設會設 [] 為unlockedd。
1. （可選）如果您需要變更檔案中的設定：

   1. 按一下右鍵檔案的複選標籤。
   1. 按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 將開啟[!DNL folder.lock]檔案。

   1. 將設定更改為[locked]。
   1. 儲存並關閉檔案。

1. 要將此設定設定為所有使用相同工作配置檔案的用戶，請按一下右鍵檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]**>*。

現在會根據新檔案中的設定，鎖定或解除鎖定此檔案夾中的工作區。

**從現有檔案建立。lock檔案**

1. 在[!DNL Profile Manager]或[!DNL Workspaces Manager]中，按一下右鍵現有[!DNL .lock]檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Copy]**。
1. 在要將[!DNL .lock]檔案貼上到的資料夾的[!DNL User]列中，按一下右鍵單元格，然後按一下&#x200B;**[!UICONTROL Paste]**。
1. 如果此檔案用於鎖定單個工作區，請按一下右鍵[!DNL User]列中[!DNL .lock]檔案的複選標籤，並更改[!DNL File]欄位中的名稱，以匹配要鎖定的工作區的名稱。

   例如，要鎖定[!DNL Monthly Numbers.vw]工作區，請為檔案命名&quot;[!DNL Monthly Numbers.lock]&quot;。如果此檔案用於鎖定單個工作區，請按一下右鍵[!DNL User]列中[!DNL .lock]檔案的複選標籤，並更改[!DNL File]欄位中的名稱，以匹配要鎖定的工作區的名稱。 例如，要鎖定[!DNL Monthly Numbers.vw]工作區，請為檔案命名&quot;[!DNL Monthly Numbers.lock]&quot;。

1. 要更改檔案中的設定：

   1. 按一下右鍵檔案的複選標籤。
   1. 按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 將開啟[!DNL .lock]檔案。

   1. 將設定更改為[locked]或[unlocked]。
   1. 儲存並關閉檔案。

1. 要將此設定設定為所有使用相同工作配置檔案的用戶，請按一下右鍵檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]**>*。

選取的工作區現在會根據新檔案中的設定，鎖定或解除鎖定。
