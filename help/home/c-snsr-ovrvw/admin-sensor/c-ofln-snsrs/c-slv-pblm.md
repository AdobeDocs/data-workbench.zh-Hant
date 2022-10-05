---
description: 當Web伺服器因故障而離線時，此解決方案很簡單，需要具有適當權限的Data Workbench使用者開啟Log Processing Mode.cfg檔案，並將感測器的ID（在本例中為WEB2）新增至「離線來源」區段。
title: 解決問題
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 解決問題{#solving-the-problem}

{{eol}}

當Web伺服器因故障而離線時，此解決方案很簡單，需要具有適當權限的Data Workbench使用者開啟Log Processing Mode.cfg檔案，並將感測器的ID（在本例中為WEB2）新增至「離線來源」區段。

檔案的此區段會告訴 [!DNL data workbench server] 不應再指望此來源提供任何資料，因為事實上，它是離線的。

>[!NOTE]
>
>此變更不需要由Adobe顧問執行。 具有適當權限以開啟 [!DNL Log Processing Mode.cfg] 檔案進行此變更。

如果WEB2開始再次傳送資料， [!DNL data workbench server] 使源重新聯機並調整截止時間以反映其上次從其感知的所有源接收資料的時間。 換句話說，傳入系統的新資料優先於 [!DNL Log Processing Mode.cfg file].

如果WEB2再次離線，「截止時間」將再次停止，您需要編輯 [!DNL Log Processing Mode.cfg] 檔案，即使WEB2已列為離線來源亦然。 這是產品設計中符合「截止時間」(As Of Time)定義的一種工具：系統上次擁有所有已知源的資料時。

當您添加更多Web伺服器(WEB4、WEB5、WEB6)時，這些伺服器將開始向 [!DNL data workbench server]，您不需要執行任何動作，就能擁有 [!DNL data workbench server] 認識新的來源。 如上所述，系統只是意識到它應期望從這些新來源獲得資料。
