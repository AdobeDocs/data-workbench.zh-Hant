---
description: AdobeData Workbench提供工具和程式，讓您的資料符合一般資料保護規範(GDPR)。
title: GDPR 的 Data Workbench 支援
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 4%

---

# GDPR 的 Data Workbench 支援

AdobeData Workbench提供工具和程式，讓您的資料符合[!DNL General Data Protection Regulations](GDPR)。

與所有Adobe Analytics解決方案一樣，Data Workbench在處理Adobe Analytics的資料饋送時，提供分析變數的清除、刪除和標籤功能，以支援GDPR。 為支援GDPR實作，Adobe可讓您根據貴公司與Adobe的合約中確立的權限，設定GDPR的程式。 如需詳細資訊，請參閱[Adobe Analytics和GDPR](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=zh-Hant)。

GDPR規則識別負責GDPR啟用之不同方面的角色和義務（請參閱[GDPR和您的業務](https://www.adobe.com/tw/privacy/general-data-protection-regulation.html)）。

* 貴組織擔任&#x200B;**資料控制方**，根據您的需求和限制決定個人資料的內容和保留。 Adobe接著代表您處理和儲存這些資料。
* Adobe充當&#x200B;**資料處理者** ，根據您與Adobe的合約，提供實施GDPR要求的軟體和服務。
* 將Data Workbench與GDPR服務整合後，並根據GDPR標準，網站的訪客（**資料主體**）可行使其「被資料處理者遺忘的權利」(Adobe)。 您做為資料控管單位，可以從UI或API將有問題的訪客ID上傳至Adobe，以完成被遺忘的權利。 如需詳細資訊，請參閱[Adobe Analytics GDPR工作流程](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html)檔案，包括[提交存取和刪除請求](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html)區段。

>[!NOTE]
>
>對於其他資料來源，您的組織將負責清除其他記錄來源（例如CRM、POS、IVR和其他原始資料來源）中出現問題的訪客ID。 通過&#x200B;_為每個資料源_&#x200B;提供一組完整替換的檔案，以支援或維護需要持續的服務容器，自定義範圍的服務包將可用於為組織提供支援。

## 升級DWB以實作GDPR

諮詢服務將就適當的服務套件提供建議，以便讓現有實作符合規範。 如需詳細資訊，請連絡您的客戶成功經理(CSM)。

如果需要：

* [升級至最新](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) 版本的Data Workbench。為獲得最高的安全性，DWB 6.7版新增了GDPR整合所需的憑證和安全性功能。
* 如果使用舊版TSV Analytics事件記錄，請升級至[Avro資料摘要](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)。
* 如果使用具有轉換的舊版UCP（統一客戶流程）來更新現有日誌，請升級至目前的流程。 更新後的程式會直接產生主要查閱檔案，以便跨來源對應訪客ID。
* 標準化資料流程以符合GDPR服務。
* 建立自訂範圍的服務套件，以管理其他記錄來源，例如CRM、POS、IVR和其他原始資料來源。
* 在Analytics合約中確認25個月或更長的預設資料保留期。
