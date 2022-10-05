---
description: 在Insight.cfg檔案中設定參數，以指定您的網路連線和Data Workbench組態設定。
title: 組態參數
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 2%

---

# 組態參數{#configuration-parameters}

{{eol}}

在Insight.cfg檔案中設定參數，以指定您的網路連線和Data Workbench組態設定。

下列範例僅包含 [!DNL Insight.cfg] 檔案。

**新版面檢視**

![](assets/config_tree_new_layout.png)

**原始版面檢視**

![](assets/cfg_Workstation_AddServer.png)

新增的 [!DNL Insight.cfg] 檔案可能在您的 [!DNL Insight.cfg] 檔案。 如果需要其中一個參數，您必須將其新增至 [!DNL Insight.cfg] 使用 [!DNL Add Custom Key]，方法是按一下右鍵參數，然後指定名稱和類型。 您也可以開啟 [!DNL .cfg] 檔案(位於Data Workbench安裝目錄中)。

以下是適用於 [!DNL Insight.cfg] 可用作添加參數條目模型的檔案：

```
Licensing = serverInfo:
  Proxy Address = string: 
  Proxy Port = int: 8080
  Proxy User Name = string: 
  Proxy Password = string: 
Servers = vector: 1 items
  0 = serverInfo: 
    Address = string: VS02
    Name = string: Insight Server
    Port = int: 443
    Proxy Address = string: 
    Proxy Password = string: 
    Proxy Port = int: 8080
    Proxy User Name = string: 
    SSL Client Certificate = string: Named User.pem
    SSL Server Common Name = string: VS02
    Use Address File = bool: false
    Use SSL = bool: true
Color Set = int: 0
Default to Online = bool: false
Fonts = vector: 0 items
Gamma = float: 1.6
Maximum Sample Size (MB) = double: 0
Network Location = string: 
Unhide All = bool: false
Unlock = bool: false
Update Software = bool: true
User Folder = string: User\\
Toolbar Icons = bool: false
```

下表提供可用 [!DNL Insight.cfg] 檔案參數的字母順序。

<table id="table_4465713A08B649E280A3B4840E829518"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>地址 </p> </td> 
   <td colname="col2"> <p>Data Workbench伺服器電腦的主機名或數值IP地址。 </p> <p>範例： <span class="filepath"> vsServer.mycompany.com或192.168.1.90</span> </p> <p>若 <span class="wintitle"> 地址</span> 未指定， <span class="keyword"> 客戶</span> 當「使用地址檔案」設為false時，使用在SSL伺服器公用名稱參數中指定的公用名稱。 </p> <p> <p>注意：如果「使用地址檔案」參數設定為true，則在開啟第一個配置檔案後，可刪除在「地址」參數中輸入的文本 <span class="keyword"> 客戶</span>. 然後，網路位置參數的設定將確定群集的地址檔案中用於連接到主伺服器的地址。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>色彩集 </p> </td> 
   <td colname="col2"> <p>指定背景顏色 <span class="keyword"> 客戶端應用程式</span>. 選項如下： </p> <p>0 =黑色 </p> <p>1 =白 </p> <p>2 =單色 </p> <p>預設值為0，黑色。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>預設聯機級別 </p> </td> 
   <td colname="col2"> <p>選填。可讓您在Data Workbench執行個體每次開啟時，依預設以串流、離線或線上方式運作。 選項包括串流、線上或離線。 Data Workbench的預設設定是離線工作。 </p> <p> <p>注意：在決定預設線上工作之前，請務必權衡 <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> 離線和線上工作</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字型 </p> </td> 
   <td colname="col2"> <p>選填。列出字型的向量 <span class="keyword"> 客戶</span> 應使用來轉譯以UTF8為基礎的Unicode特殊字元。 清單中的字型數量不限。 </p> <p>第一個字型應始終為Lucida Sans Console。 如果此參數未包含在 <span class="filepath"> Insight.cfg</span> 檔案中，Data Workbench僅使用Lucida Sans控制台來顯示文本。 </p> <p> Data Workbench使用清單中的第一個字型來呈現所有字元，直到遇到無法呈現的字元為止。 它會使用清單中的第二個字型來轉譯該字元。 如果該字型未呈現字元，則Data Workbench會使用清單中的第三個字型來呈現該字元，以此類推，直到它到達字型清單的結尾。 如果向量中未列出正確的字型，Data Workbench將顯示字元的十六進位值。 </p> <p> <p>注意：Data Workbench執行時請勿變更此參數。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Data Workbench顯示的Gamma設定。 預設值為1.6。Adobe不建議變更此值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>授權 </p> </td> 
   <td colname="col2"> <p>選填。只有透過代理伺服器連絡Adobe的授權伺服器時，才需要修改授權向量中的參數。 </p> <p>可讓您 <span class="keyword"> 客戶</span> 通過代理伺服器與Adobe許可證伺服器聯繫。 展開「授權」節點，並完成下列參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理地址 </p> </td> 
   <td colname="col2"> <p>選填。該代理伺服器的地址 <span class="keyword"> 客戶</span> 必須使用來存取Adobe授權伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理埠 </p> </td> 
   <td colname="col2"> <p>選填。代理伺服器的埠。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理用戶名 </p> </td> 
   <td colname="col2"> <p>選填。代理伺服器的用戶名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理密碼 </p> </td> 
   <td colname="col2"> <p>選填。與代理用戶名關聯的密碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最大樣本大小(MB) </p> </td> 
   <td colname="col2"> <p>指定所使用的資料快取中允許的最大大小 <span class="keyword"> 客戶</span> 在一台電腦上運行。 </p> <p>若 <span class="filepath"> Server.cfg</span> 檔案指定所有資料快取的大小 <span class="keyword"> 客戶</span> 連接到Data Workbench伺服器（預設為250e6位元組）時，「最大樣本大小」參數允許您進一步限制特定電腦的資料快取大小。 當客戶端安裝在儲存能力或計算能力有限的電腦上時，這非常有用。 </p> <p> <p>注意：此參數限制客戶端程式本地查詢的本地資料樣本的大小。 相反， <span class="filepath"> cache.db</span> 檔案包含用戶端所連線之每個設定檔的資料，以及元素名稱及其維度。 這些元素名稱和維度 <span class="filepath"> cache.db</span> 運行本地查詢需要檔案。 因此，除了減少資料集中的元素數量之外，沒有其他方法可限制其大小。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名稱 </p> </td> 
   <td colname="col2">選填。名稱 <span class="keyword"> 客戶</span> 用於識別 <span class="keyword"> 伺服器</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路位置 </p> </td> 
   <td colname="col2"> <p>選填。網路位置 <span class="keyword"> 客戶</span> 用於將Data Workbench伺服器的公用名稱解析為IP地址。 可用網路位置在伺服器的地址檔案中定義。 如需詳細資訊，請參閱 <i>《伺服器產品安裝與管理指南》</i>. </p> <p>如果未指定網路位置， <span class="keyword"> 客戶</span> 使用預設網路位置「Insight」解析常見名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>埠 </p> </td> 
   <td colname="col2"> <p>連接的埠 <span class="keyword"> 客戶</span> 傳送要求。 此埠號必須與Data Workbench伺服器監聽請求的埠相匹配。 對於安全連線，通常為443。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理地址 </p> </td> 
   <td colname="col2"> <p>如果需要代理伺服器才能連接到Data Workbench伺服器電腦，則至少必須完成此參數和代理埠參數。 您可以選擇填寫「代理用戶名」和「代理用戶密碼」參數。 </p> <p>該代理伺服器的地址 <span class="keyword"> 客戶</span> 必須使用來存取Data Workbench伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理密碼 </p> </td> 
   <td colname="col2"> <p>選填。代理伺服器的密碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理埠 </p> </td> 
   <td colname="col2"> <p>代理伺服器的埠。 預設值為 8080。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理用戶名 </p> </td> 
   <td colname="col2"> <p>選填。代理伺服器的用戶名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜尋 </p> </td> 
   <td colname="col2"> <p>在 <span class="filepath"> Insight.cfg</span> (或 <span class="filepath"> .cfg</span> 檔案)，您可以依索引鍵名稱、索引鍵類型或值來搜尋以快速找到項目，以移除捲動擴充的大型檔案以取得巢狀資訊的需求。 您可以找到維度名稱、伺服器名稱等。 </p> <p>在此欄位中輸入搜尋片語以尋找資料。 欄位的顏色會隨著比對的成功而改變。 「符合」會反白顯示，而「非符合」則會暗顯。 如果沒有相符項目，搜尋欄位的背景會變成紅色。 按下Enter時，設定樹會展開有相符項目的每個位置，然後折疊沒有相符項目的位置。 </p> <p>您也可以在 <span class="wintitle"> 搜尋</span> 欄位。 例如，您可以使用： <span class="filepath"> *zip。*</span> 任何包含"zip"的項目。 </p> <p>要清除搜索，請按 <span class="uicontrol"> 逸出</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器 </p> </td> 
   <td colname="col2"> <p>向量標題 <span class="keyword"> 客戶</span> to <span class="keyword"> 伺服器</span> 連線。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL用戶端憑證 </p> </td> 
   <td colname="col2"> <p>選用，除非您有多個憑證。 包含此Data Workbench副本數位憑證的檔案名稱。 這是您在下載和安裝數位憑證中下載的檔案。 </p> <p>範例： <span class="filepath"> 薩曼莎·史密斯.pem</span> </p> <p>如果將此參數留空， <span class="keyword"> 客戶</span> 會使用任何憑證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL伺服器公用名稱 </p> </td> 
   <td colname="col2"> <p>Data Workbench伺服器的通用名稱（在其數位憑證上指派）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工具欄表徵圖 </p> </td> 
   <td colname="col2"> <p>False會關閉工作站使用者介面中的圖示，並在工具列中顯示文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用地址檔案 </p> </td> 
   <td colname="col2"> <p>指定地址檔案中的任何設定是否覆蓋地址參數設定。 選項為true或false。 如果設為true，則地址檔案中的設定（如果存在）將覆蓋地址參數設定。 預設值為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用SSL </p> </td> 
   <td colname="col2">指定是否將SSL用於Data Workbench伺服器和 <span class="keyword"> 客戶</span>. 選項為true或false。 預設值為true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>全部取消隱藏 </p> </td> 
   <td colname="col2"> <p>選填。可讓您使用下列任何功能，暫時取消隱藏所有已隱藏的量度、維度和篩選器： 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">[獨佔]設定 <span class="filepath"> order.txt</span> 檔案 </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">隱藏 <span class="filepath"> order.txt</span> 檔案 </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">在中顯示參數 <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>，和 <span class="filepath"> .filter</span> 檔案。 </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">中的隱藏參數 <span class="filepath"> Transformation.cfg</span> 檔案。 </li> 
     </ul> </p> <p>如需這些方法的詳細資訊，請參閱 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> 隱藏菜單項</a>. </p> <p>選項為true或false。 預設設定為false。 將此參數變更為true，即可暫時取消隱藏的量度、維度和篩選器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>解鎖 </p> </td> 
   <td colname="col2"> <p>選填。指定是否允許解鎖鎖定的工作區。 選項為true和false。 True可讓您解除鎖定任何鎖定的工作區，而False則否。 預設值為 false。如需鎖定工作區的詳細資訊，請參閱 <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> 解鎖工作區</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新軟體 </p> </td> 
   <td colname="col2"> <p>選填。指定是否允許此 <span class="keyword"> the </span>由Data Workbench伺服器更新的客戶端軟體。 選項為true或false。 預設值為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者資料夾 </p> </td> 
   <td colname="col2"> <p>選填。指定資料夾的名稱和位置，該資料夾包含每個配置檔案的任何工作區、度量、維或配置檔案的本地副本。 預設設定為User\\，它指定Data Workbench安裝目錄中的User資料夾。 </p> <p>當兩個用戶共用同一台電腦時，更改此設定非常有用。 要容納兩個用戶，您可以指定兩個用戶都有權訪問的共用資料夾。 </p> </td> 
  </tr> 
 </tbody> 
</table>
