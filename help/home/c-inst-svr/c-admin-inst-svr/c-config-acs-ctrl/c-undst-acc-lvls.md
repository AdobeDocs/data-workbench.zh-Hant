---
description: 訪問級別描述了允許一組用戶讀取或修改電腦上的哪些URI。
solution: Analytics
title: 瞭解存取層級
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---


# 瞭解存取層級{#understanding-access-levels}

訪問級別描述了允許一組用戶讀取或修改電腦上的哪些URI。

請依照下列准則，為組織的使用者定義所需的存取層級：

* 沒有尾隨斜線字元的特定URI僅限該URI的存取。 例如，僅 [!DNL /Components/Communications.cfg] 提供對檔案 [!DNL Communications.cfg]的訪問。

* 指定目錄的尾隨斜線(/)可讓群組成員存取以該字串開頭的任何URI。 例如，/Profiles/提供對整個Profiles目錄的訪問。
* 尾隨美元符號符號($)僅限限制對精確URI的存取，即使它是目錄亦然。 例如，/Profiles/$提供讀取主Profiles目錄的權限，但不能讀取該目錄內的任何檔案。

   若要存取特定檔案，您不需要使用尾隨$。

   例如， [!DNL /Components/Communications.cfg] 並提 [!DNL /Components/Communications.cfg$] 供相同的存取權。

* 百分比符號(%)可與CN（公用名稱）搭配使用，以允許存取。 例如，/Users/%CN%/允許訪問與用戶的SSL證書公共名稱匹配的用戶目 [!DNL Insight] 錄。 請注意，此語法在URI中只能使用一次。

預定義訪問控制組中的URI配置如下：

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 群組名稱 </th> 
   <th colname="col2" class="entry"> 唯讀存取 </th> 
   <th colname="col3" class="entry"> 讀寫訪問 </th> 
   <th colname="col4" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>管理員 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>讀取和寫入所有 <span class="keyword"> Insight Server目錄</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>感測器 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>讀取和寫入Sensors用於與 <span class="wintitle"> Insight Server通信的兩個檔案</span><span class="keyword"></span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者 </p> </td> 
   <td colname="col2"> <p>/設定檔/ </p> <p>/狀態/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/使用者/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>讀取和寫入與Insight使用者的SSL憑證公用名稱相符的使用者目錄 <span class="keyword"> 存取</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>超級用戶 </p> </td> 
   <td colname="col2"> <p>/設定檔/$ </p> <p>/狀態/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/使用者/$ </p> </td> 
   <td colname="col3"> <p>/設定檔/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>高級用戶可以與用戶具有相同的訪問權限，並可以添加寫入配置檔案目錄的能力。 這些使用者可以編輯設定檔，並讓變更自動更新給其他 <span class="keyword"> Insight</span> 使用者，例如在分發新定義的工作區時。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>群集伺服器 </p> </td> 
   <td colname="col2"> <p>/Components for Processing Servers/ </p> <p>/地址/ </p> <p>/設定檔/ </p> <p>/Lookups/ </p> <p>/存取控制/ </p> <p>/Bin/ </p> <p>/記錄檔/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>對群集目錄的讀寫訪問。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>報表伺服器 </p> </td> 
   <td colname="col2"> <p>/設定檔/$ </p> <p>/狀態/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/使用者/$ </p> </td> 
   <td colname="col3"> <p>/設定檔/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>報告電腦可以與「超級用戶」具有相同的訪問權限，並可以對 <span class="filepath"> ReportStatus.vsp檔案進行寫入</span> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**配置訪問控制**

定義訪問控制組時，需要包括所有需要訪問此電腦的系統管理員、用戶、群集伺服器和報告伺服器用 [!DNL Insight Server] 戶。 您可以使用IP位址或SSL憑證資訊（例如公用名稱或組織）來授與存取權。

>[!NOTE]
>
>在上更 [!DNL Access Control.cfg] 改檔案時，所有現 [!DNL Insight Server]有連接都會終止並強制重新連接。 根據更新檔案中的權限檢查連 [!DNL Access Control.cfg] 線。 在「伺服器管理器」介面中，該圖 [!DNL Insight Server] 標會暫時變為紅色，然後再次變為綠色，因為連接被終止，並強制與所有其它連接一起重新連接。

1. 在>標 [!DNL Admin] 簽上 [!DNL Dataset and Profile] ，按一下縮 **[!UICONTROL Servers Manager]** 圖以開啟「伺服器管理員」工作區。

1. 按一下右鍵要配置的 [!DNL Insight Server] 表徵圖，然後按一下 **[!UICONTROL Files]**。

1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Access Control]** 查看其內容。 文 [!DNL Access Control.cfg] 件位於此目錄中。

1. 按一下右鍵的伺服器名 *稱列中的複選標籤* ，然 [!DNL Access Control.cfg] 後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在的 [!DNL Temp] 列中 [!DNL Access Control.cfg]。

1. 在欄中以滑鼠右鍵按一下新建立的核取標 [!DNL Temp] 記，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Workstation]**。

1. 在視窗 [!DNL Access Control.cfg] 中，按一 **[!UICONTROL Access Control Groups]** 下以檢視其內容。

   ![](assets/access_ctrl_cfg.png)

1. 要添加新訪問控制組，請執行以下操作：

   1. 以滑鼠右鍵按 **[!UICONTROL Access Control Groups]** 一下，然後按 **[!UICONTROL Add new]** > **[!UICONTROL Group]**。

   1. 以滑鼠右鍵按 **[!UICONTROL Members]** 一下，然後按 **[!UICONTROL Add new]** > **[!UICONTROL Member]**。

      預設組的成員未預先定義。 預設情況下，管理員訪問權限授予127.0.0.1（本地主機）, [!DNL Sensor] 並授予IP:*訪問權限。 必須定義所有其他訪問控制組成員。

   1. 完成參數。

1. 要向現有訪問控制組添加新成員，請執行以下操作：

   1. 在適當的 **[!UICONTROL Members]** 存取控制群組下按一下滑鼠右鍵，然後按一 **[!UICONTROL Add new]** 下> **[!UICONTROL Member]**。

1. 以滑鼠右鍵按一下視窗頂 **[!UICONTROL (modified)]** 端的檔案，然後按一下以儲存檔案 **[!UICONTROL Save]**。

1. 要保存對電腦進行的本 [!DNL Insight Server] 地更改，請在 [!DNL Server Files Manager]中按一下右鍵列中的複選標籤，然後 [!DNL Access Control.cfg] 按一下 [!DNL Temp] &lt; **[!UICONTROL Save to]** > ***[!UICONTROL server name]***&#x200B;選中標籤。

