---
description: 您可以從「Data Workbench用戶端」的「明細表」視覺化中輕鬆建立「區段匯出」定義。
title: 區段匯出
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# 區段匯出{#segment-export}

您可以從「Data Workbench用戶端」的「明細表」視覺化中輕鬆建立「區段匯出」定義。

此外，[!DNL Segment Exports]會自動將其結果結合至單一伺服器，而不是在每個DPU上產生部分結果，而您必須使用外部程式來結合。 您可以建立區段匯出檔案，將它儲存至[!DNL Profile Manager]，然後將輸出檔案上傳至您選擇的伺服器。

**若要設定區段匯出伺服器**

[!DNL Segment Export]功能會在區段匯出伺服器上建立單一輸出檔案，而不是在每個DPU上建立個別的輸出檔案。 區段匯出伺服器通常設定為在FSU上執行。

在[!DNL Profile Manager]的「資料集」目錄中，開啟「工作站」中的[!DNL Segment Export.cfg]，並指定您伺服器的位址。 （您的地址可以是IP或完全限定的域名。）:

![](assets/segment_export_cfg.png)

這是接收段導出結果的Data Workbench伺服器的IP。 這是一次性設定。 如果[!DNL Segment Export.cfg]不存在，則不會運行導出。

**要配置導出目錄**

為安全起見，在區段匯出後執行的可執行檔或批次檔案必須位於區段匯出伺服器的可設定Scripts\目錄中。

[!DNL .part]和最終輸出必須駐留在可配置的導出目錄中。 要運行的命令存在於命令和命令參數中。 命令參數中%file%的實例將替換為輸出檔案的路徑。

>[!NOTE]
>
>對於Data Workbench5.4,\Exports資料夾將自動建立。 在5.4版之前設定的先前導出目錄要求在每個段導出的檔案名前加上導出\前置詞。 現在新增此首碼是多餘的。

1. 在[!DNL Segment Exports]的目標伺服器上的[!DNL Communications.cfg]中，將SegmentExportServer添加到伺服器清單中。 （以紅色顯示的範例）。

   ![](assets/communications_cfg_example.png)

   導出目錄：指定放置[!DNL .part]和輸出檔案的位置。 此目錄可以是共用目錄。

   指令碼目錄：指定從中運行所有執行檔或批處理檔案的目錄。

1. [!DNL Access Control.cfg]，在同一伺服器上，將對URI /SegmentExportServer/的讀寫訪問添加到群集伺服器訪問組：

   ![](assets/accesscontrol_cfg_example.png)

1. 更改[!DNL .export]檔案：

   ![](assets/segment_export_query_example.png)

1. 對於每個配置檔案，[!DNL Segment Export.cfg]位於Dataset\目錄中，包含以下內容：

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. 確保導出目錄和指令碼目錄中引用的目錄存在。

   只有Scripts目錄中的執行檔和批處理檔案才能作為段導出的命令運行。

**若要建立區段匯出檔案**

1. 在工作區中，建立顯示資料子集（視覺化>詳細資料表格）的詳細資料表格，並新增屬性。
1. 視需要在工作區中進行選取。 （所有選擇或篩選器都會套用至匯出。）

   ![](assets/create_segment_export_file.png)

1. 在「明細表」標題中，按一下右鍵並選擇&#x200B;**[!UICONTROL Create Segment Export File]**。
1. 在[!DNL Save as]中，鍵入[!DNL .export]檔案的名稱。
1. 在[!DNL .export]檔案中，視需要設定參數。

   工作區中的任何選擇或篩選器都會合併到導出檔案中。

1. 保存[!DNL .export]檔案。

   儲存的檔案會顯示在[!DNL Profile Manager]中，供您儲存至伺服器。 將檔案保存到伺服器時，導出開始。
