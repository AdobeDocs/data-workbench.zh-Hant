---
description: 依預設，Insight Server會將其資料集(temp.db)寫入與Insight Server程式檔案相同的磁碟機。
solution: Analytics
title: 設定資料集 (temp.db) 的位置
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---


# 設定資料集 (temp.db) 的位置{#configuring-the-location-of-the-dataset-temp-db}

依預設，Insight Server會將其資料集(temp.db)寫入與Insight Server程式檔案相同的磁碟機。

例如，如果您安裝在 [!DNL Insight Server] 驅動器C上，它會將資料集寫入驅動器C。

如果您想 [!DNL Insight Server] 要將資料集維護在不同的磁碟機上，或您預期要收集的資料量需要使用多個磁碟機，您必須更新檔案，以指定您要將檔案 [!DNL Disk Files.cfg] 寫入的 [!DNL Insight Server][!DNL temp.db] 位置。

**配置temp.db的位置**

1. 導覽至您 [!DNL Components] 所安裝目錄中的資料夾 [!DNL Insight Server]。

   範例：[!DNL C:\Adobe\Server\Components]

1. 在文本編 [!DNL Disk Files.cfg] 輯器（如記事本）中開啟檔案。

   預設情況下，此檔案在磁碟檔案結構中包含一個條目，如下所示。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. 要更改的位置， [!DNL temp.db]請修改磁碟檔案定義。 以下示例說明如何編輯配置以跨驅動器C、 [!DNL temp.db] D和E分佈檔案：

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
   >請注意，在上述檔案名稱中使用雙反斜線。 在配 [!DNL Insight Server] 置檔案中，反斜線字元是轉義字元。 它用於在文本中表示特殊的控制序列（例如，\t用於制表符字元）。 若要表示實際反斜線字元，您必須輸入反斜線兩次（例如\\）以覆寫逸出函式。 僅當在文本編輯器（如記事本）中編輯配置檔案時，才適用。

