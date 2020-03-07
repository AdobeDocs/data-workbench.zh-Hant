---
description: 必須以特定方式設定報表集，才能產生透過報表入口網站正確顯示的報表。
solution: Analytics
title: 自訂報表入口網站使用者介面
topic: Data workbench
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 自訂報表入口網站使用者介面{#customize-the-report-portal-user-interface}

必須以特定方式設定報表集，才能產生透過報表入口網站正確顯示的報表。

的用戶介面 [!DNL Report Portal] 設計為顯示輸出目錄中顯示的、列在檔案中的每個報告集資料夾的頁籤，以及必須添加到要顯示的檔案的內置頁籤 [!DNL profiles.xml][!DNL Admin][!DNL TopNavigation.xml] 。 有關顯示內置頁籤的詳細信 [!DNL Admin] 息，請參 [閱將輸出資料夾連結到用戶……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [確保您的報表集與報表入口網站相容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [將輸出資料夾連結到用戶中的頁籤……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## 確保您的報表集與報表入口網站相容 {#section-2b141e5d198a4bbea455699126c24706}

報表集定義的計畫作業 [!DNL Report]。 它包含兩個項目：

* 定義要生成為報告的工作區集 [!DNL Report] 合的資料夾。
* 配置檔案( [!DNL Report.cfg])。

除其他事項外，檔 [!DNL Report.cfg] 案會告 [!DNL Report] 訴您何時產生報表，以及儲存輸出檔案的位置。 報表集位於資料工作台伺服器上的「報表」資料夾中。 描述檔可顯示任意數目的報表集。

為確保與相容 [!DNL Report Portal]性，您的報表集必須符合下列要求：

* 報表集的輸出目錄必須包含已設定的 [!DNL profiles.xml] 檔案。
* 每個報表集都必須包含名為「*ReportSetName* Summary」的頂層報表，其中 *ReportSetName* 與報表集的名稱相符。 例如，下列顯示 [!DNL Profile Manager] 兩個報表集：「首頁」和「流量」。請注意，每個報表集都會定義摘要報表( [!DNL Home Summary.vw] 分 [!DNL Traffic Summary.vw]別和)。

![](assets/rptPort_scrn_RptSets.png)

在 [!DNL Report Portal]中，摘要報表會顯示在報表集的標籤上。 摘要報表可包含您選擇的任何工作區、視窗或視覺化。

* 摘要報表必須是報表集頂層資料夾中唯一的報表。 所有其他報表都必須放在子檔案夾中。 如果您將其他報表置於頂層檔案夾中，則無法透過入口網站檢視。

## 將輸出資料夾連結到用戶介面中的頁籤 {#section-3f6bc47d37ed448e871f4f685f46acee}

要指定要顯示的頁籤， [!DNL Report Portal] 必須為每個配置檔案 [!DNL TopNavigation.xml] 配置一個檔案。 此檔案會決定哪些報表集在特定描述檔的使用者介面中顯示為標籤，以及這些標籤的順序。 檔 [!DNL TopNavigation.xml] 案位於\*PortalName*\PortalFiles\Core\TopNav\*profileName*資料夾中。

**若要編輯TopNavigation.xml檔案**

1. 在運行IIS的電腦上，在文本編輯器( [!DNL TopNavigation.xml] 如記事本)中開啟檔案。
1. 編輯元素 `<TopNav>` 清單，以定義要顯示其輸出的報表集的名稱 [!DNL Report Portal] 和順序，如下例所示：

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <TOPNAV_ELEMENTS>
   <TOPNAV>
       <NAME>Monthly Web</NAME>
     </TOPNAV>
     <TOPNAV>
       <NAME>Weekly Web</NAME>
     </TOPNAV>
   <TOPNAV> 
         <NAME>Admin</NAME> 
     </TOPNAV>
   </TOPNAV_ELEMENTS>
   ```

   >[!NOTE]
   >
   >此標 [!DNL Admin] 簽是內建的標籤，提供其他功能。 如果您未將它包含在檔案中， [!DNL TopNavigation.xml] 則不會顯示此標籤，且其功能無法使用。

1. 在\*PortalName*\PortalFiles\Core\TopNav\ folder中，為您的下一個描述檔建立檔案夾。
1. 從第一 [!DNL TopNavigation.xml] 個描述檔資料夾複製檔案，並貼到新資料夾。
1. 視需要 [!DNL TopNavigation.xml] 編輯，然後儲存檔案。
1. 對入口網站中所有其他可用的設定檔重複步驟3-5。

