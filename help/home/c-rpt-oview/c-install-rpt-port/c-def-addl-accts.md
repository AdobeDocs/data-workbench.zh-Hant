---
description: 使用者必須擁有有效的帳戶，並在存取報表入口網站時提供帳戶名稱和密碼。
solution: Analytics
title: 定義附加帳戶
topic: Data workbench
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 定義附加帳戶{#define-additional-accounts}

使用者必須擁有有效的帳戶，並在存取報表入口網站時提供帳戶名稱和密碼。

預設情況下，在中啟用用戶驗證 [!DNL Report Portal]。

有效帳戶的清單 [!DNL Report Portal] 保存在資料庫檔案中 [!DNL portal.mdb]。 [!DNL Report Portal] 與具有管理權限的一個帳戶一起安裝：

* 帳戶名稱：測試
* 密碼：用戶

>[!NOTE]
>
>出於安全原因，Adobe建議您在安裝後變更此帳戶的密碼 [!DNL Report Portal]。

若要新增使用者帳 [!DNL Report Portal] 戶至或變更現有帳戶的相關資訊，請使用使 [!DNL Admin] 用者介面上的 [!DNL Report Portal] 標籤。

每次您新增帳戶或編輯現有帳戶時，會依\*PortalName*\PortalASP資料夾中 [!DNL email.asp] 的檔案指定，傳送確認電子郵件。 如需詳細資訊，請 [參閱編輯Email.asp檔案](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)。

如需新增其他使用者的步驟，請參 [閱使用帳戶](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)。

>[!NOTE]
>
>或者，您可以停用使用者驗證並允許匿名存取 [!DNL Report Portal]。 有關執行此操作的步驟，請參閱編輯會話配置檔案中有關Session(&quot;In&quot;) [參數的資訊](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)。

