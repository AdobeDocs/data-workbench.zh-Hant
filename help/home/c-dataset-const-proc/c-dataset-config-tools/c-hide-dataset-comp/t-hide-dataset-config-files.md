---
description: 如果您不想從內部或其他繼承的配置檔案繼承配置檔案（即，您希望在資料集構建過程中忽略檔案中的說明），但不想修改檔案，則可以建立同名的空（零位元組）檔案，並將該檔案儲存在另一個配置檔案中。
solution: Analytics
title: 隱藏資料集設定檔案
topic: Data workbench
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 隱藏資料集設定檔案{#hiding-dataset-configuration-files}

如果您不想從內部或其他繼承的配置檔案繼承配置檔案（即，您希望在資料集構建過程中忽略檔案中的說明），但不想修改檔案，則可以建立同名的空（零位元組）檔案，並將該檔案儲存在另一個配置檔案中。

**對資料集配置檔案進行零位元組操作**

1. 在中 [!DNL Profile Manager]，開啟必要的資料夾和子資料夾以找到要零位元組的檔案。
1. 按一下右鍵檔案名稱旁的複選標籤，然後按一下 **[!UICONTROL Make Local]**。
1. 在文本編輯器（如記事本）中開啟本地檔案並刪除其內容。
1. 儲存並關閉檔案。
1. 在中， [!DNL Profile Manager]將零位元組檔案保存到原始檔案所在配置檔案右側的配置檔案中。 （您希望零位元組檔案優先於原始檔案。）

   在中 [!DNL Profile Manager]，欄中的連字型大小(-)（而非複選標籤）會識別零位元組檔案，如下例所示。

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

當您重新處理資料集時，資料集不包含原始檔案所定義的資料集元件。

>[!NOTE]
>
>如果設定檔案的零位元組定義了在視覺化或度量定義中使用的擴充維度，資料工作台會分別針對該視覺化或度量產生錯誤。

您也可以使用零位元組檔案，將量度、維度或篩選移至描述檔中的其他位置，或隱藏功能表項目。 For information, see the *Data Workbench User Guide*.
