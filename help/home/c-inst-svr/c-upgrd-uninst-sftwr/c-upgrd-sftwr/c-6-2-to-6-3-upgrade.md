---
description: 升級Data Workbench6.3的伺服器元件。
title: DWB伺服器6.2升級至6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
exl-id: 5106d9a3-179a-49f1-915a-c03b36ed5257
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# DWB 伺服器升級：6.2 升級至 6.3{#dwb-server-upgrade-to}

{{eol}}

升級Data Workbench6.3的伺服器元件。

**升級伺服器**

如果您有自訂的設定檔，其優先於 [!DNL Base] 封裝，則您需要更新這些自訂檔案：

* **更新Meta.cfg檔案** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]為檔案系統單元（FSU伺服器）設定更新的密碼加密，並為名稱值對轉換添加條目以利用 [查詢字串群組](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. 開啟 [!DNL meta.cfg] 檔案。
   1. 變更 **[!UICONTROL Proxy Password]** 從&quot; [!DNL string"] 到&quot; [!DNL EncryptedString]」 *工作站配置* 區段。

      ```
        Proxy User Name = string:
        Proxy Password = EncryptedString:   (
        from Proxy Password = String)
        Use Address File = bool: true
      ```

   1. 添加新條目以啟用新的名稱值對轉換： *BuildNameValuePair* 和 *ExtractNameValuePairs*.

      開啟工作區並按一下滑鼠右鍵 **管理** > **設定檔管理員**.

      在 **內容**，按一下 **meta.cfg** 檔案 **基** 欄，然後按一下 **使本地**. 在「用戶」表列中，按一下右鍵並選擇 **開啟** > **在工作站中**.

      ![](assets/meta_cfg.png)

      * 在新視窗中，按一下 **中繼資料** 和添加可接受的子模板。

         ![](assets/meta_cfg_child.png)

      * 開啟 **轉換** 和新增範本。

         ![](assets/meta_cfg_template.png)

* **更新以改善快速合併**. 將參數或變更值新增至下列組態檔，以便在轉換期間善用Data Workbench的速度。

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

   * **Log Processing Mode.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

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
   >若要利用快速合併改善功能，請確定每個DPU至少有8 GB的RAM。

* **Adobe Target與DWB整合更新**. 新的匯出檔案， [!DNL ExportIntegration.exe]，取代現有 [!DNL TnTSend.exe] 檔案(`E:\Server\Scripts\TnTSend.exe`)。 這個新的匯出檔案同時支援 [Adobe Target](https://www.adobe.com/marketing/target.html) 與新的主行銷設定檔(MMP)整合與協調，以及 [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

   您需要更新下列命令，才能匯出Adobe Target。

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

   您也可以嘗試下列步驟，以採用舊的匯出程式：

   * 在工作站中建立新的測試和目標匯出。
   * 修改舊的Test和Target匯出，位於 [!DNL Server/Profiles/`<your profile>`/Export.]

* **更新AdobeSC配置檔案。** 變更 [!DNL Exclude Hit.cfg] 檔案要求在關聯的欄位中聲明 [!DNL Decoding Instructions.cfg] 檔案。

   >[!NOTE]
   >
   >如果您的AdobeSC設定檔包含自訂的 [!DNL Decoding Instructions.cfg] 檔案，您需要 [!DNL DelimitedDecoder] 參數。

   ```
   0 = DelimitedDecoder:
      Delimiter = string: \t
      Fields = vector: x items
      …
         5 = string:
   Changed to:
   
   5 = string: x-hit_source
   ```

   新增 [!DNL DelimitedDecoder] 欄位可讓您善用功能更新，並避免因這些更新而可能發生的記錄處理問題。
