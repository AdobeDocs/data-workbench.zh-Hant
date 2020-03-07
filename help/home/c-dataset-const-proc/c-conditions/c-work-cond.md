---
description: 新增、移除或複製條件的相關資訊。
solution: Analytics
title: 使用條件
topic: Data workbench
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 使用條件{#working-with-conditions}

新增、移除或複製條件的相關資訊。

* [向資料集配置檔案添加條件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [從資料集配置檔案中刪除條件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [複製條件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## 向資料集配置檔案添加條件 {#section-3e2a34db047b462585502f69722f6511}

1. 在資料集設定檔中工作時，請 [!DNL Profile Manager] 使用開啟您要編輯的資料集設定檔。

   * 要開啟文 [!DNL Log Processing.cfg] 件，請參 [閱編輯日誌處理配置檔案](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)。

   * 要開啟文 [!DNL Transformation.cfg] 件，請參 [閱編輯轉換配置檔案](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

   * 若要開啟檔 [!DNL Dataset Include] 案，請參 [閱資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

1. 在資料集設定檔案中，找出您要定義的記錄項目條件或條件參數。
1. 按一下右鍵參數並按一下 **[!UICONTROL Add new]**。 選擇下列條件類型之一：

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. 視需要編輯條件的參數。 如需每個條件參數的說明，請參閱本附錄的適當章節。
1. 要保存更改，請按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save]**。

1. 若要讓本機所做的變更生效，請在欄中按一下滑鼠右鍵，然後按一下 [!DNL Profile Manager,] > &lt;* [!DNL User]**[!UICONTROL Save to]****[!UICONTROL profile name]***>，其中描述檔名稱是資料集描述檔的名稱或檔案所屬的繼承描述檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

## 從資料集配置檔案中刪除條件 {#section-677270f93f1648c3a268ca2aea7d4540}

1. 按一下右鍵條件的名稱或與要刪除的條件對應的編號。
1. 按一下 **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***> ，其中number是與要刪除的條件對應的數字。

## 複製條件 {#section-00617bcf2c274f428686b2ec7f2d1db8}

您可以將條件從一個位置複製到同一檔案中的另一個位置，也可以將條件從一個資料集配置檔案複製到另一個資料集配置檔案。

1. 按一下右鍵條件的名稱或與要複製的條件對應的編號，然後按一下 **[!UICONTROL Copy]**。
1. 按一下右鍵要放置複製條件的下方條件的名稱或編號，然後按一下 **[!UICONTROL Paste]**。

