---
description: 使用者Insight.cfg檔案中的Unlock參數會指定該使用者是否有權暫時解除鎖定的工作區鎖定以供編輯。
title: 設定解鎖參數
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# 設定解鎖參數{#set-the-unlock-parameter}

使用者Insight.cfg檔案中的Unlock參數會指定該使用者是否有權暫時解除鎖定的工作區鎖定以供編輯。

如果用戶的[!DNL Insight.cfg]檔案中已存在Unlock參數，則可以使用Data Workbench編輯參數。 如果用戶的[!DNL Insight.cfg]檔案中尚未出現該檔案，則必須使用文本編輯器（如記事本）將其添加到檔案中。

**在Insight.cfg檔 [!DNL Unlock] 案中設定現有參數的方式**

1. 在工作區中，按一下右鍵&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**。 將開啟[!DNL Insight.cfg]檔案。
1. 對於Unlock參數，鍵入true或false。 True可讓使用者暫時解除鎖定任何鎖定的工作區，而False則否。
1. 要保存配置更改，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL Insight.cfg (modified)]**，然後按一下&#x200B;**[!UICONTROL Save as Insight.cfg]**。

**將Unlock參數新增至Insight.cfg檔案的方式**

1. 導覽至您的Data Workbench安裝目錄，並使用文字編輯器（如記事本）開啟[!DNL Insight.cfg]檔案。
1. 將Unlock參數添加到檔案的結尾，如下例所示：

[!DNL Unlock = bool: false]

1. 將值設為true或false。 True可讓使用者暫時解除鎖定任何鎖定的工作區，而False則否。
1. 儲存並關閉檔案。
