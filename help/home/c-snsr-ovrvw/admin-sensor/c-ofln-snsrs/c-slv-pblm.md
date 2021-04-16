---
description: 當Web伺服器因故障而離線時，解決方案很簡單，需要具有適當權限的Data Workbench用戶開啟Log Processing Mode.cfg檔案，並將感測器ID（在我們的示例中，WEB2）添加到「Offline Sources」（離線源）部分。
title: 解決問題
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 解決問題{#solving-the-problem}

當Web伺服器因故障而離線時，解決方案很簡單，需要具有適當權限的Data Workbench用戶開啟Log Processing Mode.cfg檔案，並將感測器ID（在我們的示例中，WEB2）添加到「Offline Sources」（離線源）部分。

該檔案的此部分告訴[!DNL data workbench server]它不應再期望此源中的任何資料，因為它實際上處於離線狀態。

>[!NOTE]
>
>無需由Adobe顧問執行此更改。 任何擁有開啟[!DNL Log Processing Mode.cfg]檔案之適當權限的人都可進行此變更。

如果WEB2開始再次發送資料，[!DNL data workbench server]將源重新聯機並調整截止時間，以反映其上次從其感知的所有源接收資料的時間。 換言之，進入系統的新資料優先於[!DNL Log Processing Mode.cfg file]中寫入的資料。

如果WEB2再次離線，「截止時間」將再次停止，而且您需要再次編輯[!DNL Log Processing Mode.cfg]檔案，即使該檔案可能已將WEB2列為離線源。 這是符合「截止時間」(As Of Time)定義的產品設計的偽品：上次系統擁有所有已知來源的資料時。

當您新增更多Web伺服器(WEB4、WEB5、WEB6)，而他們開始傳送資料至[!DNL data workbench server]時，您不需要執行任何動作，讓[!DNL data workbench server]識別新來源。 如上所述，系統只是意識到應期待這些新來源的資料。
