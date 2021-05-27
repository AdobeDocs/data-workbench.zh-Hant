---
description: 運行Insight Server複製服務的Target Insight Server電腦必須能夠讀取此中繼器伺服器上的記錄檔。
title: 為目標機器設定存取控制
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# 為目標機器設定存取控制{#configuring-access-control-for-target-machines}

運行Insight Server複製服務的Target Insight Server電腦必須能夠讀取此中繼器伺服器上的記錄檔。

使用[!DNL Access Control.cfg]檔案授予對目標電腦的訪問權。

**配置訪問控制以供目標電腦訪 [!DNL Insight Server] 問**

1. 導覽至安裝中繼器功能之目錄的[!DNL Access Control]資料夾。

   範例：[!DNL D:\Adobe\Repeater\Access Control]

1. 在文本編輯器（如記事本）中開啟[!DNL Access Control.cfg]。
1. 為必須訪問此中繼器伺服器上日誌檔案的[!DNL Insight Server]電腦建立訪問組。 為此訪問組命名「複製目標」。

   下列檔案片段顯示存取群組的外觀。

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. 在「成員」部分，指定每台電腦的IP地址。
   1. 更新成員向量的項目計數，以反映插入的電腦IP地址數。
   1. 在「只讀訪問」部分，指定複製目標訪問的事件資料的位置。 在路徑規範(/)中使用正斜線。 預設位置是中繼器電腦(/Logs/)上的[!DNL Logs]資料夾。
   1. 更新唯讀存取向量的項目計數，以反映您插入的位置數。

1. 更新檔案頂部「訪問控制組」向量中的訪問組數，以反映新訪問組的添加。

   ```
   Access Control Groups = vector: n items
   ```

1. 儲存檔案。
