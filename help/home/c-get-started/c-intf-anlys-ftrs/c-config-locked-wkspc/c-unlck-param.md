---
description: 使用者Insight.cfg檔案中的「解除鎖定」參數會指定該使用者是否有權暫時解除鎖定的工作區，以進行編輯。
solution: Analytics
title: 設定解鎖參數
topic: Data workbench
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定解鎖參數{#set-the-unlock-parameter}

使用者Insight.cfg檔案中的「解除鎖定」參數會指定該使用者是否有權暫時解除鎖定的工作區，以進行編輯。

如果使用者檔案中已有「解除鎖定」參數，您 [!DNL Insight.cfg] 可以使用「資料工作台」編輯參數。 如果使用者的檔案中尚未顯示此 [!DNL Insight.cfg] 檔案，您必須使用文字編輯器（例如記事本）將它新增至檔案。

**若要在Insight.cfg[!DNL Unlock]檔案中設定現有參數**

1. 在工作區中，以滑鼠右鍵按一下 **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**。 檔案 [!DNL Insight.cfg] 隨即開啟。
1. 對於「解除鎖定」參數，鍵入true或false。 True可讓使用者暫時解除鎖定任何工作區，而False則不會。
1. 要保存配置更改，請按一下右鍵 **[!UICONTROL Insight.cfg (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save as Insight.cfg]**。

**若要將Unlock參數新增至Insight.cfg檔案**

1. 導覽至您的資料工作台安裝目錄，並使 [!DNL Insight.cfg] 用文字編輯器（例如記事本）開啟檔案。
1. 將Unlock參數添加到檔案的末尾，如以下示例所示：

[!DNL Unlock = bool: false]

1. 將值設為true或false。 True可讓使用者暫時解除鎖定任何工作區，而False則不會。
1. 儲存並關閉檔案。

