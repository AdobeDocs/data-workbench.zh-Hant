---
description: 轉換功能（轉換）可在資料工作台伺服器機器上執行，以匯出記錄來源資料供其他應用程式使用。
solution: Analytics
title: 關於轉換功能
topic: Data workbench
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 關於轉換功能{#about-transformation-functionality}

轉換功能（轉換）可在資料工作台伺服器機器上執行，以匯出記錄來源資料供其他應用程式使用。

[!DNL Transform] 可以讀 [!DNL .vsl][!DNL .vsl] 取檔案、記錄檔、XML檔案和ODBC資料，並將資料匯出為檔案、文字檔或分隔文字檔，供DataWarehouse載入常式、稽核機構或其他目標使用。 資料提取和轉換可以連續地執行或其它排程的。

>[!NOTE]
>
>通常， [!DNL Transform] 是在資料工作台伺服器FSU上設定。 不過，您的實作可能需要在資料工作台伺服器DPU上進行設定。 如需詳細資訊，請聯絡Adobe。

您可以在詳細狀態介面中查 [!DNL Transform] 看記憶體使用資訊。 如需詳細資訊，請參閱資料工作台使用指南的「管 *理介面」一章*。

區段匯出功能提供從Adobe應用程式匯出資料的另一種方式。 [!DNL Transform] 可讓您將未處理的資料匯出至外部目標，但區段匯出功能可讓您從資料集輸出已處理的資料，並要求將匯出的資料定義為資料集中的維度。 如需區段匯出的詳細資訊，請參閱資 *料工作台使用指南*。
