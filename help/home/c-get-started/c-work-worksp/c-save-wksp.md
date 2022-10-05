---
description: 依預設，關閉解除鎖定的工作區會儲存對工作區所做的任何變更。
title: 儲存工作區
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# 儲存工作區{#save-a-workspace}

{{eol}}

依預設，關閉解除鎖定的工作區會儲存對工作區所做的任何變更。

如果工作區是伺服器工作區，則您的變更只會儲存在本機，除非您特別將更新後的工作區儲存至Data Workbench伺服器。 如需鎖定工作區的詳細資訊，請參閱 [解鎖工作區](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## 將工作區儲存在本機 {#section-3f331c880f1a490c96844103c2432d61}

預設的儲存位置為 **用戶\配置檔案名稱\工作區\頁簽名稱** 資料夾(位於Data Workbench安裝目錄中)。 例如，如果您使用「電影」設定檔，並從「 [!UICONTROL Custom] 標籤中，工作區會儲存至 **User\Movies\Workspaces\Custom** 資料夾(位於Data Workbench安裝目錄中)。

**要保存對工作區的更改**

* 在工作區中，按一下 **[!UICONTROL File]**，然後 **[!UICONTROL Save]**.

**將現有工作區儲存為新工作區的方式**

1. 在所需的 [!DNL Worktop] 頁簽，按一下要顯示的工作區縮圖。
1. 在工作區中，按一下 **[!UICONTROL File]**，然後按一下 **[!UICONTROL Save Copy As]**.
1. 在 [!DNL Save Workspace As] 對話框，指定要保存複製的工作區的名稱和位置，然後按一下 **[!UICONTROL Save]**.

## 將工作區儲存至Data Workbench伺服器 {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>只有具有適當權限的使用者才能將工作區儲存至Data Workbench伺服器。 有關詳細資訊，請與系統管理員聯繫。

將工作區儲存至連線的Data Workbench伺服器也稱為發佈工作區，因為工作區可讓其他使用者使用。 依預設，工作區會儲存至 *工作設定檔名稱*\Workspaces\*標籤名稱*Data Workbench伺服器的資料夾。 例如，如果您使用「電影」設定檔，並將工作區從儲存器儲存至連線的Data Workbench伺服器 [!DNL Custom] 頁簽中，工作區將保存到Data Workbench伺服器的「影片」\「工作區」\「自定義」資料夾。

**將工作區保存到Data Workbench伺服器**

* 在所需的 [!DNL Worktop] 頁簽，按一下右鍵要保存到Data Workbench伺服器的工作區縮略圖，然後按一下 **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
