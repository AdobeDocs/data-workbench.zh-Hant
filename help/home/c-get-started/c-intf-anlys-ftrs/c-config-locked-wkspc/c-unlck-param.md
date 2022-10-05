---
description: 使用者Insight.cfg檔案中的Unlock參數會指定該使用者是否有權暫時解除鎖定的工作區鎖定以供編輯。
title: 設定解鎖參數
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# 設定解鎖參數{#set-the-unlock-parameter}

{{eol}}

使用者Insight.cfg檔案中的Unlock參數會指定該使用者是否有權暫時解除鎖定的工作區鎖定以供編輯。

如果使用者的 [!DNL Insight.cfg] 檔案中，可使用Data Workbench編輯參數。 若尚未出現在使用者的 [!DNL Insight.cfg] 檔案時，必須使用文本編輯器（如記事本）將其添加到檔案中。

**若要設定現有 [!DNL Unlock] 參數**

1. 在工作區中，按一下滑鼠右鍵 **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. 此 [!DNL Insight.cfg] 檔案開啟。
1. 對於Unlock參數，鍵入true或false。 True可讓使用者暫時解除鎖定任何鎖定的工作區，而False則否。
1. 若要儲存設定變更，請按一下滑鼠右鍵 **[!UICONTROL Insight.cfg (modified)]** 在視窗頂端按一下 **[!UICONTROL Save as Insight.cfg]**.

**將Unlock參數新增至Insight.cfg檔案的方式**

1. 導覽至您的Data Workbench安裝目錄，然後開啟 [!DNL Insight.cfg] 檔案（如記事本）。
1. 將Unlock參數添加到檔案的結尾，如下例所示：

[!DNL Unlock = bool: false]

1. 將值設為true或false。 True可讓使用者暫時解除鎖定任何鎖定的工作區，而False則否。
1. 儲存並關閉檔案。
