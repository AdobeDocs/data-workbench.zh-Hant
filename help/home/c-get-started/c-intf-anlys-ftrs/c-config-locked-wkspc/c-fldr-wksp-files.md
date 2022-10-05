---
description: 在Data Workbench安裝目錄的Workspaces資料夾中，folder.lock檔案指定是否鎖定該特定資料夾中的工作區，而workspace name.lock檔案指定是否鎖定特定工作區。
title: Folder.lock 和 workspace.lock 檔案
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Folder.lock 和 workspace.lock 檔案{#folder-lock-and-workspace-lock-files}

{{eol}}

在Data Workbench安裝目錄的Workspaces資料夾中，folder.lock檔案指定是否鎖定該特定資料夾中的工作區，而workspace name.lock檔案指定是否鎖定特定工作區。

鎖定整個資料夾時，可以在「工作區」(Workspaces)資料夾級別或子資料夾（頁簽）級別鎖定它們。 您也可以鎖定或解除鎖定所有資料夾（在「工作區」資料夾層級），然後指定特定子資料夾的例外(使用 [!DNL folder.lock] 檔案)或特定工作區(使用 *工作區名稱*.lock檔案)。

下列範例 [!DNL Profile Manager] 重點說明三個元素：

* A [!DNL folder.lock] 主工作區資料夾的檔案
* A [!DNL Monthly Numbers.lock] 檔案 [!DNL Monthly Numbers.vw] 工作區檔案

* A [!DNL folder.lock] 工作區的檔案\自定義子資料夾

![](assets/wsp_Locking_lockFiles.png)

在此範例中， [!DNL Workspaces folder.lock] 檔案設定為鎖定，這會鎖定此Data Workbench實例中的所有工作區。 Workspaces\Custom子資料夾 [!DNL folder.lock] 檔案設定為「解除鎖定」(unlocked)，這會解除鎖定上所有工作區 [!DNL Custom] 標籤。 最後， [!DNL Monthly Numbers.lock] 檔案設為鎖定，這會鎖定「每月編號」工作區。

## 建立.lock檔案 {#section-c4f78b4b43c347368a376904effb41d2}

您可以建立 [!DNL new folder.lock] 檔案，使用 [!DNL Create menu] 選項 [!DNL Profile Manager] 或 [!DNL Workspaces Manager]. 您也可以建立 [!DNL folder.lock] 或 *工作區名稱*&#x200B;通過複製和貼上現有檔案來鎖定檔案 [!DNL .lock] 檔案到相應的資料夾，更改檔案的名稱(對於 *工作區名稱*.lock檔案)，並視需要變更檔案中的設定。

**建立新資料夾.lock檔案**

1. 在Data Workbench中，開啟 [!DNL Workspaces Manager] 在工作區中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. 按一下要建立的資料夾 [!DNL folder.lock] 檔案。
1. 在 [!DNL User] 欄，在儲存格中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. A [!DNL new folder.lock] 檔案。 [!DNL New folder.lock] 檔案設定為 [解除鎖定] 依預設。
1. （選用）如果您需要變更檔案中的設定：

   1. 以滑鼠右鍵按一下檔案的勾號。
   1. 按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 此 [!DNL folder.lock] 檔案開啟。

   1. 將設定變更為 [鎖定].
   1. 儲存並關閉檔案。

1. 若要讓所有使用相同工作設定檔的使用者都使用此設定，請以滑鼠右鍵按一下檔案的核取記號，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

此資料夾中的工作區現在會根據新檔案中的設定而鎖定或解除鎖定。

**從現有檔案建立.lock檔案**

1. 在 [!DNL Profile Manager] 或 [!DNL Workspaces Manager]，按一下右鍵現有的複選標籤 [!DNL .lock] 按一下 **[!UICONTROL Copy]**.
1. 在 [!DNL User] 欄，將您要貼入的資料夾 [!DNL .lock] 檔案，按一下右鍵單元格，然後按一下 **[!UICONTROL Paste]**.
1. 如果此檔案用於鎖定個別工作區，請以滑鼠右鍵按一下 [!DNL .lock] 檔案 [!DNL User] 欄，並變更其名稱 [!DNL File] 欄位，以符合您要鎖定的工作區名稱。

   例如，若要鎖定 [!DNL Monthly Numbers.vw] 工作區中，您可將檔案命名為「 [!DNL Monthly Numbers.lock].&quot;如果此檔案用於鎖定個別工作區，請以滑鼠右鍵按一下 [!DNL .lock] 檔案 [!DNL User] 欄，並變更其名稱 [!DNL File] 欄位，以符合您要鎖定的工作區名稱。 例如，若要鎖定 [!DNL Monthly Numbers.vw] 工作區中，您可將檔案命名為「 [!DNL Monthly Numbers.lock].&quot;

1. 若要變更檔案中的設定：

   1. 以滑鼠右鍵按一下檔案的勾號。
   1. 按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 此 [!DNL .lock] 檔案開啟。

   1. 將設定變更為 [鎖定] 或 [解除鎖定].
   1. 儲存並關閉檔案。

1. 若要讓所有使用相同工作設定檔的使用者都使用此設定，請以滑鼠右鍵按一下檔案的核取記號，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

現在會根據新檔案中的設定鎖定或解除鎖定所選工作區。
