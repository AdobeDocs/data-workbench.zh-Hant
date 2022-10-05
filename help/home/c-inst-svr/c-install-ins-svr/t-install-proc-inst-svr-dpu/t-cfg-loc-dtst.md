---
description: 依預設，Insight Server會將其資料集(temp.db)寫入與Insight Server程式檔案相同的磁碟機。
title: 設定資料集 (temp.db) 的位置
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# 設定資料集 (temp.db) 的位置{#configuring-the-location-of-the-dataset-temp-db}

{{eol}}

依預設，Insight Server會將其資料集(temp.db)寫入與Insight Server程式檔案相同的磁碟機。

例如，若您安裝 [!DNL Insight Server] 在C驅動器上，資料集寫入C驅動器。

如果您想要 [!DNL Insight Server] 若要在不同的磁碟上維護資料集，或如果您要收集的資料量需要使用多個磁碟，則必須更新 [!DNL Disk Files.cfg] 要指定位置的檔案 [!DNL Insight Server] 寫 [!DNL temp.db] 檔案。

**配置temp.db的位置**

1. 導覽至 [!DNL Components] 資料夾（位於安裝的目錄中） [!DNL Insight Server].

   範例：[!DNL C:\Adobe\Server\Components]

1. 開啟 [!DNL Disk Files.cfg] 檔案（如記事本）。

   預設情況下，此檔案在磁碟檔案結構中包含一個條目，如下所示。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. 若要變更 [!DNL temp.db]，修改磁碟檔案定義。 下列範例說明如何編輯設定以分散 [!DNL temp.db] 檔案跨驅動器C、D和E:

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
   >請注意，在上述檔案名稱中使用雙反斜線。 在 [!DNL Insight Server] 設定檔中，反斜線字元為逸出字元。 它用於在文本中表示特殊的控制序列（例如\t用於定位字元）。 若要表示實際的反斜線字元，您必須輸入兩次反斜線（例如\\），才能覆寫逸出函式。 這僅適用於在文字編輯器（如記事本）中編輯組態檔時。
