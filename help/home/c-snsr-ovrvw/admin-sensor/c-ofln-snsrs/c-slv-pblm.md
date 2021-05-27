---
description: 當Web伺服器因故障而離線時，此解決方案很簡單，需要具有適當權限的Data Workbench使用者開啟Log Processing Mode.cfg檔案，並將感測器的ID（在本例中為WEB2）新增至「離線來源」區段。
title: 解決問題
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 解決問題{#solving-the-problem}

當Web伺服器因故障而離線時，此解決方案很簡單，需要具有適當權限的Data Workbench使用者開啟Log Processing Mode.cfg檔案，並將感測器的ID（在本例中為WEB2）新增至「離線來源」區段。

檔案的此區段會告訴[!DNL data workbench server]，它不應再期望來自此來源的任何資料，因為實際上它是離線的。

>[!NOTE]
>
>此變更不需要由Adobe顧問執行。 任何具有開啟[!DNL Log Processing Mode.cfg]檔案的適當權限的人都可以進行此更改。

如果WEB2開始再次發送資料， [!DNL data workbench server]將源重新聯機並調整截止時間以反映上次從它感知的所有源接收資料的時間。 換言之，進入系統的新資料優先於[!DNL Log Processing Mode.cfg file]中寫入的資料。

如果WEB2再次離線，「截止時間」將再次停止，並且您需要再次編輯[!DNL Log Processing Mode.cfg]檔案，即使它可能已將WEB2列為離線源。 這是產品設計中符合「截止時間」(As Of Time)定義的一種工具：系統上次擁有所有已知源的資料時。

當您添加更多Web伺服器(WEB4、WEB5、WEB6)，並且它們開始向[!DNL data workbench server]發送資料時，您無需執行任何操作，使[!DNL data workbench server]能夠識別新源。 如上所述，系統只是意識到它應期望從這些新來源獲得資料。
