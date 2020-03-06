---
description: 設定查詢API的快速指南。
title: 查詢API設定
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 查詢API設定{#query-api-setup}

設定查詢API的快速指南。

請依照下列步驟來設定查詢API:

1. 查詢API憑證贏取

   傳送電子郵件給Adobe電子郵件的Tech Ops團隊- `Dataworkbench@adobe.com`。

   請提供您要用於查詢API的CN名稱(提供一般名稱，如查詢 `<Client>` API)。

   >[!NOTE]
   >
   >Tech Ops將產生憑證並上傳至URL。 收到Tech Ops有關成功產生票證的通知後，請讓Adobe顧問知道，如此票證就會由他們寄回給您。

1. 下載和擷取API特效。 從您的顧問處收到api特定檔案。

   確保Perl已安裝在您的電腦上。

   在擷取的檔案夾（您複製檔案的檔案夾路徑）中，將您的Query API憑證複製到Stunnel檔 *案夾* 。

1. 設定Stunnel.conf

   Stunnel資料夾中(您復 *制憑證的位置* )應有一個名為 ** stunnel.conf的檔案。

   在記事本中編輯檔案。

   ![](assets/dwb_impl_API1.png)

   更改參數如下： ![](assets/dwb_impl_API2.png)

   此檔案中需要更改兩個參數。

   * *Cert* =證書上的名稱。 在此範例中，它是Aadhithya Ramani QAPI Client.pem。
   * *Connect* =您主要DPU的伺服器名稱。

1. 複製 *Query.pm*。

   Query.pm ** 檔案將可在Insight API資料夾中使用。

   複製 *Query.pm* 檔案並將其貼上到Perl庫資料夾(通常為*C:\Perl64\lib *，但檢查Perl在電腦中的安裝位置)。

1. 修改 *api-http.pl檔案*

   api-http.pl檔案將可在api-stunnel檔案夾中使用。

   只要修改一個參數

   *我的$profile* =您要設定查詢API的描述檔名稱。

1. 安裝查詢API。

   在系統中以「管理員」的身份開啟命令提示符，並導航到解壓特效的目 *錄* ，如所示： ![](assets/dwb_impl_API3.png)

   執行以下命令 *.\stunnel -install*。 ![](assets/dwb_impl_API4.png)

   執行命令後，會出現一個窗口，指 *出安裝了* stunnel。

   >[!NOTE]
   >
   >執行命令後，會出現一個窗口，指 *出安裝了* stunnel。

1. 測試查詢API特效配置

   此程式的最後步驟是測試查詢API設定。 在用於安裝api-stunnel目錄的命令提示符下。 ![](assets/dwb_impl_API5.png)

   使用以下命令* perl api-http.pl*運行該資料夾中可用的Perl指令碼。 ![](assets/dwb_impl_API6.png)

   執行指令碼後，結果應會像下方的螢幕擷取(結果中的日期時間和值會依您設定查詢API的描述檔中的截止時間和其他參數而異（在步驟6）。 ![](assets/dwb_impl_API7.png)

