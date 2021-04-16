---
description: 與AppendURI轉換類似，PrependURI轉換會影響資料工作台伺服器用來建立URI維度的內部欄位。
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 6%

---

# PrependURI{#prependuri}

與AppendURI轉換類似，PrependURI轉換會影響資料工作台伺服器用來建立URI維度的內部欄位。

[!DNL PrependURI]轉換的運作方式是將已識別輸入欄位中的值新增至URI中目前的值前面。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設 | 如果條件符合且輸入值不可用，則使用的預設值。 |  |
| 輸入 | 值優先於URI的欄位的名稱。 |  |

下面的示例僅將s-dns欄位預置到URI上，將URI維的表示擴展到包括客戶端設備請求的域。

![](assets/cfg_TransformationType_PrependURI.png)

在此範例中，將s-dns欄位預先置於URI

* [!DNL /modelview.asp&id=login]

結果為：

* [!DNL www.adobe.com/modelview.asp?id=login]

現在，URI已擴充為包含請求的域。
