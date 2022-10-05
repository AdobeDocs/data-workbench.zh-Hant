---
description: 資料集包含檔案可提供彈性的方式來設定資料集。
title: 使用資料集包含檔案
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
exl-id: 94044c85-030c-4912-9546-d4a34b4115e0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 4%

---

# 使用資料集包含檔案{#working-with-dataset-include-files}

{{eol}}

資料集包含檔案可提供彈性的方式來設定資料集。

在每個檔案中，您可以定義任意數量的欄位、轉換或維，並可以根據繼承的檔案來組織包含檔案。 設定資料集時，您可以選擇編輯Adobe應用程式內部設定檔隨附的資料集包含檔案，或為您建立的任何繼承設定檔建立新的資料集包含檔案。

當您編輯內部設定檔的資料集包含檔案的參數，並將更新的檔案儲存至您建立的資料集設定檔或繼承的設定檔時，實際上會覆寫檔案的原始設定。 Adobe建議您在需要微幅變更資料集內容時（例如變更「條件」參數或參數的預設設定），為內部設定檔編輯包含資料集的檔案。 請參閱 [編輯現有的資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). 不過，如果您想要指定要從記錄處理傳遞至轉換、使用轉換更新或建立新欄位，或定義延伸維度，最好建立新的資料集包含檔案。 請參閱 [建立新的資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). 您可以編輯您隨時或隨時看到適合的檔案。
