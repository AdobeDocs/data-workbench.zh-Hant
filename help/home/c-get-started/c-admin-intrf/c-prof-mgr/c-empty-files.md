---
description: 如果您沒有從描述檔刪除檔案的權限，或不想永久刪除檔案，則可使用空（零位元組）檔案來隱藏檔案。
solution: Analytics
title: 清空檔案（零位元組）以隱藏檔案
topic: Data workbench
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 清空檔案（零位元組）以隱藏檔案{#hide-a-file-by-emptying-it-zero-byte}

如果您沒有從描述檔刪除檔案的權限，或不想永久刪除檔案，則可使用空（零位元組）檔案來隱藏檔案。

在中 [!DNL Profile Manager]，列中的連字型大小(-)而不是複選標籤標識零位元組檔案。

![](assets/vis_ProfMgr_Zero-byte.png)

與其他隱藏檔案的方法(例如 [!DNL order.txt]「顯示」參數和「隱藏」參數)不同，資料工作台將零位元件視為不存在。 例如，如果您將已用於視覺化或量度定義的維度設定為零位元組，資料工作台會分別針對該視覺化或量度產生錯誤。

此功能有許多用處，包括您要執行下列作業時：

* **在資料工作台中** ，讓檔案無法使用，而不需具備刪除檔案所需的設定檔權限。
* **將量度、維度或篩選移至其他位置** ，而不需具備從原始位置刪除檔案所需的描述檔權限。
* **隱藏功能表項目。** 例如，描述檔 [!DNL Base] 在檔案中 [!DNL Metric Legend] 有定義 [!DNL Metric.vw] 的。 假設您的公司已建立三個您要顯示在「新增圖例>量度」子功能表上的量度圖例。 您可以將描述檔檔案設 [!DNL Base] 為零位 [!DNL Metric.vw] 元組，以便只顯示您的新子功能表和三個新度量圖例。

**隱藏檔案**

1. 在中 [!DNL Profile Manager]，開啟必要的資料夾和子資料夾以找到要零位元組的檔案。
1. 按一下右鍵檔案名稱旁的複選標籤，然後按一下 **[!UICONTROL Make Local]**。
1. 開啟本機檔案並刪除其內容。
1. 儲存並關閉檔案。

