---
description: 已為每個應用程式建立一組標準配置檔案，以允許在任何給定時間安裝一個或多個配置檔案。
title: 基線設定檔
uuid: ff76ff7e-ccde-4d99-9109-8612a4a83183
exl-id: f1bd5c1d-5f79-4b8c-9928-97169d553631
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# 基線設定檔{#baseline-profiles}

已為每個應用程式建立一組標準配置檔案，以便在任何給定時間安裝一個或多個配置檔案。

這些基線設定檔包含標準量度、維度、篩選器、報表、工作區和控制面板的定義。 Adobe不斷更新這些配置檔案，並通過其軟體支援計畫向其授權廠商提供這些配置檔案。 此外，Adobe應用程式的使用者可以定義其他設定檔，並搭配或使用，而非Adobe提供的設定檔。

設定檔管理系統允許由較高層級的設定檔來覆寫設定檔的設定。 當您想在安裝這些設定檔後覆寫這些設定檔中納入的任何定義時，請使用此功能。 安裝這些設定檔的新版本將會覆寫任何舊版。 因此，安裝新設定檔時，會直接覆寫對這些設定檔所做的任何變更。

垂直市場或特定類型的公司或產業的設定檔也可從AdobeClientCare取得。 以下是基線設定檔的說明：

* **基本設定檔**&#x200B;包含隨Insight Server提供的組態檔。 用戶或管理員不應修改基本配置檔案。 當Adobe發行下一版Insight Server或其他軟體應用程式時，在基本設定檔中所做的任何變更都可能會遭到覆寫。
* **流量設定檔**&#x200B;包含一組基本量度、維度，以及網頁分析的篩選器。 它也包含範本工作區、報表和控制面板，可協助您分析、報告網際網路網站活動整體趨勢和模式，以及全面了解這些趨勢和模式。 此設定檔可搭配基準安裝Site運作「立即可用」。
* **值設定檔**&#x200B;包含一組與內建網站業務值和轉換模型相關聯的量度、維度和範本工作區、報表及控制面板。 此設定檔可讓使用者識別網站上的值事件，並將貨幣值與這些事件建立關聯。

   此設定檔提供「業務值模型」，這是一種進階方法，可測量及追蹤網站產生的值量，借此擴充您的網站分析功能。 值事件及其相對值是透過Site內簡易的拖放介面來定義。 網站使用這些定義來計算每個工作階段產生的業務值，而此資訊則用來定義量度，例如值、值事件、轉換等。 這些量度可讓您回答下列問題：

   * 通過該站點獲利最多的路徑是什麼？
   * 哪個反向連結或促銷活動產生的值最多？
   * 網站每天的平均購買次數為何？ （平均每天發生多少個值事件？）

   在網站中定義了業務價值模型後，您就可以在分析中使用值量度和維度。

* **行銷設定檔**&#x200B;包含與分析網際網路行銷活動相關的量度與維度、範本工作區、報表及控制面板集，包括搜尋分析和延伸反向連結分析。

Adobe也提供下列要使用的選用設定檔：

* **IP地理位置設定檔**&#x200B;包含與根據Quova, Inc.提供給Adobe的IP地理位置資料分析訪客位置相關的維度和層檔案，並整合至Data Workbench。
* IP地理情報設定檔包含與根據Digital Envoy, Inc.提供給Adobe的IP地理情報資料來分析訪客位置相關的維度和層檔案，並整合至Data Workbench。

如需IP地理位置和IP地理情報設定檔的相關資訊，請聯絡您的Adobe支援人員。 以下各節將說明每個基線設定檔中定義的量度和維度。
