---
description: 報表集必須以特定方式設定，才能產生可透過Report Portal正確顯示的報表。
title: 自訂 Report Portal 使用者介面
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# 自訂 Report Portal 使用者介面{#customize-the-report-portal-user-interface}

{{eol}}

報表集必須以特定方式設定，才能產生可透過Report Portal正確顯示的報表。

的使用者介面 [!DNL Report Portal] 設計為顯示每個報表集資料夾的索引標籤，該資料夾會顯示在輸出目錄中，並列於 [!DNL profiles.xml] 檔案，以及內建 [!DNL Admin] 索引標籤，必須新增至 [!DNL TopNavigation.xml] 檔案。 如需有關顯示內建的 [!DNL Admin] 標籤，請參閱 [將輸出資料夾連結到用戶中的頁簽……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [確保您的報表集與Report Portal相容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [將輸出資料夾連結到用戶中的頁簽……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## 確保您的報表集與Report Portal相容 {#section-2b141e5d198a4bbea455699126c24706}

報表集定義 [!DNL Report]. 它包含兩個項目：

* 定義您要的工作區集合的資料夾 [!DNL Report] 以產生為報表。
* 配置檔案( [!DNL Report.cfg])。

除其他事情外， [!DNL Report.cfg] 檔案通知 [!DNL Report] 何時生成報告以及在何處保存輸出檔案。 報表集位於Data Workbench伺服器上的「報表」資料夾中。 設定檔可顯示任意數量的報表集。

確保與 [!DNL Report Portal]，您的報表集必須符合下列要求：

* 報表集的輸出目錄必須包含已設定的 [!DNL profiles.xml] 檔案。
* 每個報表集都必須包含名為「*ReportSetName* 摘要，」其中 *ReportSetName* 符合報表集的名稱。 例如，下列 [!DNL Profile Manager] 顯示兩個報表集：「首頁」和「流量」。 請注意，每個報表集定義摘要報表( [!DNL Home Summary.vw] 和 [!DNL Traffic Summary.vw]，分別)。

![](assets/rptPort_scrn_RptSets.png)

在 [!DNL Report Portal]，則摘要報表會顯示在報表集的標籤上。 摘要報表可包含您選擇的任何工作區、視窗或視覺效果。

* 摘要報表必須是報表集頂層資料夾中的唯一報表。 所有其他報表都必須放在子資料夾中。 如果將其他報表放在頂層資料夾中，則無法透過入口網站檢視。

## 將輸出資料夾連結到用戶介面中的頁簽 {#section-3f6bc47d37ed448e871f4f685f46acee}

指定要的頁簽 [!DNL Report Portal] 若要顯示，您必須設定 [!DNL TopNavigation.xml] 檔案。 此檔案會決定在特定設定檔的使用者介面中，哪些報表集會顯示為索引標籤，以及這些索引標籤的順序。 此 [!DNL TopNavigation.xml] 檔案位於\*PortalName*\PortalFiles\Core\TopNav\*profileName*資料夾中。

**要編輯TopNavigation.xml檔案**

1. 在運行IIS的電腦上，開啟 [!DNL TopNavigation.xml] 檔案（如記事本）。
1. 編輯 `<TopNav>` 元素，以定義您要輸出之報表集的名稱和順序 [!DNL Report Portal] 顯示，如下例所示：

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
   >此 [!DNL Admin] 標籤是內建的標籤，可提供其他功能。 若您未將其納入 [!DNL TopNavigation.xml] 檔案中，此索引標籤不會顯示，且其功能無法使用。

1. 在\*PortalName*\PortalFiles\Core\TopNav\ folder中，為下一個配置檔案建立資料夾。
1. 複製 [!DNL TopNavigation.xml] 檔案，並貼到新資料夾中。
1. 編輯 [!DNL TopNavigation.xml] 視需要，儲存檔案。
1. 對入口網站中提供的所有其他設定檔重複步驟3-5。
