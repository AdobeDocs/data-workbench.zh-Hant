---
description: 使用者必須擁有有效的帳戶，並在存取報表入口網站時提供帳戶名稱和密碼。
title: 定義其他帳戶
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# 定義其他帳戶

使用者必須擁有有效的帳戶，並在存取報表入口網站時提供帳戶名稱和密碼。

預設情況下，[!DNL Report Portal]中啟用了用戶身份驗證。

[!DNL Report Portal]的有效帳戶清單保存在[!DNL portal.mdb]資料庫檔案中。 [!DNL Report Portal] 與具有管理權限的一個帳戶一起安裝：

* 帳戶名稱：測試
* 密碼：用戶

>[!NOTE]
>
>出於安全原因，Adobe建議您在安裝[!DNL Report Portal]後更改此帳戶的密碼。

要向[!DNL Report Portal]添加用戶帳戶或更改與現有帳戶相關的資訊，請使用[!DNL Report Portal]用戶介面上的[!DNL Admin]頁籤。

每次您新增帳戶或編輯現有帳戶時，都會傳送確認電子郵件，如\*PortalName*\PortalASP資料夾中[!DNL email.asp]檔案中所指定。 如需詳細資訊，請參閱[編輯Email.asp檔案](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)。

有關添加其他用戶的步驟，請參閱[使用帳戶](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)。

>[!NOTE]
>
>或者，您可以停用使用者驗證並允許匿名存取[!DNL Report Portal]。 有關執行此操作的步驟，請參見[編輯會話配置檔案](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)中有關Session(&quot;In&quot;)參數的資訊。
