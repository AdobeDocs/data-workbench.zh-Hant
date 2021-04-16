---
description: 新增、移除或複製條件的相關資訊。
title: 使用條件
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# 使用條件{#working-with-conditions}

新增、移除或複製條件的相關資訊。

* [向資料集配置檔案添加條件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [從資料集配置檔案中刪除條件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [複製條件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## 向資料集配置檔案{#section-3e2a34db047b462585502f69722f6511}添加條件

1. 在資料集設定檔中工作時，請使用[!DNL Profile Manager]來開啟您要編輯的資料集設定檔。

   * 要開啟[!DNL Log Processing.cfg]檔案，請參閱[編輯日誌處理配置檔案](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)。

   * 要開啟[!DNL Transformation.cfg]檔案，請參閱[編輯轉換配置檔案](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

   * 要開啟[!DNL Dataset Include]檔案，請參閱[資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

1. 在資料集設定檔案中，找出您要定義的記錄項目條件或條件參數。
1. 按一下右鍵參數，然後按一下&#x200B;**[!UICONTROL Add new]**。 選擇下列條件類型之一：

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. 視需要編輯條件的參數。 如需每個條件參數的說明，請參閱本附錄的適當章節。
1. 要保存更改，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

1. 要使本地更改生效，請在[!DNL Profile Manager,]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***> ，其中配置檔案名稱是資料集配置檔案的名稱或檔案所屬的繼承配置檔案的名稱。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。

## 從資料集配置檔案{#section-677270f93f1648c3a268ca2aea7d4540}中刪除條件

1. 按一下右鍵條件的名稱或與要刪除的條件對應的編號。
1. 按一下&#x200B;**[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>，其中number是與要刪除的條件對應的數字。

## 複製條件{#section-00617bcf2c274f428686b2ec7f2d1db8}

您可以將條件從一個位置複製到同一檔案中的另一個位置，也可以將條件從一個資料集配置檔案複製到另一個資料集配置檔案。

1. 按一下右鍵條件的名稱或與要複製的條件對應的編號，然後按一下&#x200B;**[!UICONTROL Copy]**。
1. 按一下右鍵要放置複製條件的條件的名稱或編號，然後按一下&#x200B;**[!UICONTROL Paste]**。
