---
description: 新增、移除或複製條件的相關資訊。
title: 使用條件
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# 使用條件{#working-with-conditions}

{{eol}}

新增、移除或複製條件的相關資訊。

* [將條件新增至資料集組態檔的方式](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [從資料集組態檔中移除條件的方式](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [複製條件的方式](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## 將條件新增至資料集組態檔的方式 {#section-3e2a34db047b462585502f69722f6511}

1. 使用資料集設定檔時，請使用 [!DNL Profile Manager] 開啟要編輯的資料集組態檔。

   * 若要開啟 [!DNL Log Processing.cfg] 檔案，請參閱 [編輯記錄處理組態檔](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * 若要開啟 [!DNL Transformation.cfg] 檔案，請參閱 [編輯轉換組態檔](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * 若要開啟 [!DNL Dataset Include] 檔案，請參閱 [資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. 在資料集組態檔中，找出您要定義的記錄項目條件或條件參數。
1. 以滑鼠右鍵按一下參數，然後按一下 **[!UICONTROL Add new]**. 選擇下列其中一種條件類型：

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. 視需要編輯條件的參數。 如需各條件參數的說明，請參閱本附錄的適當章節。
1. 若要儲存變更，請按一下滑鼠右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

1. 若要讓本機所做的變更生效，請在 [!DNL Profile Manager,] 按一下右鍵中檔案的複選標籤 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>，其中profile name是資料集設定檔的名稱或檔案所屬的繼承設定檔的名稱。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

## 從資料集組態檔中移除條件的方式 {#section-677270f93f1648c3a268ca2aea7d4540}

1. 以滑鼠右鍵按一下條件的名稱，或與您要移除之條件相對應的數字。
1. 按一下 **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>，其中number是與您要移除之條件相對應的數字。

## 複製條件的方式 {#section-00617bcf2c274f428686b2ec7f2d1db8}

您可以將條件從一個位置複製到同一檔案中的另一個位置，或是將條件從一個資料集組態檔複製到另一個位置。

1. 以滑鼠右鍵按一下條件的名稱或與您要複製之條件相對應的編號，然後按一下 **[!UICONTROL Copy]**.
1. 以滑鼠右鍵按一下要放置複製條件之下的條件名稱或編號，然後按一下 **[!UICONTROL Paste]**.
