---
description: 依預設，Insight Server會將其資料集(temp.db)寫入與Insight Server程式檔案相同的磁碟機。
title: 設定資料集 (temp.db) 的位置
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# 設定資料集 (temp.db) 的位置{#configuring-the-location-of-the-dataset-temp-db}

依預設，Insight Server會將其資料集(temp.db)寫入與Insight Server程式檔案相同的磁碟機。

例如，如果在驅動器C上安裝[!DNL Insight Server]，則會將資料集寫入驅動器C。

如果希望[!DNL Insight Server]將資料集維護在不同的驅動器上，或者如果希望收集的資料量需要使用多個驅動器，則必須更新[!DNL Disk Files.cfg]檔案，以指定[!DNL Insight Server]要寫入[!DNL temp.db]檔案的位置。

**配置temp.db的位置**

1. 導覽至[!DNL Insight Server]安裝目錄中的[!DNL Components]資料夾。

   範例：[!DNL C:\Adobe\Server\Components]

1. 在文本編輯器（如記事本）中開啟[!DNL Disk Files.cfg]檔案。

   預設情況下，此檔案在磁碟檔案結構中包含一個條目，如下所示。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. 要更改[!DNL temp.db]的位置，請修改磁碟檔案定義。 以下示例說明如何編輯配置以將[!DNL temp.db]檔案分佈到驅動器C、D和E:

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >請注意，在上述檔案名稱中使用雙反斜線。 在[!DNL Insight Server]配置檔案中，反斜線字元是轉義字元。 它用於在文本中表示特殊的控制序列（例如\t用於定位字元）。 若要表示實際的反斜線字元，您必須輸入兩次反斜線（例如\\），才能覆寫逸出函式。 這僅適用於在文字編輯器（如記事本）中編輯組態檔時。
