---
description: 訪問級別描述允許一組用戶讀取或修改電腦上的哪些URI。
title: 瞭解存取層級
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# 瞭解存取層級{#understanding-access-levels}

{{eol}}

訪問級別描述允許一組用戶讀取或修改電腦上的哪些URI。

請依照下列准則，視需要為組織的使用者定義存取層級：

* 沒有尾斜線字元的特定URI僅限訪問該URI。 例如， [!DNL /Components/Communications.cfg] 提供 [!DNL Communications.cfg]檔案。

* 尾隨斜線(/)指定目錄，為組成員提供對以該字串開頭的任何URI的訪問。 例如， /Profiles/提供對整個Profiles目錄的訪問。
* 尾隨美元符號($)僅限訪問確切的URI，即使它是目錄亦然。 例如， /Profiles/$提供讀取主Profiles目錄的訪問權限，但不能讀取該目錄中的任何檔案。

   若要存取特定檔案，您不需使用尾端$。

   例如， [!DNL /Components/Communications.cfg] 和 [!DNL /Components/Communications.cfg$] 提供相同的存取權。

* 百分比符號(%)可與CN（通用名稱）一起使用，以允許訪問。 例如， /Users/%CN%/允許訪問與的SSL證書公共名稱匹配的用戶目錄 [!DNL Insight] 使用者。 請注意，此語法在URI中只能使用一次。

預定義的訪問控制組中的URI已配置如下：

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
   <td colname="col4"> <p>讀取和寫入所有 <span class="keyword"> Insight Server</span> 目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>感測器 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>讀取和寫入 <span class="wintitle"> 感測器</span> 用於與 <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用戶 </p> </td> 
   <td colname="col2"> <p>/設定檔/ </p> <p>/狀態/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/用戶/$ </p> </td> 
   <td colname="col3"> /用戶/%CN%/ </td> 
   <td colname="col4"> <p>對與的SSL證書公共名稱匹配的用戶目錄的讀寫訪問 <span class="keyword"> 分析</span> 使用者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>超級用戶 </p> </td> 
   <td colname="col2"> <p>/設定檔/$ </p> <p>/狀態/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/用戶/$ </p> </td> 
   <td colname="col3"> <p>/設定檔/ </p> <p>/用戶/%CN%/ </p> </td> 
   <td colname="col4"> <p>Power Users與Users具有相同的訪問權限，並且還能夠寫入Profiles目錄。 這些使用者可編輯設定檔，並啟用其他使用者自動更新的變更 <span class="keyword"> 分析</span> 使用者，例如分佈新定義的工作區時。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>群集伺服器 </p> </td> 
   <td colname="col2"> <p>/處理伺服器的元件/ </p> <p>/地址/ </p> <p>/設定檔/ </p> <p>/Lookups/ </p> <p>/存取控制/ </p> <p>/Bin/ </p> <p>/記錄檔/ </p> </td> 
   <td colname="col3"> <p>/cluster/ </p> </td> 
   <td colname="col4"> <p>對群集目錄的讀寫訪問。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>報表伺服器 </p> </td> 
   <td colname="col2"> <p>/設定檔/$ </p> <p>/狀態/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/用戶/$ </p> </td> 
   <td colname="col3"> <p>/設定檔/ </p> <p>/用戶/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>報表電腦可以與電源用戶具有相同的訪問權限，並且還能夠寫入 <span class="filepath"> ReportStatus.vsp</span> 檔案。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**配置訪問控制**

定義訪問控制組時，需要包括所有需要訪問此權限的系統管理員、用戶、群集伺服器和報告伺服器用戶 [!DNL Insight Server] 電腦。 您可以使用IP位址或SSL憑證資訊（例如通用名稱或組織）來授與存取權。

>[!NOTE]
>
>當 [!DNL Access Control.cfg] 檔案在 [!DNL Insight Server]，則所有現有連線都會終止，並強制重新連線。 系統會根據更新後的 [!DNL Access Control.cfg] 檔案。 在伺服器管理器介面中， [!DNL Insight Server] 表徵圖會暫時變為紅色，然後再次變為綠色，因為連接已終止，並且會強制與所有其他連接重新連接。

1. 在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。

1. 以滑鼠右鍵按一下 [!DNL Insight Server] 要配置，請按一下 **[!UICONTROL Files]**.

1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Access Control]** 來檢視其內容。 此 [!DNL Access Control.cfg] 檔案位於此目錄中。

1. 以滑鼠右鍵按一下 *伺服器名稱* 欄 [!DNL Access Control.cfg] 按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Access Control.cfg].

1. 在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. 在 [!DNL Access Control.cfg] 按一下 **[!UICONTROL Access Control Groups]** 來檢視其內容。

   ![](assets/access_ctrl_cfg.png)

1. 要添加新的訪問控制組：

   1. 按一下右鍵 **[!UICONTROL Access Control Groups]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. 按一下右鍵 **[!UICONTROL Members]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      預設組的成員未預定義。 依預設，管理員存取權會授予127.0.0.1（本機主機），以及 [!DNL Sensor] 授予IP存取權：&#42;. 必須定義所有其他訪問控制組成員。

   1. 完成參數。

1. 要向現有訪問控制組添加新成員，請執行以下操作：

   1. 按一下右鍵 **[!UICONTROL Members]** 在適當的訪問控制組下，按一下 **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. 按一下滑鼠右鍵以儲存檔案 **[!UICONTROL (modified)]** ，然後按一下 **[!UICONTROL Save]**.

1. 若要儲存本機對 [!DNL Insight Server] 機器，在 [!DNL Server Files Manager]，按一下右鍵的複選標籤 [!DNL Access Control.cfg] 在 [!DNL Temp] 欄，然後按一下 **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]**>*.
