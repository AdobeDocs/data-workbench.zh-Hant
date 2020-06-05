---
description: Adobe資料工作台提供工具和程式，讓您的資料準備符合一般資料保護法規(GDPR)。
solution: Analytics
title: GDPR的資料工作台支援
topic: Data workbench
translation-type: tm+mt
source-git-commit: 279e71f3da3f0ebc29091e88b87666a22a36a8d6
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---


# GDPR的資料工作台支援

Adobe資料工作台提供工具和程式，讓您的資料準備符合(GDPR) [!DNL General Data Protection Regulations] 的要求。

與所有Adobe Analytics解決方案一樣，資料工作台在處理Adobe Analytics資料饋送時提供分析變數的清除、刪除和標籤，以支援GDPR。 為支援GDPR實作，Adobe可讓您根據您與Adobe的合約所規定的公司權限，設定GDPR的程式。 如需詳 [細資訊，請參閱Adobe Analytics和GDPR](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)。

GDPR規則可識別負責GDPR實施的不同方的角色和義務(請參 [閱GDPR和您的業務](https://www.adobe.com/tw/privacy/general-data-protection-regulation.html))。

* 您的組織充當資 **料掌控者** ，根據您的需求和限制來判斷個人資料的內容和保留。 然後，Adobe會代表您處理和儲存這些資料。
* Adobe是資料處 **理者** ，根據您與Adobe的合約，提供實施GDPR要求的軟體和服務。
* 資料工作台與GDPR服務整合後，根據GDPR標準，造訪網站(資料主體 ****)的訪客可以行使資料處理者Adobe「忘記的權利」。 若要完成遺忘權，您身為資料掌控者，可從UI或API將受挑戰的訪客ID上傳至Adobe。 如需詳細 [資訊，請參閱Adobe Analytics GDPR Workflow](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) (Adobe Analytics GDPR Workflow [)檔案，包](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) 括提交存取和刪除請求。

>[!NOTE]
>
>對於其他資料來源，您的組織將負責清除其他記錄來源（例如CRM、POS、IVR和其他原始資料來源）中有問題的訪客ID。 自訂範圍的服務套件將可為組織提供支援， _為每個資料來源提供完整的檔案取代集_ ，而持續的服務保留者需要支援或維護這些檔案。

## 升級DWB以實作GDPR

Consulting將就適當的服務套件提供建議，以符合法規。 如需詳細資訊，請連絡您的客戶成功經理(CSM)。

如果需要：

* [升級至最新版](https://docs.adobe.com/content/help/zh-Hant/data-workbench/using/release-notes/release-notes.translate.html) 「資料工作台」。 DWB 6.7版中新增了GDPR整合所需的全新憑證和安全性功能，以提供最高的安全性。
* 如果使用舊版TSV Analytics事件記錄，請升級至 [Avro資料饋送](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)。
* 如果將舊式UCP（統一客戶流程）與轉換一起使用以更新現有日誌，請升級到當前流程。 更新的程式會直接產生主查閱檔案，以對應不同來源的訪客ID。
* 標準化資料流程以配合GDPR服務。
* 建立自訂範圍的服務套件，以管理其他記錄來源，例如CRM、POS、IVR和其他原始資料來源。
* 在Analytics合約中確認預設資料保留期為25個月或更長。
