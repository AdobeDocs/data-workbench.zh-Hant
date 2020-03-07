---
description: 與AppendURI轉換類似，PrependURI轉換會影響資料工作台伺服器用來建立URI維度的內部欄位。
solution: Analytics
title: 附加URI前
topic: Data workbench
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 附加URI前{#prependuri}

與AppendURI轉換類似，PrependURI轉換會影響資料工作台伺服器用來建立URI維度的內部欄位。

轉 [!DNL PrependURI] 換的運作方式是將已識別輸入欄位中的值新增至URI中目前的值前面。

| 參數 | 說明 | 預設值 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 意見 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設值 | 如果條件符合且輸入值不可用，則使用的預設值。 |  |
| 輸入 | 值優先於URI的欄位的名稱。 |  |

下面的示例僅將s-dns欄位預置到URI上，將URI維的表示擴展到包括客戶端設備請求的域。

![](assets/cfg_TransformationType_PrependURI.png)

在此範例中，將s-dns欄位預先置於URI

* [!DNL /modelview.asp&id=login]

結果為：

* [!DNL www.adobe.com/modelview.asp?id=login]

現在，URI已擴充為包含請求的域。
