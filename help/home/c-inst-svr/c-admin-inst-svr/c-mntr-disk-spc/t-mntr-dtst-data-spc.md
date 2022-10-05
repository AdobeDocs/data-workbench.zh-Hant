---
description: 資料集監控和新增資料集資料儲存位置的相關資訊。
title: 監控資料集資料空間
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# 監控資料集資料空間{#monitoring-dataset-data-space}

{{eol}}

資料集監控和新增資料集資料儲存位置的相關資訊。

**建議頻率：** 每5-10分鐘

依預設， [!DNL Insight Server] 將其資料集寫入 [!DNL temp.db] 檔案與 [!DNL Insight Server] 程式檔案。 每個資料集的資料量 [!DNL Insight Server] 電腦限制為下列情況之一：

* 5億（5億）條資料輸入到該資料集的記錄
* 儲存500 GB的資料集資料
* 每個根層級維度儲存一(1)MB的資料集資料（例如，每位訪客5,000筆記錄，每筆記錄平均200個位元組）

如果您想要 [!DNL Insight Server] 要在不同的驅動器上維護資料集，或者如果要收集的資料量需要使用多個驅動器，則必須更新磁碟檔案配置檔案( [!DNL Disk Files.cfg])，指定您想要的位置 [!DNL Insight Server] 寫 [!DNL temp.db] 檔案。 此 [!DNL Disk Files.cfg] 檔案會列出磁碟檔案（字串向量），並指定所使用資料集資料的位置 [!DNL Insight Server] 進行重新處理和操作時。 每個物理驅動器通常有一個檔案。

>[!NOTE]
>
>內容 [!DNL Disk Files.cfg] 安裝時可能修改了檔案 [!DNL Insight Server]. 如需詳細資訊，請參閱 [設定資料集(temp.db)的位置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**為資料集資料儲存新增位置的方式**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。
1. 以滑鼠右鍵按一下 [!DNL Insight Server] 要配置，請按一下 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL Disk Files.cfg] 檔案位於此目錄中。
1. 以滑鼠右鍵按一下 *伺服器名稱* 欄 [!DNL Disk Files.cfg] 按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Disk Files.cfg].
1. 在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 在 [!DNL Disk Files.cfg] 按一下 **[!UICONTROL component]** 來檢視其內容。

   ![步驟資訊](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >預設情況下， Detect Disk Crobution參數設定為true。 磁碟快取大小(MB)參數控制 [!DNL Insight Server] 用於提高磁碟訪問速度，預設為128。 在更改其中一個參數之前，請與Adobe聯繫。

1. 要更改 [!DNL Insight Server] 電腦，按一下右鍵 **[!UICONTROL Disk Files]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   要刪除磁碟檔案，請按一下右鍵磁碟檔案號，然後按一下 **[!UICONTROL Remove]**.

1. 對於新磁碟檔案，輸入要使用的檔案的目錄和名稱 [!DNL Insight Server] 進行重新處理和操作時。

   ![步驟資訊](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >預設情況下， Detect Disk Crobution參數設定為true。 磁碟快取大小(MB)參數控制 [!DNL Insight Server] 用於提高磁碟訪問速度，預設為128。 在更改其中一個參數之前，請與Adobe聯繫。

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄和選取 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
