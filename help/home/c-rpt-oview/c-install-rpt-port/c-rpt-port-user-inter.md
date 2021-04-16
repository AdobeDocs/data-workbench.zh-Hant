---
description: 必須以特定方式設定報表集，才能產生透過報表入口網站正確顯示的報表。
title: 自訂 Report Portal 使用者介面
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# 自訂 Report Portal 使用者介面{#customize-the-report-portal-user-interface}

必須以特定方式設定報表集，才能產生透過報表入口網站正確顯示的報表。

[!DNL Report Portal]的用戶介面設計為顯示輸出目錄中顯示的、列在[!DNL profiles.xml]檔案中的每個報告集資料夾的頁籤，以及必須添加到要顯示的[!DNL TopNavigation.xml]檔案的內置[!DNL Admin]頁籤。 有關顯示內置[!DNL Admin]頁籤的詳細資訊，請參閱[將輸出資料夾連結到用戶中的頁籤……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)。

![](assets/report_portal_home.png)

* [確保您的報表集與報表入口網站相容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [將輸出資料夾連結到用戶中的頁籤……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## 確保您的報表集與報表入口網站{#section-2b141e5d198a4bbea455699126c24706}相容

報表集定義[!DNL Report]的排程工作。 它包含兩個項目：

* 一個資料夾，它定義要[!DNL Report]生成為報告的工作區集合。
* 配置檔案([!DNL Report.cfg])。

此外，[!DNL Report.cfg]檔案會告訴[!DNL Report]何時產生報表，以及儲存輸出檔案的位置。 報表集位於資料工作台伺服器上的「報表」資料夾中。 描述檔可顯示任意數目的報表集。

為確保與[!DNL Report Portal]相容，您的報表集必須符合下列要求：

* 報表集的輸出目錄必須包含已設定的[!DNL profiles.xml]檔案。
* 每個報表集都必須包含名為&quot;*ReportSetName*&#x200B;摘要&quot;的頂層報表，其中&#x200B;*ReportSetName*&#x200B;與報表集的名稱相符。 例如，下列[!DNL Profile Manager]顯示兩個報表集：「首頁」和「流量」。 請注意，每個報表集分別定義摘要報表（[!DNL Home Summary.vw]和[!DNL Traffic Summary.vw]）。

![](assets/rptPort_scrn_RptSets.png)

在[!DNL Report Portal]中，摘要報表會顯示在報表集的標籤上。 摘要報表可包含您選擇的任何工作區、視窗或視覺化。

* 摘要報表必須是報表集頂層資料夾中唯一的報表。 所有其他報表都必須放在子檔案夾中。 如果您將其他報表置於頂層檔案夾中，則無法透過入口網站檢視。

## 將輸出資料夾連結到用戶介面{#section-3f6bc47d37ed448e871f4f685f46acee}中的頁籤

要指定要顯示[!DNL Report Portal]的頁籤，必須為每個配置檔案配置[!DNL TopNavigation.xml]檔案。 此檔案會決定哪些報表集在特定描述檔的使用者介面中顯示為標籤，以及這些標籤的順序。 [!DNL TopNavigation.xml]檔案位於\*PortalName*\PortalFiles\Core\TopNav\*profileName*資料夾中。

**若要編輯TopNavigation.xml檔案**

1. 在運行IIS的電腦上，在文本編輯器（如記事本）中開啟[!DNL TopNavigation.xml]檔案。
1. 編輯`<TopNav>`元素的清單，以便定義要顯示[!DNL Report Portal]輸出的報表集的名稱和順序，如下例所示：

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
   >[!DNL Admin]標籤是內建標籤，提供其他功能。 如果您未將它包含在[!DNL TopNavigation.xml]檔案中，則不會顯示此標籤，且其功能無法使用。

1. 在\*PortalName*\PortalFiles\Core\TopNav\ folder中，為您的下一個描述檔建立檔案夾。
1. 從第一個配置檔案資料夾複製[!DNL TopNavigation.xml]檔案並將其貼上到新資料夾中。
1. 視需要編輯[!DNL TopNavigation.xml]，然後儲存檔案。
1. 對入口網站中所有其他可用的設定檔重複步驟3-5。
