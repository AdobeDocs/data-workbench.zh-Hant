---
description: 轉換功能（轉換）會在Data Workbench伺服器電腦上執行，以匯出記錄來源資料供其他應用程式使用。
title: 關於轉換功能
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# 關於轉換功能{#about-transformation-functionality}

{{eol}}

轉換功能（轉換）會在Data Workbench伺服器電腦上執行，以匯出記錄來源資料供其他應用程式使用。

[!DNL Transform] 可讀 [!DNL .vsl] 檔案、日誌檔案、XML檔案和ODBC資料，並將資料導出為 [!DNL .vsl] 檔案、文本檔案或分隔文本檔案，這些檔案可用於DataWarehouse載入常式、審計機構或其他目標。 資料提取和轉換可以連續執行，或者以其它預定方式執行。

>[!NOTE]
>
>通常， [!DNL Transform] 是在data workbench伺服器FSU上設定。 不過，您的實作可能需要在Data Workbench伺服器DPU上進行設定。 如需詳細資訊，請聯絡Adobe。

您可以查看 [!DNL Transform] （在詳細狀態介面中）。 如需詳細資訊，請參閱 *Data Workbench使用手冊*.

區段匯出功能提供從Adobe應用程式匯出資料的另一種方式。 [!DNL Transform] 可讓您將未處理的資料匯出至外部目標，但區段匯出功能可讓您從資料集輸出已處理的資料，並要求將匯出的資料定義為資料集中的維度。 如需區段匯出的詳細資訊，請參閱 *Data Workbench使用手冊*.
