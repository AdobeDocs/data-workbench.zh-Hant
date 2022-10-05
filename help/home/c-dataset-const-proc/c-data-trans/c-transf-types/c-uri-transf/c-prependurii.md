---
description: 與AppendURI轉換類似，PrependURI轉換會影響Data Workbench伺服器用於構造URI維的內部欄位。
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 6%

---

# PrependURI{#prependuri}

{{eol}}

與AppendURI轉換類似，PrependURI轉換會影響Data Workbench伺服器用於構造URI維的內部欄位。

此 [!DNL PrependURI] 轉換的工作方式是將標識輸入欄位中的值添加到URI中當前值的前面。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 預設 | 在符合條件且輸入值不可用時使用的預設值。 |  |
| 輸入 | 其值在URI前面的欄位的名稱。 |  |

下面的示例僅將s-dns欄位前置於URI上，將URI維的表示擴展為包括客戶端設備請求的域。

![](assets/cfg_TransformationType_PrependURI.png)

在此範例中，將s-dns欄位預先置於URI中

* [!DNL /modelview.asp&id=login]

會產生下列URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

現在，URI已擴展為包括請求的域。
