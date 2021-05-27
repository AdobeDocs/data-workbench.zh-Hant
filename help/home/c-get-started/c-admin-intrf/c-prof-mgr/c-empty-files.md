---
description: 如果您沒有從配置檔案刪除檔案的權限，或者您不想永久刪除檔案，則可以使用空（零位元組）檔案來隱藏檔案。
title: 清空檔案 (零位元組) 以隱藏檔案
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---

# 清空檔案 (零位元組) 以隱藏檔案{#hide-a-file-by-emptying-it-zero-byte}

如果您沒有從配置檔案刪除檔案的權限，或者您不想永久刪除檔案，則可以使用空（零位元組）檔案來隱藏檔案。

在[!DNL Profile Manager]中，列中的連字型大小(-)（而不是勾號）標識零位元組檔案。

![](assets/vis_ProfMgr_Zero-byte.png)

與隱藏檔案的其他方法（如[!DNL order.txt]、Show參數和Hidden參數）不同，Data Workbench將零位元組檔案視為不存在。 例如，如果您將視覺效果或量度定義中使用的維度設為零位元組，Data Workbench會分別針對該視覺效果或量度產生錯誤。

由於下列原因，此功能很實用，包括您想執行下列動作時：

* **讓檔案在Data Workbench** 中無法使用，而不需要刪除檔案所需的設定檔權限。
* **將量度、維度或篩選器移** 動至其他位置，而不需要從原始位置刪除檔案所需的設定檔權限。
* **隱藏菜單項。** 例如，設定 [!DNL Base] 檔在檔 [!DNL Metric Legend] 案中已定 [!DNL Metric.vw] 義。假設您的公司已建立三個量度圖例，您要在「新增圖例>量度」子功能表中顯示。 您可以對[!DNL Base]配置檔案[!DNL Metric.vw]檔案執行零位元組操作，以便僅顯示新子菜單和三個新度量圖例。

**隱藏檔案**

1. 在[!DNL Profile Manager]中，開啟必要的資料夾和子資料夾，以找到要零位元組的檔案。
1. 按一下右鍵檔案名稱旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。
1. 開啟本機檔案並刪除其內容。
1. 儲存並關閉檔案。
