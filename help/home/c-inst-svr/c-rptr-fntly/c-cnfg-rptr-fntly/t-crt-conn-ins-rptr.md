---
description: 如果網路防火牆無法阻止Insight電腦存取中繼器伺服器，您可以在中繼器伺服器與Insight之間建立連線，以便您能使用Insight管理中繼器伺服器。
title: 在 Insight 和中繼器之間建立連線
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 4%

---

# 在 Insight 和中繼器之間建立連線{#creating-a-connection-between-insight-and-repeater}

如果網路防火牆無法阻止Insight電腦存取中繼器伺服器，您可以在中繼器伺服器與Insight之間建立連線，以便您能使用Insight管理中繼器伺服器。

**在中繼器伺服器 [!DNL Insight] 之間建立連線**

1. 在[!DNL Insight]中，在[!DNL Admin]標籤上，按一下&#x200B;**[!UICONTROL Configure Connections to Servers]**&#x200B;縮圖以開啟「設定與伺服器的連線」工作區。
1. 在[!DNL Insight.cfg]窗口中，按一下右鍵&#x200B;**[!UICONTROL Servers]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Server]**。
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
   <td colname="col2">（選用）您要此<span class="keyword"> Insight</span>用來在其使用者介面中呈現中繼器伺服器的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <p>中繼器伺服器的主機名稱或數值IP位址。 </p> <p>範例：<span class="filepath">中繼器.mycompany.com</span>或192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL用戶端憑證 </td> 
   <td colname="col2"> <p>選用，除非您有多個憑證。 包含此<span class="keyword"> Insight</span>副本數位憑證的檔案名稱。 （這是您在安裝<span class="keyword"> Insight</span>時下載的檔案。） </p> <p>範例：<span class="filepath">薩曼莎·史密斯.pem</span></p> <p>若將此參數留空，<span class="keyword"> Insight</span>會使用任何憑證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL伺服器 </p> <p>公用名稱 </p> </td> 
   <td colname="col2">指派給中繼器伺服器的通用名稱。 此名稱必須符合在其授權憑證中指派給中繼器伺服器的一般名稱。 如果您有權訪問中繼器的證書檔案(<span class="filepath"> Certificates\server_cert.pem</span>)，則可以使用Notepad等文本編輯器開啟該檔案來查找公共名稱。 在憑證的CN欄位中識別通用名稱。 </td> 
  </tr> 
 </tbody> 
</table>

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存檔案。 [!DNL Insight] 會嘗試使用您指定的設定連線至中繼器伺服器。如果已建立連接，[!DNL Servers Manager]介面中將顯示綠色的伺服器表徵圖。 如果無法建立連接，則會顯示紅色表徵圖。

   有關[!DNL Servers Manager]介面的詳細資訊，請參閱* [!DNL Insight]使用手冊*。
