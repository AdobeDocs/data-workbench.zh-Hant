---
description: 當Web伺服器因故障而離線時，解決方案很簡單，需要具有適當權限的資料工作台用戶才能開啟Log Processing Mode.cfg檔案，並將感測器ID（在我們的示例中，WEB2）添加到「離線源」部分。
solution: Insight
title: 解決問題
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 解決問題{#solving-the-problem}

當Web伺服器因故障而離線時，解決方案很簡單，需要具有適當權限的資料工作台用戶才能開啟Log Processing Mode.cfg檔案，並將感測器ID（在我們的示例中，WEB2）添加到「離線源」部分。

檔案的這一區段會告 [!DNL data workbench server] 訴您，它不應再期待來自此來源的任何資料，因為它實際上是離線的。

>[!NOTE]
>
>此變更不需要由Adobe顧問執行。 任何具有開啟檔案之適當權限 [!DNL Log Processing Mode.cfg] 的人都可進行此變更。

如果WEB2開始再次傳送資料，則 [!DNL data workbench server] 會將來源重新連線，並調整截止時間，以反映其上次從所有來源接收資料的時間。 換言之，傳入系統的新資料優先於寫入的資料 [!DNL Log Processing Mode.cfg file]。

如果WEB2再次離線，「截止時間」將再次停止，而您需要再次編輯該檔案，即使該檔案可能已將 [!DNL Log Processing Mode.cfg] WEB2列為離線源。 這是符合「截止時間」(As Of Time)定義的產品設計的偽品：上次系統擁有所有已知來源的資料時。

當您新增更多Web伺服器(WEB4、WEB5、WEB6)，而他們開始傳送資料至時 [!DNL data workbench server]，您不需要執行任何動作，就能辨識 [!DNL data workbench server] 新來源。 如上所述，系統只是意識到應期待這些新來源的資料。
