---
description: 運行Insight Server Replication Service的Target Insight Server電腦必須能夠讀取此重複項伺服器上的日誌檔案。
solution: Insight
title: 為目標電腦配置訪問控制
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 為目標電腦配置訪問控制{#configuring-access-control-for-target-machines}

運行Insight Server Replication Service的Target Insight Server電腦必須能夠讀取此重複項伺服器上的日誌檔案。

使用檔案授予對目標電腦的訪 [!DNL Access Control.cfg] 問權。

**要配置由目標電腦訪問的訪問控制，請執行以下操[!DNL Insight Server]作：**

1. 導覽至您 [!DNL Access Control] 安裝中繼器功能之目錄中的資料夾。

   範例: [!DNL D:\Adobe\Repeater\Access Control]

1. 在文 [!DNL Access Control.cfg] 字編輯器（如記事本）中開啟。
1. 為必須訪問此重複項服 [!DNL Insight Server] 務器上日誌檔案的電腦建立訪問組。 為此訪問組指定類似「複製目標」的名稱。

       下列檔案片段顯示存取群組的外觀。
       
       ```
       . . .
       6 =訪問組：
  成     員=向量：N個項目
 0     =字串：IP:Machine0IPAddress
     1 =字串：IP:Machine1IPAddress
    ...
       N =字串：IP:MachineNIPAddress
     Name = string:複製目標
    只讀訪問=向量：1個項目
 0     =字串：EventDataLocation
 讀     寫存取=向量：0個項目
    。..
      &quot;
   
   1. 在「成員」部分，指定每台電腦的IP地址。
   1. 更新「成員」向量的項目計數，以反映您插入的電腦IP地址數。
   1. 在「只讀訪問」部分，指定複製目標訪問的事件資料的位置。 在路徑規範(/)中使用正斜線。 預設位置是Repeater [!DNL Logs] 機器(/Logs/)上的資料夾。
   1. 更新唯讀存取向量的項目計數，以反映您所插入的位置數。

1. 更新檔案最上方的「存取控制群組」向量中的存取群組數目，以反映新存取群組的新增。

   ```
   Access Control Groups = vector: n items
   ```

1. 儲存檔案。
