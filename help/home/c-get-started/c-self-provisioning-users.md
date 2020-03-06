---
description: 使用工作站管理您的資料工作台使用者。
title: 自我布建使用者
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 自我布建使用者{#self-provisioning-of-users}

使用工作站管理您的資料工作台使用者。

您可以透過設定Adobe所需的憑證，使用Workstation來連線至資料工作台伺服器。 此憑證可協助SSL通訊和授權使用授權的資源和功能。 在基於證書的驗證中，您需要獲取並設定多個證書，以便在多台電腦上使用工作站。 此外，使用者布建和權益由Adobe管理，您必須聯絡Adobe以取得新憑證或撤銷憑證。

從DWB 6.7開始，工作站支援通過用戶名和密碼進行用戶驗證。

雖然憑證式驗證／授權仍適用於您的設定，但強烈建議您移轉至較新的憑證式驗證。 在較新的方法中，您的工作站使用者會透過Adobe Identity Management System(IMS)驗證自己。 在使用工作站之前，必須由組織的管理員透過 [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) ，授予他們存取功能的權限。

新的驗證和用戶設定模型有助於：

* 透過Admin Console自行布建使用者和群組。 您不需要連絡Adobe，即可新增、移除或修改使用者的授權權益。
* 通過使用憑據登錄，從多台電腦訪問工作站而不丟失配置狀態。 本地快取在註銷時被刪除，當前配置檔案關閉，配置配置檔案變為活動狀態。

## 入門

開始之前，請連絡Adobe，在Admin Console中新增您的組織。 視您購買的服務而定，Adobe會為您布建組織。 例如，組織可以存取Attribution服務或Beta版本，或兩者皆可。 在設定組織後，組織管理員就可以新增使用者和群組。 如需詳 [細資訊，請參閱](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) Experience Cloud中的管理Experience Cloud使用者和產品。 組織管理員也可以根據不同使用者的角色，設定其使用限制。 例如，非發行前版本使用者不需要存取測試版本。

透過Admin Console新增至此組織的每個已布建使用者都可存取使用資料工作台。 子服務只能針對每個使用者啟用或停用，視其產品存取權限而定。 當使用者從憑證升級至IMS時，所有本機資料都會複製至新的IMS使用者目錄。

>[!NOTE]
>
>除非重新整理存取Token，否則作業階段在伺服器上持續6小時，在用戶端持續23小時。 重新整理代號後，您就可以使用用戶端，而不需重新登入。

管理員至少必須在「管理控制台」中建立一個產品層級設定，才能授予任何使用者存取權。

可新增「 **使用IMS** 」布林值標幟， [!DNL Insight.cfg] 以備退回憑證模式。 如需為IMS使用者設定存取控制的詳細資訊，請參 [閱更新存取控制檔案](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html)。

## 衝突解決

當使用者登入多部電腦時，在相同的設定檔上使用相同IMS帳戶，而且在其中一部電腦上處於離線模式時，可能會表單和快顯視窗會通知您。 `.conflict` 當內容與任何檔案（工作區、尺寸、篩選器等）有差異時，就會發生此情況同步於伺服器和用戶端上[!DNL User\Profile\]的兩部電腦。 將在檔案中建立備 `.conflict` 份，不會丟失任何資料。 中的布爾標 [!DNL Insight.cfg] 幟可讓您停用此衝突快顯視窗。

標幟：衝突通知

這適用於工作區、量度、維度等。 在用戶資料夾中。
