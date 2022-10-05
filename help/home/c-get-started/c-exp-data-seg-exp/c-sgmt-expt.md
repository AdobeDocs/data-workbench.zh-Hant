---
description: 您可以從Data Workbench用戶端的「詳細資料表」視覺效果輕鬆建立「區段匯出」定義。
title: 區段匯出
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# 區段匯出{#segment-export}

{{eol}}

您可以從Data Workbench用戶端的「詳細資料表」視覺效果輕鬆建立「區段匯出」定義。

此外， [!DNL Segment Exports] 自動將其結果合併至單一伺服器，而非在您必須使用外部程式合併的每個DPU上產生部分結果。 您可以建立區段匯出檔案，並儲存至 [!DNL Profile Manager]，並將輸出檔案上傳至您所選擇的伺服器。

**若要設定區段匯出伺服器**

此 [!DNL Segment Export] 功能會在區段匯出伺服器上建立單一輸出檔案，而非在每個DPU上建立個別的輸出檔案。 區段匯出伺服器通常設定為在FSU上執行。

在 [!DNL Profile Manager]，開啟 [!DNL Segment Export.cfg] 在工作站中，並指定您伺服器的位址。 （您的地址可以是IP或完全限定的域名。）:

![](assets/segment_export_cfg.png)

這是接收Data Workbench匯出結果之區段伺服器的IP。 這是一次性設定。 若 [!DNL Segment Export.cfg] 不存在，則不會執行匯出。

**配置導出目錄**

為了安全起見，在區段匯出後執行的執行檔或批次檔案必須位於區段匯出伺服器的可設定指令碼\目錄中。

此 [!DNL .part] 而最終輸出必須位於可配置的導出目錄中。 要運行的命令存在於命令和命令參數中。 命令參數中%file%的實例將替換為輸出檔案的路徑。

>[!NOTE]
>
>新建到Data Workbench5.4時，\Exports資料夾將自動建立。 在5.4版之前設定的先前匯出目錄，在每個區段匯出的檔案名稱前面都需要Exports\前置詞。 現在不需要添加此前置詞。

1. 在 [!DNL Communications.cfg] 在 [!DNL Segment Exports]，將SegmentExportServer新增至伺服器清單。 （以紅色顯示的範例）。

   ![](assets/communications_cfg_example.png)

   導出目錄：指定放置位置 [!DNL .part] 和輸出檔案。 這可以是共用目錄。

   指令碼目錄：指定運行所有執行檔或批處理檔案的目錄。

1. [!DNL Access Control.cfg]，在同一伺服器上，將對URI /SegmentExportServer/的讀寫訪問添加到群集伺服器訪問組：

   ![](assets/accesscontrol_cfg_example.png)

1. 變更您的 [!DNL .export] 檔案：

   ![](assets/segment_export_query_example.png)

1. 對於每個設定檔， [!DNL Segment Export.cfg] 位於資料集\目錄中，其內容如下：

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. 確保導出目錄和指令碼目錄中引用的目錄存在。

   只有指令碼目錄中的執行檔和批處理檔案才能作為段導出的命令運行。

**若要建立區段匯出檔案**

1. 在工作區中，建立顯示資料子集的「詳細資料表」（「視覺效果」>「詳細資料表」）並新增屬性。
1. 如果需要，在工作區中進行選取。 （任何選擇或篩選器都會套用至匯出。）

   ![](assets/create_segment_export_file.png)

1. 在「詳細資料表」標題中，按一下右鍵並選擇 **[!UICONTROL Create Segment Export File]**.
1. 在 [!DNL Save as]，輸入名稱 [!DNL .export] 檔案。
1. 在 [!DNL .export] ，視需要設定參數。

   工作區中的任何選取項目或篩選器都會併入匯出檔案中。

1. 儲存 [!DNL .export] 檔案。

   儲存的檔案會顯示在 [!DNL Profile Manager] 儲存到伺服器。 將檔案保存到伺服器時，導出將開始。
