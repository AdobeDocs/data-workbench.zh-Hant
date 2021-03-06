---
description: 本節將說明Saint Scrubber指令碼。
title: SAINT Scrubber的指令碼
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# SAINT Scrubber的指令碼{#scripting-for-the-saint-scrubber}

本節將說明Saint Scrubber指令碼。

## SAINT分類概觀 {#section-b840a99f10684bb4b58e844a515d0d79}

SiteCatalyst屬性匯入與命名工具的首字母縮寫SAINT也稱為分類。

當我們「分類」SiteCatalyst變數時，您會建立與該變數相關的變數與中繼資料之間的關係。 分類最常用於促銷活動區域，因此我會使用它來解釋。 大部分客戶會使用追蹤代碼將促銷活動流量傳送至其網站。 此追蹤代碼是可能代表在Google上購買之特定關鍵字的識別碼，例如「goog123」。 此識別碼會傳入s.campaigns變數中，以便您查看訪客從該促銷活動代碼進入您的網站後發生的網站成功事件。

但是，如果您不只是透過追蹤代碼檢視促銷活動，而是想透過搜尋引擎、關鍵字或促銷活動渠道查看促銷活動結果，該怎麼辦？ 您是否必須為搜尋引擎建立新的轉換變數、關鍵字的另一個變數，以及促銷活動渠道的另一個變數？ 若是，您將僅使用促銷活動上的50個變數中的許多變數！ 幸好，您可以使用「分類」，讓生活更輕鬆！ 由於每個追蹤代碼都可能有搜尋引擎、關鍵字或促銷活動渠道，因此您只需建立三個促銷活動變數的「分類」即可代表每個。 實際上，您是在告訴SiteCatalyst,「促銷活動」變數與這三個其他「中繼資料」值之間有直接關係。 如此一來，SiteCatalyst將允許您依據所有四個變數切割網站「成功事件」，毋需加上標籤。

## DWB中的SAINT Scrubber指令碼 {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

當您將任何SAINT分類資料匯入DWB時，就會使用此指令碼。 指令 *碼SaintScrubber.dat* 通常位於 *FSU的\Scripts\Scripository* folder下方。

此指令碼的主要用途是移除 `<discoiqbr>` SAINT分類檔案中的標題。 此外，如果欄標題行中提及的欄並檢查所有資料行，則會計算數字。 如果存在列數少於或多於列的行，則從檔案中刪除這些行。

SaintScrubber.dat ** 會在內部呼叫*saint_scrubber.pl *script。 以下是此指令碼檔案的詳細資訊：

路徑： *E:\Scripts\Scripository\Library\Perl*

指令碼引數：

1. 輸入資料夾（必要）:source_directory
1. 輸出資料夾（必填）:destination_directory
1. 分隔字元（必填）:分隔字元
1. 拒絕資料夾（可選）（參數可以保留為空白或在命令行中忽略）
1. 日誌資料夾（可選）（參數可以保留為空或在命令行中省略）

在Perl指令碼中執行的步驟：

1. 以空格取代逸出的表單摘要、新行、歸位、標籤。
1. 移除在UTF-8 BMP（基本多語言平面）中被解譯為控制字元的雙位元組，但下列除外：

   * 9個水準標籤
   * 10行饋送
   * 12份表單摘要
   * 13節回車
   * 使用垂直號關鍵字作為分隔字元| eg:分隔字管
   * 移除其他麻煩的字元
   * 在上述清除後，會拖放與第一行不同的欄數行（非空白或註解）
   * 支援選用的拒絕檔案，以保留拒絕的行，而不是只跳過這些行
   * 支援遞歸輸入資料夾；生成同一結構的輸出資料夾
   * 將已處理的輸入檔案移動到已處理的子資料夾，這樣，當指令碼在同一個現有輸入資料夾上再次運行時，指令碼不會重複執行
   * 識別工作台檔名中的日期；先依日期排序處理，再依字母排序——不論檔案夾名稱。 無論工作台檔案類型（ecom、非ecom）或報表套裝ID（如果您要將多個報表套裝處理成單一Insight資料集），這都可確保順序正確。
   * 支援電子郵件警報 `<discoiqbr>`

