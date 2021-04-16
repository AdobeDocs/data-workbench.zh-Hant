---
description: 訪問級別描述了允許一組用戶讀取或修改電腦上的哪些URI。
title: 瞭解存取層級
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# 瞭解存取層級{#understanding-access-levels}

訪問級別描述了允許一組用戶讀取或修改電腦上的哪些URI。

請依照下列准則，為組織的使用者定義所需的存取層級：

* 沒有尾隨斜線字元的特定URI僅限該URI的存取。 例如，[!DNL /Components/Communications.cfg]僅提供對[!DNL Communications.cfg]檔案的訪問。

* 指定目錄的尾隨斜線(/)可讓群組成員存取以該字串開頭的任何URI。 例如，/Profiles/提供對整個Profiles目錄的訪問。
* 尾隨美元符號符號($)僅限限制對精確URI的存取，即使它是目錄亦然。 例如，/Profiles/$提供讀取主Profiles目錄的權限，但不能讀取該目錄內的任何檔案。

   若要存取特定檔案，您不需要使用尾隨$。

   例如，[!DNL /Components/Communications.cfg]和[!DNL /Components/Communications.cfg$]提供相同的存取。

* 百分比符號(%)可與CN（公用名稱）搭配使用，以允許存取。 例如，/Users/%CN%/允許訪問與[!DNL Insight]用戶的SSL證書公共名稱匹配的用戶目錄。 請注意，此語法在URI中只能使用一次。

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
   <td colname="col4"> <p>對所有<span class="keyword"> Insight Server</span>目錄的讀取和寫入訪問。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>感測器 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>讀取和寫入<span class="wintitle">感測器</span>用於與<span class="keyword"> Insight Server</span>通信的兩個檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者 </p> </td> 
   <td colname="col2"> <p>/設定檔/ </p> <p>/狀態/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/使用者/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>讀取和寫入與<span class="keyword"> Insight</span>使用者的SSL憑證公用名稱相符的使用者目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>超級用戶 </p> </td> 
   <td colname="col2"> <p>/設定檔/$ </p> <p>/狀態/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/使用者/$ </p> </td> 
   <td colname="col3"> <p>/設定檔/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>高級用戶可以與用戶具有相同的訪問權限，並可以添加寫入配置檔案目錄的能力。 這些使用者可以編輯描述檔，並讓其他<span class="keyword"> Insight</span>使用者的變更自動更新，例如在分發新定義的工作區時。 </p> </td> 
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
   <td colname="col4"> <p>報告電腦可以與電源用戶訪問相同，並添加了寫入<span class="filepath"> ReportStatus.vsp</span>檔案的功能。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**配置訪問控制**

定義訪問控制組時，需要包括所有需要訪問此[!DNL Insight Server]電腦的系統管理員、用戶、群集伺服器和報告伺服器用戶。 您可以使用IP位址或SSL憑證資訊（例如公用名稱或組織）來授與存取權。

>[!NOTE]
>
>在[!DNL Insight Server]上更改[!DNL Access Control.cfg]檔案時，所有現有連接都會被終止並強制重新連接。 根據更新的[!DNL Access Control.cfg]檔案中的權限檢查連接。 在「伺服器管理器」介面中，[!DNL Insight Server]表徵圖會暫時變為紅色，然後再次變為綠色，因為連接被終止，並強制與所有其它連接重新連接。

1. 在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。

1. 按一下右鍵要配置的[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Files]**。

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Access Control]**&#x200B;查看其內容。 [!DNL Access Control.cfg]檔案位於此目錄中。

1. 按一下右鍵[!DNL Access Control.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL Access Control.cfg]的[!DNL Temp]欄中會出現複選標籤。

1. 在[!DNL Temp]欄中按一下新建立的核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Workstation]**。

1. 在[!DNL Access Control.cfg]窗口中，按一下&#x200B;**[!UICONTROL Access Control Groups]**&#x200B;查看其內容。

   ![](assets/access_ctrl_cfg.png)

1. 要添加新訪問控制組，請執行以下操作：

   1. 按一下右鍵&#x200B;**[!UICONTROL Access Control Groups]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Group]**。

   1. 按一下右鍵&#x200B;**[!UICONTROL Members]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Member]**。

      預設組的成員未預先定義。 預設情況下，管理員訪問權被授予127.0.0.1（本地主機）,[!DNL Sensor]訪問權被授予IP:*。 必須定義所有其他訪問控制組成員。

   1. 完成參數。

1. 要向現有訪問控制組添加新成員，請執行以下操作：

   1. 按一下右鍵相應訪問控制組下的&#x200B;**[!UICONTROL Members]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Member]**。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]** ，以保存檔案。

1. 要保存對[!DNL Insight Server]電腦所做的更改，請在[!DNL Server Files Manager]中按一下右鍵[!DNL Temp]列中的[!DNL Access Control.cfg]複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** ***[!UICONTROL server name]***。
