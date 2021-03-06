---
description: 資料集監控和新增資料集資料儲存位置的相關資訊。
title: 監控資料集資料空間
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# 監控資料集資料空間{#monitoring-dataset-data-space}

資料集監控和新增資料集資料儲存位置的相關資訊。

**建議頻率：** 每5-10分鐘

預設情況下， [!DNL Insight Server]將其資料集寫入資料處理單元上與[!DNL Insight Server]程式檔案位於同一驅動器上的[!DNL temp.db]檔案。 每部[!DNL Insight Server]電腦的資料集資料量限於下列項目，以先發生者為準：

* 5億（5億）條資料輸入到該資料集的記錄
* 儲存500 GB的資料集資料
* 每個根層級維度儲存一(1)MB的資料集資料（例如，每位訪客5,000筆記錄，每筆記錄平均200個位元組）

如果希望[!DNL Insight Server]將資料集維護在不同的驅動器上，或者如果希望收集的資料量需要使用多個驅動器，則必須更新磁碟檔案配置檔案([!DNL Disk Files.cfg])，以指定[!DNL Insight Server]要寫入[!DNL temp.db]檔案的位置。 [!DNL Disk Files.cfg]檔案列出磁碟檔案（字串向量），並指定[!DNL Insight Server]在重新處理和操作期間使用的資料集資料的位置。 每個物理驅動器通常有一個檔案。

>[!NOTE]
>
>安裝[!DNL Insight Server]時，可能已修改[!DNL Disk Files.cfg]檔案的內容。 如需詳細資訊，請參閱[設定資料集(temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)。

**為資料集資料儲存新增位置的方式**

1. 在[!DNL Insight]中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要配置的[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以查看其內容。 [!DNL Disk Files.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL Disk Files.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Disk Files.cfg]的[!DNL Temp]列中出現複選標籤。
1. 在[!DNL Temp]欄中按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL Disk Files.cfg]窗口中，按一下&#x200B;**[!UICONTROL component]**&#x200B;查看其內容。

   ![步驟資訊](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >預設情況下， Detect Disk Crobution參數設定為true。 「磁碟快取大小(MB)」參數控制[!DNL Insight Server]用於提高磁碟訪問速度的記憶體量，預設情況下設定為128。 在更改其中一個參數之前，請與Adobe聯繫。

1. 要更改[!DNL Insight Server]電腦上的磁碟檔案，請按一下右鍵&#x200B;**[!UICONTROL Disk Files]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Disk File]**。

   要刪除磁碟檔案，請按一下右鍵磁碟檔案號，然後按一下&#x200B;**[!UICONTROL Remove]**。

1. 對於新磁碟檔案，輸入[!DNL Insight Server]在重新處理和操作期間要使用的檔案的目錄和名稱。

   ![步驟資訊](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >預設情況下， Detect Disk Crobution參數設定為true。 「磁碟快取大小(MB)」參數控制[!DNL Insight Server]用於提高磁碟訪問速度的記憶體量，預設情況下設定為128。 在更改其中一個參數之前，請與Adobe聯繫。

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，按一下右鍵[!DNL Temp]列中檔案的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。
