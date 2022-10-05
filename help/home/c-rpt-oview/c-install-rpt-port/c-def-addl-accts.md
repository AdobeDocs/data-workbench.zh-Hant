---
description: 使用者必須具備有效的帳戶，並在存取Report Portal時提供帳戶名稱和密碼。
title: 定義其他帳戶
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# 定義其他帳戶

{{eol}}

使用者必須具備有效的帳戶，並在存取Report Portal時提供帳戶名稱和密碼。

依預設，在 [!DNL Report Portal].

的有效帳戶清單 [!DNL Report Portal] 在資料庫檔案中維護， [!DNL portal.mdb]. [!DNL Report Portal] 與一個具有管理權限的帳戶一起安裝：

* 帳戶名稱：測試
* 密碼：使用者

>[!NOTE]
>
>基於安全原因，Adobe建議您在安裝後更改此帳戶的密碼 [!DNL Report Portal].

若要新增使用者帳戶至 [!DNL Report Portal] 或更改與現有帳戶相關的資訊，請使用 [!DNL Admin] 標籤 [!DNL Report Portal] 使用者介面。

每次您新增帳戶或編輯現有帳戶時，都會依 [!DNL email.asp] 檔案（位於\*PortalName*\PortalASP資料夾中）。 如需詳細資訊，請參閱 [編輯Email.asp檔案](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

如需新增其他使用者的步驟，請參閱 [使用帳戶](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>或者，您可以停用使用者驗證，並允許匿名存取 [!DNL Report Portal]. 如需執行此動作的步驟，請參閱 [編輯會話配置檔案](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
