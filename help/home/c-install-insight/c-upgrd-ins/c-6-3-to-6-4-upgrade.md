---
description: 請依照下列步驟升級至Data Workbenchv6.4。
title: 6.3 升級至 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
exl-id: 540deb86-2463-4820-b67a-a32d68b4346e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# 6.3 升級至 6.4{#upgrading-to}

{{eol}}

請依照下列步驟升級至Data Workbenchv6.4。

## 升級需求和Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

升級至Data Workbench6.4時，請遵循這些需求和建議。

>[!IMPORTANT]
>
>建議您使用新安裝的預設配置檔案並對其進行自定義，而不是從以前的安裝中移動檔案，但有以下例外：

* **新增** ***排除的進程*** for *Windows 2012伺服器中的MS System Center端點保護* 對於以下執行檔：

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   這將為這些介面執行檔啟用允許清單權限。

* **更新 *Trust_ca_cert.pem* 伺服器上的證書**.
* **重組歸因設定檔**.

   * 此 *歸因* 資料夾重新命名為 ***歸因 — Premium*** (在預設安裝中找到，位於 *設定檔*\*歸因 — Premium*)。

   * 此 *Premium* 設定檔已移除，且工作區已移至新 ***歸因 — Premium*** 檔案夾。

* **更新 *Attribution-Premium* 設定**. 如果您有自訂的設定檔，其參數設定會覆寫預設值 *AdobeSC* 設定檔，則您需要更新這些設定檔中的自訂欄位：

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* 因為此重組，您將要移除舊 *歸因* 和 *Premium* 資料夾。

   **變更這些設定**

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 6 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
   
       4 = string: Attribution\\ 
       5 = string: Premium\\
   ```

   至下列設定：

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\
       4 = string: Attribution - Premium\\
   ```

* **更新自訂Meta.cfg檔案** （如有必要）。

   此 **[!DNL Meta.cfg]** 檔案 **[!DNL Base\Context and AdobeSC\Context]** 資料夾在此版本中已更新。

   如果您覆寫 **meta.cfg** 檔案安裝期間，您的設定檔復本需使用這些參數和 **中繼資料向量** 正確輸入：

   ```
   94 = meta: 
     path = string: SegmentExport:CRS Configuration/CRS Attributes 
     acceptable children = vector: 1 items 
       0 = Template: 
         name = string: CRS Attributes 
         value = CRSAttributeConfiguration: 
           Attribute Name = string: 
           Attribute Type(int,string) = string: 
           Field Name = string: 
   
   95 = meta: 
     path = string: SegmentExportQuery:CRS Configuration/Report Suite 
     acceptable children = vector: 1 items 
       0 = Template 
         name = string: Add Report Suite 
         value = string:
   ```

* **設定報表伺服器權限** 在Windows 2012伺服器上產生Microsoft Excel報表。

   1. 設定根資料夾的權限(**[!DNL E:\ReportServer\]**) *所有人=完全控制*.

   1. 使用適當權限建立下列資料夾：

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >如果在Windows Server 2012上運行Report Server，則需要安裝Windows Server 2012 R2。

   1. 將&quot;SYSTEM&quot;指定為這些資料夾的所有者。

* **將字型新增至報表伺服器。** 在**[!DNL ReportServer.cfg]**檔案，添加這些字型（適用於所有語言）:

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **更新您的Microsoft Excel **版（如有需要）。

   隨著Data Workbench6.4的發行，Excel 2007的支援已停止。 另外，由於Data Workbench只會在Microsoft Windows上執行64位元架構，因此建議您也安裝64位元版Microsoft Excel。

* **64位體系結構** 安裝工作站（客戶端）所需。
* **運行工作站設定嚮導**.

   下載並啟動，以安裝新版工作站（客戶端） ***InsightSetup.exe*** 並逐步執行設定指示。 預設情況下，安裝嚮導會將您的檔案安裝到新位置：

   程式檔案現在預設會儲存為：

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   資料檔案（設定檔、憑證、追蹤記錄和使用者檔案）現在預設會儲存為：

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **向工作站添加字型**.

   在 **[!DNL Insight.cfg]** 檔案中，添加這些字型（所有語言）:

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```
