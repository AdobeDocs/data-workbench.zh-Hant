---
description: 如果網路防火牆無法阻止從Insight機器存取中繼器伺服器，您可以在中繼器伺服器與Insight之間建立連線，以便您使用Insight管理中繼器伺服器。
solution: Insight
title: 在Insight和Repeater之間建立連線
uuid: dccce83a-8708-4763-a19a-64d905a9f624
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 在Insight和Repeater之間建立連線{#creating-a-connection-between-insight-and-repeater}

如果網路防火牆無法阻止從Insight機器存取中繼器伺服器，您可以在中繼器伺服器與Insight之間建立連線，以便您使用Insight管理中繼器伺服器。

**在中繼器伺服器[!DNL Insight]和中繼器伺服器間建立連線**

1. 在標 [!DNL Insight]簽中，單 [!DNL Admin] 擊縮略圖以 **[!UICONTROL Configure Connections to Servers]** 開啟「配置到伺服器的連接」工作區。
1. 在視窗 [!DNL Insight.cfg] 中，以滑鼠右鍵按一 **[!UICONTROL Servers]** 下並按 **[!UICONTROL Add new]** > **[!UICONTROL Server]**。
1. 對於新伺服器，請完成以下參數：

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於此參數…… </th> 
   <th colname="col2" class="entry"> 指定分類的... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2">（可選）您希望此Insight用來在其使用者介面中 <span class="keyword"></span> 代表中繼器伺服器的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <p>中繼器伺服器的主機名稱或數值IP位址。 </p> <p>範例： <span class="filepath"> Repeater.mycompany.com</span> 或192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL用戶端憑證 </td> 
   <td colname="col2"> <p>選用，除非您有多個憑證。 包含此Insight副本之數位憑證的檔案名 <span class="keyword"> 稱</span>。 (這是您在安裝 <span class="keyword"> Insight時下載的檔案</span>。) </p> <p>範例：薩 <span class="filepath"> 曼莎·史密斯</span></p> <p>如果您將此參數留空， <span class="keyword"> Insight</span> 會使用任何憑證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL伺服器 </p> <p>通用名稱 </p> </td> 
   <td colname="col2">指派給中繼器伺服器的公用名稱。 此名稱必須與在其授權憑證中指派給中繼器伺服器的公用名稱相符。 如果您可存取中繼器的憑證檔案(<span class="filepath"> Certificates\server_cert.pem</span>)，則可使用記事本等文字編輯器開啟檔案，以找到常用名稱。 在證書的CN欄位中標識公用名稱。 </td> 
  </tr> 
 </tbody> 
</table>

1. 以滑鼠右鍵按一下視窗頂 **[!UICONTROL (modified)]** 端的檔案，然後按一下以儲存檔案 **[!UICONTROL Save]**。 [!DNL Insight] 將會嘗試使用您指定的設定連線至中繼器伺服器。 如果建立連接，介面中將顯示綠色的伺服器 [!DNL Servers Manager] 表徵圖。 如果無法建立連線，則會顯示紅色圖示。

   For more information about the [!DNL Servers Manager] interface, see the * [!DNL Insight] User Guide*.

