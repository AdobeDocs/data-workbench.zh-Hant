---
description: 請依照下列步驟升級至Data Workbench v6.4。
title: 將6.3升級至6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 2930bd3ae06e700e75144221fc993efdd6bd1e85
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---


# Upgrading 6.3 to 6.4{#upgrading-to}

請依照下列步驟升級至Data Workbench v6.4。

## 升級需求與建議 {#section-8704a9ac358246cd81233dd0982d534f}

在升級至資料工作台6.4時，請遵循這些需求和建議。

>[!IMPORTANT]
>
>建議您使用新安裝的預設設定檔案並加以自訂，而不是從先前的安裝移動檔案，但有下列例外：

* **在Windows** 2012 ***伺服器中為*** MS System Center端點保護添加排除的進程，以用於以下執行檔 ** :

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   這將為這些介面執行檔啟用允許清單權限。

* **在伺服器&#x200B;*上更新Trust_ca_cert.pem*憑證**。
* **重組歸因設定檔**。

   * Attribution ** 資料夾已重新命名為 ***Attribution - Premium*** (位於 *Profiles*\*Attribution - Premium*的預設安裝)。

   * Premium *描述檔已移除，工作區已移至新的* Attribution - Premium資料夾 ****** 。

* **更新&#x200B;*Attribution-Premium設定***。 如果您有自訂的描述檔，其參數設定會覆寫預設的 *Adobe SC* ，則您必須更新下列組態檔中的自訂欄位：

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* 由於這項重組，您會想要從伺服器安裝 *移除舊**Attribution* 和Premium資料夾。

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

   此版 **[!DNL Meta.cfg]** 本中已 **[!DNL Base\Context and AdobeSC\Context]** 更新資料夾中的檔案。

   如果您在安裝期 **間覆寫meta.cfg檔案** ，則您的描述檔復本必須以下列參數和正確輸入的中繼資料 **向量來更新** :

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

* **設定報表伺服器權限** ，以便在Windows 2012伺服器上產生Microsoft Excel報表。

   1. 將根資料夾(**[!DNL E:\ReportServer\]**)的權限設定 *為「每個人=完全控制」*。

   1. 使用適當的權限建立下列資料夾：

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >如果您在Windows Server 2012上運行Report Server，則需要安裝Windows Server 2012 R2。

   1. 將&quot;SYSTEM&quot;指定為這些資料夾的所有者。

* **新增字型至報表伺服器。** 在**[!DNL ReportServer.cfg]**檔案中，新增這些字型（適用於所有語言）:

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **更新您的Microsoft Excel **（如有需要）。

   隨著Data Workbench 6.4的推出，Excel 2007的支援已中止。 此外，由於資料工作台僅在Microsoft Windows上執行64位元架構，因此建議您也安裝64位元版本的Microsoft Excel。

* **安裝工作站** （客戶端）需要64位體系結構。
* **運行工作站設定嚮導**。

   下載並啟動 ****** InsightSetup.exe並逐步執行設定指示，以安裝新版工作站（用戶端）。 安裝嚮導將預設將檔案安裝到新位置：

   程式檔案現在預設會儲存為：

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   資料檔案（描述檔、憑證、追蹤記錄檔和使用者檔案）現在預設會儲存為：

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **將字型新增至Workstation**。

   在檔案 **[!DNL Insight.cfg]** 中，新增這些字型（適用於所有語言）:

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

