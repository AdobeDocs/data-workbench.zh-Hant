---
description: 請依照下列步驟，開始AdobeData Workbench(DWB)(Adobe Analytics Premium(AAP)的元件)的入門程式。
title: DWB Managed Services 的基本入門指示
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
exl-id: 49fb6afe-b417-4554-9238-fd6381c00029
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# DWB Managed Services 的基本入門指示{#basic-onboarding-instructions-for-dwb-managed-services}

{{eol}}

請依照下列步驟，開始AdobeData Workbench(DWB)(Adobe Analytics Premium(AAP)的元件)的入門程式。

這些入門指示適用於使用單一報表套裝實作Data Workbench的客戶，這些報表套裝使用Adobe管理服務而不使用諮詢服務。 如果您是實作DWB的新AAPAdobe，入門團隊將是您的初始聯絡人。 如果從Adobe Analytics標準或舊版DWB升級，Adobe客戶成功經理將協助您。

## 入門資訊：我們需要你 {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe會聯絡您：

* 識別DWB的主要使用者，以在網路目錄上為該使用者專屬產生憑證。 主要使用者也會擔任與Adobe客戶服務互動的指點人員。
* 識別要載入DWB的報表套裝。

Adobe數位行銷團隊隨後會取用您的資訊，建立設定檔、設定帳戶及傳送DWB的設定檔。

**Adobe入門任務**

* Adobe客戶服務會建立DWB授權帳戶。 Adobe客戶服務為主要使用者產生DWB憑證。
* Adobe客戶服務將主要使用者定義為「受支援使用者」，即識別為支援呼叫和問題解決的人員。
* Adobe客戶服務將軟體套件載入至DWB授權和軟體入口網站（SoftDocs/軟體和檔案設定檔），以下載至您的組織。
* AdobeTechOps團隊為DWB準備生產與開發環境及其設定檔（根據合約）。
* AdobeTechOps團隊會設定資料摘要和設定檔管理指令碼。
* AdobeTechOps團隊會建立DWB設定檔案(Insight.cfg)並傳送至Adobe入門團隊，負責與貴組織相關的上線工作。

自訂您的資料摘要並產生憑證、憑證和設定檔設定後，Adobe客戶服務將傳送您的設定檔案和憑證，以採取下一步驟。

## 存取自訂安裝檔案 {#section-26962bf57fef435dbd1c5486d4b6f688}

您會從Adobe客戶服務收到這些設定檔案，以便在用戶端電腦上安裝DWB Workstation。

* 您的自訂DWB組態檔(Insight.cfg)

   客戶端電腦上的此配置檔案將包括與托管DWB伺服器的連接。

* 授權入口網站的登入憑證，以下載DWB設定精靈和主要使用者名稱的必要憑證（.pem檔案）。

**下載其他設定檔案**

1. 瀏覽至：license.visualsciences.com下載許可證證書和DWB安裝嚮導執行檔。
1. 輸入您的組織（帳戶名稱）、主要使用者的名稱，以及您從Adobe客戶服務收到的密碼，然後按一下登入。

   >[!NOTE]
   >
   >您的瀏覽器可能會在這時提示您提供數位憑證。如果出現提示，請按一下取消以關閉對話框。

1. 找到為您的AdobeData Workbench例項核發的憑證(`<PrimaryUser>`.pem)，並下載。
1. 在「下載」區段中找到「標準用戶端安裝程式」，以下載DWB設定精靈(InsightSetup-x.xx.exe檔案)。
1. 從Adobe客戶服務接收並下載檔案後，請執行DWB設定精靈，將工作站軟體安裝至用戶端電腦。

>[!NOTE]
DWB設定精靈會引導您完成DWB用戶端工作站的安裝，並協助您找出Insight.cfg和 `<PrimaryUser>`.pem檔案放入所需資料夾中。 Insight.cfg檔案與您安裝之用戶端工作站的Insight.exe檔案共用。 此 `<PrimaryUser>`.pem檔案位於Certificates資料夾中，包含trust_ca_cert.pem檔案。 DWB必須有所有憑證和設定檔案才能運作。

如需詳細資訊，請參閱 [DWB設定精靈](https://experienceleague.adobe.com/docs/data-workbench/using/install/workstation-setup/install-setup.html).

## 與DWB伺服器的連線 {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

您的受管伺服器會識別在您從Adobe客戶服務收到的Insight.cfg檔案中，且位於您的用戶端工作站上。 AdobeTechOps會設定您的伺服器，而Adobe客戶服務會先將這些受管伺服器和設定檔的參考新增至Insight.cfg檔案，再傳送給您。 （DWB設定精靈檔案的步驟12中的設定伺服器連線即將完成。）

>[!NOTE]
在DWB用戶端工作站的工作站設定工作區中，您將會看到已連線的伺服器和設定檔。

**Adobe Managed Services**

·AdobeTechOps管理基礎架構，包括網路、資料中心、伺服器和儲存。 對於需要TechOps行動的警報，基礎架構監控和對警報的回應會全天候進行。 若是其他警報，TechOps會通知Adobe客戶服務與您協調。

·AdobeTechOps將為您的受控伺服器執行維護和韌體更新。 對於導致停機的維護，您至少提前兩週從客戶服務收到維護窗口通知。 AdobeTechOps將盡快滿足即時需求。 通知將視緊急程度而定，並在知道排程後解決。

·AdobeTechOps設定排程任務以自動管理資料。 從報表套裝時間21:00開始，Analytic摘要資料會每晚移入DWB進行處理和轉換。

·AdobeTechOps將在必要時處理其他Adobe Managed Services，包括資料備份、FTP帳戶、資料封存和資料傳輸。

·AdobeTechOps會將主要生產叢集設定為包含三個月的滾動資料，以便每月重設及重新處理。 重新處理任務中也會更新查閱（Geography、DeviceAtlas、標準分類）。 預設情況下，該任務在每個月的第一個星期五運行。 如有需要，客戶服務可以修改排程。

如需其他資訊，請聯絡 [Adobe客戶服務](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
