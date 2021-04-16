---
description: AdobeData Workbench提供工具和流程，讓您的資料符合通用資料保護法規(GDPR)。
title: GDPR 的 Data Workbench 支援
exl-id: fdc43567-0c57-4851-9073-e295258a8074
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

---

# GDPR 的 Data Workbench 支援

AdobeData Workbench提供工具和流程，讓您的資料符合[!DNL General Data Protection Regulations](GDPR)。

與所有Adobe Analytics解決方案一樣，Data Workbench在處理Adobe Analytics的資料饋送時提供分析變數的清除、刪除和標示，為GDPR提供支援。 為支援GDPR的實作，Adobe可讓您根據您與Adobe的合約中規定的公司權限，來設定GDPR的程式。 如需詳細資訊，請參閱[Adobe Analytics和GDPR。](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)

GDPR規則可識別負責GDPR實施的不同方的角色和義務（請參閱[GDPR和您的業務](https://www.adobe.com/tw/privacy/general-data-protection-regulation.html)）。

* 您的組織充當&#x200B;**資料掌控者**，根據您的需求和限制來決定個人資料的內容和保留。 Adobe，然後代表您處理並儲存此資料。
* Adobe充當&#x200B;**資料處理者**，根據您與Adobe的協定提供實施GDPR要求的軟體和服務。
* 將Data Workbench與GDPR服務整合後，根據GDPR標準，網站（**資料主體**）的訪客可以通過Adobe（即資料處理者）行使「被遺忘權」。 若要完成忘記權利，您身為資料掌控者，可從UI或API將受挑戰的訪客ID上傳至Adobe。 如需詳細資訊，請參閱[Adobe AnalyticsGDPR Workflow](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html)檔案，包括[提交存取和刪除要求](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html)一節。

>[!NOTE]
>
>對於其他資料來源，您的組織將負責清除其他記錄來源（例如CRM、POS、IVR和其他原始資料來源）中有問題的訪客ID。 _將提供自定義範圍的服務包，以支援組織，將需要持續的服務保留器來支援或維護的每個資料源_&#x200B;提供完整的檔案替換集。

## 升級DWB以實作GDPR

Consulting將就適當的服務套件提供建議，以符合法規。 如需詳細資訊，請連絡您的客戶成功經理(CSM)。

如果需要：

* [升級至最新版](https://docs.adobe.com/content/help/zh-Hant/data-workbench/using/release-notes/release-notes.translate.html) 本的Data Workbench。DWB 6.7版中新增了GDPR整合所需的全新憑證和安全性功能，以提供最高的安全性。
* 如果使用舊版TSV Analytics事件記錄，請升級至[Avro資料饋送](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)。
* 如果將舊式UCP（統一客戶流程）與轉換一起使用以更新現有日誌，請升級到當前流程。 更新的程式會直接產生主查閱檔案，以對應不同來源的訪客ID。
* 標準化資料流程以配合GDPR服務。
* 建立自訂範圍的服務套件，以管理其他記錄來源，例如CRM、POS、IVR和其他原始資料來源。
* 在Analytics合約中確認預設資料保留期為25個月或更長。
