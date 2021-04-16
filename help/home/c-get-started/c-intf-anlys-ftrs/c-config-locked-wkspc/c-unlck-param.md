---
description: 使用者Insight.cfg檔案中的「解除鎖定」參數會指定該使用者是否有權暫時解除鎖定的工作區，以進行編輯。
title: 設定解鎖參數
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# 設定解鎖參數{#set-the-unlock-parameter}

使用者Insight.cfg檔案中的「解除鎖定」參數會指定該使用者是否有權暫時解除鎖定的工作區，以進行編輯。

如果使用者的[!DNL Insight.cfg]檔案中已有「解除鎖定」參數，您可以使用Data Workbench編輯參數。 如果使用者的[!DNL Insight.cfg]檔案中尚未顯示此檔案，您必須使用文字編輯器（例如記事本）將它新增至檔案。

**若要在Insight.cfg [!DNL Unlock] 檔案中設定現有參數**

1. 在工作區中，按一下右鍵&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**。 將開啟[!DNL Insight.cfg]檔案。
1. 對於「解除鎖定」參數，鍵入true或false。 True可讓使用者暫時解除鎖定任何工作區，而False則不會。
1. 要保存配置更改，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL Insight.cfg (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save as Insight.cfg]**。

**若要將Unlock參數新增至Insight.cfg檔案**

1. 導覽至您的Data Workbench安裝目錄，然後使用文字編輯器（如記事本）開啟[!DNL Insight.cfg]檔案。
1. 將Unlock參數添加到檔案的末尾，如以下示例所示：

[!DNL Unlock = bool: false]

1. 將值設為true或false。 True可讓使用者暫時解除鎖定任何工作區，而False則不會。
1. 儲存並關閉檔案。
