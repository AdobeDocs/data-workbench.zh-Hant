---
description: 升級Data Workbench 6.3的伺服器元件。
title: DWB Server升級版6.2至6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# DWB伺服器升級：6.2至6.3{#dwb-server-upgrade-to}

升級Data Workbench 6.3的伺服器元件。

**升級伺服器**

如果您有自訂設定檔，其優先順序高於套件中提供的預設 [!DNL Base] 檔案，則您需要更新這些自訂檔案：

* **更新Meta.cfg檔案** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]為檔案系統單元（FSU伺服器）設定更新的密碼加密，並新增名稱值對變更的項目，以利用 [Query String群組](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0)。

   1. 在FSU [!DNL meta.cfg] 上開啟檔案。
   1. 在「工作站配置」 **[!UICONTROL Proxy Password]** 部分中將 [!DNL string"] 「」的數 [!DNL EncryptedString]據類型從 ** 「」更改。

      ```
      Proxy User Name = string: 
      Proxy Password = EncryptedString:   ( 
      
<i>從Proxy密碼=字串</i>)使用位址檔案=bool:true」

    1.添加新條目以啟用新的名稱值對轉換：*BuildNameValuePair*和*ExtractNameValuePairs*。
    
    開啟工作區，然後以滑鼠右鍵按一下**管理員** > **描述檔管理員**。
    
    在**Context**下，按一下**Base**欄中的**meta.cfg**檔案，然後按一下**Make Local**。 在「用戶」表列中，按一下右鍵並選擇「工作站**中的**開啟** > **」。
    
    ![](assets/meta_cfg.png)
    
    *在新視窗中，按一下**metadata**並新增可接受的子範本。
    
    ![](assets/meta_cfg_child.png)
    
    *開啟**transformation**並新增範本。
    
    ![](assets/meta_cfg_template.png)

* **更新快速合併改良功能**。 在轉換期間，將參數或變更值新增至下列設定檔案，以運用資料工作台中的速度改進功能。

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:  
          URI = string: /SourceListServer/ 
          Listing Interval = int: 10 ( 
      <new>)
      ```

   * **Disk Files.cfg** (at [!DNL E:\Server\Components] 和 [!DNL E:\Server\Components for Processing Servers])

      ```
      Disk Cache Size (MB) = double: 1024  
      <(from double: 256)> 
      Disk Cache Read Limit (MB) = double: 768  
      <(new)>
      ```

   * **記錄處理模式。cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

      ```
      <(changed) 
      Batch Bytes = int: 268435456 
      Cloud Bytes = int: 268435456 
      Real Time FIFO Bytes = int: 268435456
      ```

      ```
      ( 
      <new>) 
      Cache Bytes = int: 32000000 
      Fast Input Decision Ratio = double: 200 
      Fast Input FIFO Bytes = int: 268435456 
      FIFO Hash Mask = int: 16383 
      Fast Merge Buffer Bytes = int: 536870912 
      Slow Merge Buffer Bytes = int: 268435456 
      Fast Merge Fan In = int: 64 
      Key Cache Size Logarithm = int: 21 
      Max Seeks = int: 512 
      Output Old Buffer Bytes = int: 536870912 
      Overflow FIFO Bytes = int: 67108864 
      Paused = bool: false
      ```
   >[!NOTE]
   >
   >若要運用快速合併功能的增強功能，請確定每個DPU至少有8 GB的記憶體。

* **Adobe Target與DWB整合更新**。 新的匯出檔案 [!DNL ExportIntegration.exe]會取代Insight Server( [!DNL TnTSend.exe] )上的現有檔案`E:\Server\Scripts\TnTSend.exe`。 此新的匯出檔案支援 [Adobe Target](https://www.adobe.com/marketing/target.html) 與新的主行銷設定檔(MMP)和 [Adobe Audience Manager的整合與協調](https://www.adobe.com/analytics/audience-manager.html)。

   您需要更新下列Adobe Target匯出指令。

   `Command = string: TnTSend.exe`

   變更為

   ```
   <filepath>
   Command = string: ExportIntegration.exe 
   </filepath>
   ```

   >[!NOTE]
   >
   >這只會影響6.3版之前建立的匯出。

   您也可以嘗試使用下列項目來運用舊的匯出程式：

   * 在工作站中建立新的測試和目標匯出。
   * 修改舊的「測試」和「目標」匯出(位於 [!DNL Server/Profiles/`<your profile>`/Export中)。]

* **更新Adobe SC設定檔。** 對檔案的 [!DNL Exclude Hit.cfg] 更改要求在關聯檔案中聲明一個 [!DNL Decoding Instructions.cfg] 欄位。

   >[!NOTE]
   >
   >如果您的Adobe SC設定檔包含自訂 [!DNL Decoding Instructions.cfg] 檔案，您將需要在自訂檔 [!DNL DelimitedDecoder] 案中加入參數。

   ```
   0 = DelimitedDecoder: 
      Delimiter = string: \t 
      Fields = vector: x items 
      …  
         5 = string: 
   Changed to: 
   
   5 = string: x-hit_source
   ```

   新增欄 [!DNL DelimitedDecoder] 位可讓您運用功能更新，並避免因這些更新而產生的記錄處理問題。
