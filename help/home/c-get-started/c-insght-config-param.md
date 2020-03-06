---
description: 在Insight.cfg檔案中設定參數，以指定您的網路連線和資料工作台組態設定。
solution: Analytics
title: 配置參數
topic: Data workbench
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置參數{#configuration-parameters}

在Insight.cfg檔案中設定參數，以指定您的網路連線和資料工作台組態設定。

以下示例預設情況下僅包含檔案中 [!DNL Insight.cfg] 包含的參數。

**新版面檢視**

![](assets/config_tree_new_layout.png)

**原始版面檢視**

![](assets/cfg_Workstation_AddServer.png)

新檔案中的部分可用參 [!DNL Insight.cfg] 數可能不適用於您的檔案版 [!DNL Insight.cfg] 本。 如果需要其中一個參數，則必須使用 [!DNL Insight.cfg] 參數 [!DNL Add Custom Key]，按一下右鍵參數，然後指定名稱和類型將其添加到檔案中。 您也可以使用文字編輯器開啟 [!DNL .cfg] 檔案（位於「資料工作台」安裝目錄），以新增參數。

以下是可用於檔案的所有可用參數的示例， [!DNL Insight.cfg] 可用作添加參數項的模型：

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

下表按字母順序說明可用 [!DNL Insight.cfg] 的檔案參數。

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
   <td colname="col2"> <p>資料工作台伺服器電腦的主機名稱或數值IP位址。 </p> <p>範例： <span class="filepath"> vsServer.mycompany.com或192.168.1.90</span> </p> <p>如果未 <span class="wintitle"> 指定Address</span><span class="keyword"></span> ，則當「使用地址檔案」設定為false時，客戶端使用在SSL Server Common Name參數中指定的公用名稱。 </p> <p> <p>注意：如果「使用地址檔案」參數設定為true，則在客戶端上開啟第一個配置檔案後，可以刪除在「地址」參數中輸入的 <span class="keyword"> 文本</span>。 然後，網路位置參數的設定將確定用於連接到主伺服器的群集地址檔案中的哪些地址。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>顏色集 </p> </td> 
   <td colname="col2"> <p>指定用戶端應用程式的 <span class="keyword"> 背景顏色</span>。 選項如下： </p> <p>0 =黑色 </p> <p>1 =白色 </p> <p>2 =單色 </p> <p>預設值為0，黑色。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>預設線上層級 </p> </td> 
   <td colname="col2"> <p>選填。可讓您在資料工作台每次開啟時，依預設讓其執行個體以串流、離線或線上方式運作。 選項包括「串流」、「線上」或「離線」。 「資料工作台」的預設設定是「離線工作」。 </p> <p> <p>注意：在決定依預設線上工作之前，請務必權衡「離線工作」和「線上工作」中概述的 <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> 優點和後果</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字型 </p> </td> 
   <td colname="col2"> <p>選填。列出用戶端用來 <span class="keyword"> 轉換</span> UTF8型Unicode特殊字元的字型的向量。 清單中的字型數目不受限制。 </p> <p>第一個字型應始終為Lucida Sans Console。 如果此參數未包含在 <span class="filepath"> Insight.cfg檔案中</span> ，資料工作台僅使用Lucida Sans主控台來顯示文字。 </p> <p> 「資料工作台」會使用清單中的第一個字型來轉換所有字元，直到遇到無法轉換的字元為止。 它會使用清單中的第二個字型來轉換該字元。 如果該字型未轉譯字元，「資料工作台」會使用清單中的第三種字型來轉譯該字元等，直到字型清單結尾為止。 如果向量中未列出正確的字型，資料工作台會顯示字元的十六進位值。 </p> <p> <p>注意： 在「資料工作台」執行時，請勿變更此參數。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> 顯示「資料工作台」的Gamma設定。 預設值為1.6。Adobe不建議變更此值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>授權 </p> </td> 
   <td colname="col2"> <p>選填。您必須透過代理伺服器聯絡Adobe的授權伺服器，才能修改授權向量中的參數。 </p> <p>讓您的用戶端透過代理伺服 <span class="keyword"> 器</span> ，與Adobe License Server聯絡之參數的區段識別碼。 展開「授權」節點並完成下列參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理地址 </p> </td> 
   <td colname="col2"> <p>選填。用戶端存取Adobe授權伺服 <span class="keyword"> 器時</span> ，必須使用的代理伺服器位址。 </p> </td> 
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
   <td colname="col2"> <p>選填。與Proxy使用者名稱關聯的密碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最大樣本大小(MB) </p> </td> 
   <td colname="col2"> <p>指定在單台電腦上運行的客戶端在資料快取 <span class="keyword"> 中使用</span> 的最大大小。 </p> <p>雖然 <span class="filepath"></span><span class="keyword"></span> Server.cfg檔案中的「範例位元組」參數指定連線至資料工作台伺服器的所有用戶端的資料快取大小（預設為250e6位元組），但「最大範例大小」參數可讓您進一步限制特定電腦的資料快取大小。 當客戶機安裝在儲存或計算能力有限的電腦上時，此功能很實用。 </p> <p> <p>注意：此參數限制客戶端程式本地查詢的本地資料樣本的大小。 相反地， <span class="filepath"> cache.db</span> 檔案包含客戶機所連接的每個配置檔案的資料，以及元素名稱及其維。 執行本機查詢時， <span class="filepath"> cache.db檔案中的這些元素名稱</span> 和維度是必要的。 因此，除了減少資料集中的元素數目外，沒有其他方法可限制其大小。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名稱 </p> </td> 
   <td colname="col2">選填。客戶機用 <span class="keyword"> 於標識伺服器</span> 的名 <span class="keyword"> 稱</span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路位置 </p> </td> 
   <td colname="col2"> <p>選填。客戶端用於將「數 <span class="keyword"> 據工作台</span> 」伺服器公用名稱解析為IP地址的網路位置。 可用網路位置在伺服器上的地址檔案中定義。 如需詳細資訊，請參 <i>閱伺服器產品安裝與管理指南</i>。 </p> <p>如果您未指定網路位置，用戶端 <span class="keyword"> 會使用預設網路位置</span> 「Insight」解析常用名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>連接埠 </p> </td> 
   <td colname="col2"> <p>客戶端發送請 <span class="keyword"> 求的端</span> 口。 此埠號必須與資料工作台伺服器監聽請求的埠相符。 對於安全連接，此值通常為443。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理地址 </p> </td> 
   <td colname="col2"> <p>如果需要代理伺服器才能連接到資料工作台伺服器電腦，則至少必須完成此參數和代理埠參數。 您可以選擇性地完成「代理用戶名」和「代理用戶密碼」參數。 </p> <p>用戶端用來存取資料工作台 <span class="keyword"> 伺服器</span> ，所使用之代理伺服器的位址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代理密碼 </p> </td> 
   <td colname="col2"> <p>選填。代理伺服器的口令。 </p> </td> 
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
   <td colname="col2"> <p>在 <span class="filepath"> Insight.cfg</span> (或任何 <span class="filepath"></span> .cfg檔案)中，您可以依索引鍵名稱、索引鍵類型或值來搜尋，以快速找到項目，以移除捲動擴充大型檔案以取得巢狀資訊的需要。 可以找到維名、伺服器名等。 </p> <p>在此欄位中輸入搜尋片語以找出資料。 欄位的色彩會隨著比對的成功而改變。 相符項目會反白顯示，非相符項目則會暗顯。 如果沒有相符項目，搜尋欄位的背景會變成紅色。 按Enter鍵時，配置樹將展開存在匹配的每個位置，並折疊不匹配的位置。 </p> <p>您也可以在「搜尋」欄位中使用規則運 <span class="wintitle"> 算式</span> 。 例如，您可以使用re: <span class="filepath"> *zip。*</span> ：任何包含"zip"的項目。 </p> <p>要清除搜索，請按 <span class="uicontrol"> Escape</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器 </p> </td> 
   <td colname="col2"> <p>用於客戶端到服 <span class="keyword"> 務器</span> 連接 <span class="keyword"> 的向量標題</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL用戶端憑證 </p> </td> 
   <td colname="col2"> <p>選用，除非您有多個憑證。 包含此資料工作台副本之數位憑證的檔案名稱。 這是您在「下載並安裝數位憑證」中下載的檔案。 </p> <p>範例：薩 <span class="filepath"> 曼莎·史密斯</span> </p> <p>如果將此參數留空，則客 <span class="keyword"> 戶端會使用</span> 任何存在的憑證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL伺服器通用名稱 </p> </td> 
   <td colname="col2"> <p>資料工作台伺服器的公用名稱（在其數位憑證上指派）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工具列圖示 </p> </td> 
   <td colname="col2"> <p>False會關閉工作站使用者介面中的圖示，並在工具列中顯示文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用地址檔案 </p> </td> 
   <td colname="col2"> <p>指定地址檔案中的任何設定是否覆蓋地址參數設定。 選項是true或false。 如果設定為true，則地址檔案中的設定（如果存在）將覆蓋「地址」參數設定。 預設值為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用SSL </p> </td> 
   <td colname="col2">指定SSL是否用於資料工作台伺服器與用戶端之間的安全 <span class="keyword"> 通訊</span>。 選項是true或false。 預設值為true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>全部取消隱藏 </p> </td> 
   <td colname="col2"> <p>選填。可讓您暫時取消隱藏使用下列任何功能所隱藏的所有量度、維度和篩選器： 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">[Exclusive]在order.txt <span class="filepath"> 檔案中設定</span> </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">order.txt檔案 <span class="filepath"> 中的隱藏選項</span> 。 </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">在。metric <span class="filepath"> 、</span>.dim和。filter檔案中顯示 <span class="filepath"> 參數</span><span class="filepath"></span> 。 </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Transformation.cfg檔案中 <span class="filepath"> 的隱藏參數</span> 。 </li> 
     </ul> </p> <p>如需這些方法的詳細資訊，請參閱 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> 隱藏功能表項目</a>。 </p> <p>選項是true或false。 預設設定為false。 將此參數變更為true，可暫時取消隱藏的量度、維度和篩選。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>解除鎖定 </p> </td> 
   <td colname="col2"> <p>選填。指定是否允許解鎖鎖定的工作區。 選項是true和false。 True可讓您解除鎖定任何鎖定的工作區，而False則不會解除鎖定。 預設值為 false。有關鎖定工作區的詳細資訊，請參 <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> 閱解鎖工作區</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新軟體 </p> </td> 
   <td colname="col2"> <p>選填。指定是否允許 <span class="keyword"> 由 </span>資料工作台伺服器更新客戶端軟體。 選項是true或false。 預設值為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用戶資料夾 </p> </td> 
   <td colname="col2"> <p>選填。指定包含每個配置檔案的任何工作區、度量、維或配置檔案的本地副本的資料夾的名稱和位置。 預設設定為User\\，它會指定「資料工作台」安裝目錄中的「使用者」資料夾。 </p> <p>當兩個用戶共用同一台電腦時，更改此設定很有用。 若要容納兩個使用者，您可以指定兩個使用者都可存取的共用資料夾。 </p> </td> 
  </tr> 
 </tbody> 
</table>

