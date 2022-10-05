---
description: 使用工作站管理您的Data Workbench使用者。
title: 使用者自行佈建
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# 使用者自行佈建{#self-provisioning-of-users}

{{eol}}

使用工作站管理您的Data Workbench使用者。

您可以從Adobe中設定所需的憑證，以使用Workstation連線至Data Workbench伺服器。 此憑證可協助進行SSL通訊和授權，以使用授權的資源和功能。 在憑證式驗證中，您需要取得並設定多個憑證，以便在多部電腦上使用工作站。 此外，用戶設定和權限由Adobe管理，您必須聯繫Adobe以獲取新證書或證書吊銷。

從DWB 6.7版開始，Workstation支援透過使用者名稱和密碼進行使用者驗證。

雖然憑證式驗證/授權仍適用於您的設定，但強烈建議移轉至較新的憑證式驗證。 在較新的方法中，您的工作站使用者會透過AdobeIdentity Management系統(IMS)驗證自己。 使用者必須先透過 [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=zh-Hant) 由組織的管理員負責。

新的驗證和用戶布建模型有助於：

* 透過Admin Console自行布建使用者和群組。 您不必聯繫Adobe即可新增、移除或修改使用者的授權。
* 使用憑證登入，即可從多部電腦存取工作站，而不會失去設定狀態。 本地快取在註銷時被刪除，當前配置檔案被關閉，配置配置檔案變為活動狀態。

## 快速入門

開始之前，請聯絡Adobe以在Admin Console中新增您的組織。 根據您購買的服務，Adobe會為您布建組織。 例如，組織可以存取歸因服務或測試版組建，或兩者皆可。 設定組織後，組織管理員就可以新增使用者和群組。 請參閱 [管理Experience Cloud使用者和產品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中，以取得詳細資訊。 組織管理員也可以根據不同使用者的角色，為不同使用者設定使用限制。 例如，非發行前使用者不需要存取測試版組建。

透過Admin Console新增至此組織的每個已布建使用者都有權使用Data Workbench。 根據每個使用者的產品存取權，只能對其啟用或停用子服務。 當使用者從憑證升級至IMS時，所有本機資料都會複製到新的IMS使用者目錄。

>[!NOTE]
>
>除非重新整理存取權杖，否則工作階段在伺服器上持續6小時，在用戶端持續23小時。 重新整理代號時，您可以使用用戶端，而不需重新登入。

管理員至少需要先在Admin Console中建立一個產品級配置，然後才能授予任何用戶訪問權限。

布林值標幟 **使用IMS** 可新增至 [!DNL Insight.cfg] 回退至憑證模式。 如需為IMS使用者設定存取控制的詳細資訊，請參閱 [更新存取控制檔案](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## 衝突解決

當使用者登入多部電腦時，在同一個設定檔中具有相同IMS帳戶，且其中一部電腦處於離線模式，則 `.conflict` ，彈出窗口會通知您。 當內容與任何檔案（工作區、維度、篩選器等）有差異時，就會發生此情況。 在中同步的兩台電腦 [!DNL User\Profile\] 在伺服器和用戶端上。 備份將在 `.conflict` 檔案，不會遺失任何資料。 中的布林值標幟 [!DNL Insight.cfg] 允許您禁用此衝突彈出窗口。

標幟：衝突通知

這適用於工作區、量度、維度等。 （在用戶資料夾中）。
