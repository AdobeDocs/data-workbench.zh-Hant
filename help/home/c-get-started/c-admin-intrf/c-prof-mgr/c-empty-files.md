---
description: 如果您沒有從描述檔刪除檔案的權限，或不想永久刪除檔案，則可使用空（零位元組）檔案來隱藏檔案。
title: 清空檔案 (零位元組) 以隱藏檔案
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---

# 清空檔案 (零位元組) 以隱藏檔案{#hide-a-file-by-emptying-it-zero-byte}

如果您沒有從描述檔刪除檔案的權限，或不想永久刪除檔案，則可使用空（零位元組）檔案來隱藏檔案。

在[!DNL Profile Manager]中，欄中的連字型大小(-)（而非勾號）會識別零位元組檔案。

![](assets/vis_ProfMgr_Zero-byte.png)

與其他隱藏檔案的方法（例如[!DNL order.txt]、Show參數和Hidden參數）不同，Data Workbench將零位元件視為不存在。 例如，如果您對已用於視覺化或度量定義的維度設定零位元組，Data Workbench會分別針對該視覺化或度量產生錯誤。

此功能有許多用處，包括您要執行下列作業時：

* **讓檔案在** Data Workbench中無法使用，而不需要刪除檔案所需的設定檔權限。
* **將量度、維度或篩選器移** 動至其他位置，而不需具備從原始位置刪除檔案所需的描述檔權限。
* **隱藏功能表項目。** 例如，描述檔 [!DNL Base] 在檔案中 [!DNL Metric Legend] 有定義 [!DNL Metric.vw] 的。假設您的公司已建立三個您要顯示在「新增圖例>量度」子功能表上的量度圖例。 您可以將[!DNL Base]描述檔[!DNL Metric.vw]檔案設為零位元組，如此只會顯示您的新子功能表和三個新的度量圖例。

**隱藏檔案**

1. 在[!DNL Profile Manager]中，開啟必要的檔案夾和子檔案夾，以找出您要設定零位元組的檔案。
1. 按一下右鍵檔案名稱旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。
1. 開啟本機檔案並刪除其內容。
1. 儲存並關閉檔案。
