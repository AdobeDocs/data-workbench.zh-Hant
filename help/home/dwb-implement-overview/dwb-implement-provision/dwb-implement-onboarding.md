---
description: 請依照下列步驟，開始Adobe Analytics Premium(AAP)的元件Adobe資料工作台(DWB)的上線程式。
title: DWB受管服務的基本入門指示
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# DWB受管服務的基本入門指示{#basic-onboarding-instructions-for-dwb-managed-services}

請依照下列步驟，開始Adobe Analytics Premium(AAP)的元件Adobe資料工作台(DWB)的上線程式。

這些入門指示適用於使用Adobe管理服務而不需諮詢服務，透過單一報表套裝實作資料工作台的客戶。 如果您是實作DWB的新AAP客戶，Adobe入門團隊將是您的初始聯絡人。 如果從Adobe Analytics標準版或從舊版DWB升級，Adobe客戶成功經理將協助您。

## 入門資訊：我們需要您的 {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe會與您聯絡，以：

* 確定DWB的主用戶，以便為網路目錄上的該用戶生成證書。 主要使用者也將擔任與Adobe客戶服務互動的要員。
* 識別要載入DWB的報表套裝。

Adobe數位行銷團隊接著會利用您的資訊來建立描述檔、設定帳戶，並傳送DWB的設定檔。

**Adobe入門工作**

* Adobe客戶服務會建立DWB授權帳戶。 Adobe客戶服務會為主要使用者產生DWB憑證。
* Adobe客戶服務將主要使用者定義為「受支援使用者」，此人員是識別有支援的呼叫和問題解決方案的人員。
* Adobe客戶服務會將軟體套件載入DWB授權和軟體入口網站（SoftDocs/軟體和檔案設定檔），以下載至您的組織。
* Adobe TechOps團隊為DWB準備生產與開發環境及其個人檔案（依合約）。
* Adobe TechOps團隊會設定資料饋送和描述檔管理指令碼。
* Adobe TechOps團隊會建立DWB組態檔(Insight.cfg)並傳送給負責與貴組織相關之入職工作的Adobe入職團隊。

自訂您的資料饋送並產生認證、憑證和描述檔設定後，Adobe客戶服務會傳送您的設定檔和認證，以採取下一步驟。

## 存取您的自訂安裝檔案 {#section-26962bf57fef435dbd1c5486d4b6f688}

您會從Adobe客戶服務收到這些設定檔，以便在用戶端電腦上安裝DWB Workstation。

* 您的自訂DWB設定檔案(Insight.cfg)

   客戶機上的此配置檔案將包括到受管理DWB伺服器的連接。

* 授權入口網站的登入認證，以下載DWB設定精靈和必要憑證（.pem檔案），並以您的主要使用者名稱。

**下載其他設定檔案**

1. 瀏覽至：license.visualsciences.com下載授權憑證和DWB設定精靈可執行檔。
1. 輸入您的組織（帳戶名稱）、主要使用者的名稱，以及您從Adobe客戶服務收到的密碼，然後按一下登入。

   >[!NOTE]
   >
   >您的瀏覽器可能會提示您目前呈現數位憑證。 如果出現此情況，請按一下「取消」關閉對話框。

1. 在「下載」區段中找到您的Adobe Data Workbench(`<PrimaryUser>`.pem)實例核發的憑證並下載。
1. 在「Downloads（下載）」區段中找到「Standard Client Installer（標準用戶端安裝程式）」，以下載「DWB Setup Wizard（DWB設定精靈）」(InsightSetup-x.xx.exe檔案)。
1. 從Adobe客戶服務接收並下載檔案後，請執行DWB設定精靈，將工作站軟體安裝至用戶端電腦。

>[!NOTE]
DWB設定精靈會引導您完成DWB用戶端工作站的安裝，並協助找出要置入所需資料夾的Insight.cfg和 `<PrimaryUser>`.pem檔案。 Insight.cfg檔案位於您所安裝用戶端工作站的Insight.exe檔案中。 . `<PrimaryUser>`pem檔案位於Certificates資料夾中，內含trust_ca_cert.pem檔案。 DWB必須有所有憑證和設定檔案才能運作。

如需詳細資訊，請參 [閱DWB設定精靈](https://docs.adobe.com/content/help/en/data-workbench/using/install/workstation-setup/install-setup.html)。

## 連線至DWB伺服器 {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

您的受管理伺服器會在您從Adobe客戶服務收到的Insight.cfg檔案中識別，並位於您的用戶端工作站上。 Adobe TechOps將會設定您的伺服器，Adobe客戶服務會在將這些受控伺服器和描述檔的參考資料傳送至Insight.cfg檔案後，再將它們傳送給您。 （將完成DWB設定嚮導文檔步驟12中的「配置到伺服器的連接」。）

>[!NOTE]
在DWB客戶端工作站的「工作站配置」工作區中，您將能夠查看連接的伺服器和配置檔案。

**Adobe Managed Services**

· Adobe TechOps管理基礎架構，包括網路、資料中心、伺服器和儲存空間。 對於需要TechOps操作的警報，基礎架構監控和響應警報的全天候執行。 若有其他警報，TechOps會通知Adobe客戶服務與您協調。

· Adobe TechOps將為您的受控伺服器執行維護和韌體更新。 對於導致停機的維護，您至少會在兩週前收到客戶服務的維護視窗通知。 Adobe TechOps將盡快滿足眼前的需求。 通知將視緊急程度而定，並會在計畫知曉後解決。

· Adobe TechOps會設定排程的工作，以自動管理資料。 分析饋送資料會移入DWB，以便每晚從21:00報表套裝時間開始處理和轉換。

· Adobe TechOps將處理其他Adobe Managed Services，包括資料備份、FTP帳戶、資料封存及必要時的資料傳輸。

· Adobe TechOps將設定主要生產叢集，以包含三個月的滾動資料，每月重設並重新處理。 代碼的更新（地理位置、DeviceAtlas、標準分類）也會在重新處理任務中進行。 依預設，工作會在每個月的第一個星期五執行。 如有必要，客戶服務可修改排程。

如需詳細資訊，請 [聯絡Adobe客戶服務](https://helpx.adobe.com/support/programs/enterprise-support-terms.html)。
