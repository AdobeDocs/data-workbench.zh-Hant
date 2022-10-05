---
description: 中繼器功能的管理工作與Insight Server的管理工作非常類似。
title: 管理中繼器
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
exl-id: 5c7a4f95-be4b-4c2c-8dea-19037ba0b5cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 12%

---

# 管理中繼器{#administering-repeater}

{{eol}}

中繼器功能的管理工作與Insight Server的管理工作非常類似。

適用下列管理任務；例外或變更，以便 [!DNL Insight Server] DPU可與中繼器伺服器搭配使用，每個步驟後都會記錄。

* [重新驗證數位憑證](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [確認服務執行中](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) 在「服務」控制面板的服務清單中，尋找「中繼器」。

* [設定存取控制](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [監視磁碟空間](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) 應用於中繼器伺服器的資料類型是事件、作業系統和系統資料。 如果您正使用中繼器伺服器進行備份儲存，並且有必要在電腦上提供更多資料儲存空間，則可以將除當前日誌檔案之外的所有日誌檔案移動到其他電腦或資料儲存介質（zip驅動器、磁帶等）。 移動資料不需要停止中繼器服務。

   >[!NOTE]
   >
   >您應驗證備份副本的完整性 [!DNL .vsl] 檔案，再從中繼器刪除任何檔案。

* [設定管理警報](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [監控管理事件](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [監控稽核記錄](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [設定通訊](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [重新啟動服務](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)  [!DNL Repeater] 功能設計為持續執行。 如果重新啟動電腦，中繼器會自動重新啟動。 如果您需要手動啟動和停止中繼器，可以使用Windows中的「服務」控制面板執行此操作。
