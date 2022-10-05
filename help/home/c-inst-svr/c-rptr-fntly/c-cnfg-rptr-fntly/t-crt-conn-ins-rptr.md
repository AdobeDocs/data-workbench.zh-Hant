---
description: 如果網路防火牆無法阻止Insight電腦存取中繼器伺服器，您可以在中繼器伺服器與Insight之間建立連線，以便您能使用Insight管理中繼器伺服器。
title: 在 Insight 和中繼器之間建立連線
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 4%

---

# 在 Insight 和中繼器之間建立連線{#creating-a-connection-between-insight-and-repeater}

{{eol}}

如果網路防火牆無法阻止Insight電腦存取中繼器伺服器，您可以在中繼器伺服器與Insight之間建立連線，以便您能使用Insight管理中繼器伺服器。

**在 [!DNL Insight] 和中繼器伺服器**

1. 在 [!DNL Insight]，在 [!DNL Admin] ，按一下 **[!UICONTROL Configure Connections to Servers]** 縮圖以開啟「設定與伺服器的連線」工作區。
1. 在 [!DNL Insight.cfg] 窗口，按一下右鍵 **[!UICONTROL Servers]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. 對於新伺服器，請完成下列參數：

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
   <td colname="col2">（選用）您想要的名稱 <span class="keyword"> 分析</span> 以在其使用者介面中代表中繼器伺服器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <p>中繼器伺服器的主機名稱或數值IP位址。 </p> <p>範例： <span class="filepath"> Repeater.mycompany.com</span> 或192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL用戶端憑證 </td> 
   <td colname="col2"> <p>選用，除非您有多個憑證。 包含此副本的數位憑證的檔案名稱 <span class="keyword"> 分析</span>. (這是安裝時下載的檔案 <span class="keyword"> 分析</span>.) </p> <p>範例： <span class="filepath"> 薩曼莎·史密斯.pem</span></p> <p>如果將此參數留空， <span class="keyword"> 分析</span> 會使用任何憑證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL伺服器 </p> <p>公用名稱 </p> </td> 
   <td colname="col2">指派給中繼器伺服器的通用名稱。 此名稱必須符合在其授權憑證中指派給中繼器伺服器的一般名稱。 如果您可存取中繼器的憑證檔案(<span class="filepath"> Certificates\server_cert.pem</span>)，則可以使用文本編輯器（如記事本）開啟檔案來找到通用名稱。 在憑證的CN欄位中識別通用名稱。 </td> 
  </tr> 
 </tbody> 
</table>

1. 按一下滑鼠右鍵以儲存檔案 **[!UICONTROL (modified)]** 按一下 **[!UICONTROL Save]**. [!DNL Insight] 會嘗試使用您指定的設定連線至中繼器伺服器。 如果已建立連線， [!DNL Servers Manager] 介面。 如果無法建立連接，則會顯示紅色表徵圖。

   如需 [!DNL Servers Manager] 介面，請參閱* [!DNL Insight] 使用手冊*。
