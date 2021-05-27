---
description: 通常，Data Workbench伺服器在接收傳入的用戶查詢時會加以回答，並繼續提供結果和即時更新，直到用戶不再請求它們為止。
title: 查詢佇列
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# 查詢佇列{#query-queue}

通常，Data Workbench伺服器在接收傳入的用戶查詢時會加以回答，並繼續提供結果和即時更新，直到用戶不再請求它們為止。

有時，特別是在具有許多Data Workbench用戶的系統上，活動查詢的數量需要的系統資源比從伺服器上可用的更多。 [!DNL Query Queue] 允許伺服器暫時保留某些查詢，直到提供答案所需的資源可用為止。[!DNL Query Queue]還提供了根據各種參數對查詢進行優先順序排列的功能，以便在資源爭用時，優先順序較高的查詢會被優先回答。

來自單一用戶端或報表伺服器的查詢會放在堆中，並排程為單位。 您可以配置資源監視器以限制查詢使用的特定系統資源量。 當被監視的資源允許調度另一個查詢束團時，調度最高優先順序的束團。 由於資源限制，其查詢尚未排程的使用者不會收到錯誤，但會收到其查詢已排入佇列的通知，且使用者可繼續在本機範例上運作。

預設配置包含[!DNL Query Queue]的簡單配置，但將其保留為禁用。 管理員可以啟用或禁用[!DNL Query Queue]、配置資源監視器以確定用於查詢的各種資源的數量，以及為不同用戶配置複雜的優先順序策略。

**為配置Server.cfg檔案[!DNL Query Queuing]**

1. 按一下「**[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**」，開啟[!DNL Server.cfg]。
1. 按一下右鍵&#x200B;**[!UICONTROL Server.cfg]**，並將其設為本地以進行編輯。
1. 展開 [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. 設定下列參數：

   * **使用者群組：** 可讓您設定原則、使用者和佇列優先順序。有關定義，請參閱[查詢佇列使用者群組](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)。

   * **作用中：** (Vector)啟用或停用 [!DNL Query Queue]。有效值為true或false。 預設設定為false。

   * **預設使用者群組：** （字串）輸入新增使用者的使用者群組名稱（如果使用者未列在任何使用者群組中）。
   * **資源監視器：** （向量）按一下右鍵以添加資源監視器。您可以指定[!DNL Query Queue]是監視記憶體還是查詢數。 按一下右鍵&#x200B;**[!UICONTROL Resource Monitor]**&#x200B;以選擇「記憶體預算監視器」或「查詢數監視器」。 如需詳細資訊，請參閱[查詢佇列資源監視器](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) 。

   * **不可觸碰的優先順序：** (Int)指定優先順序大於或等於此值的簇永遠不會被優先順序較高的簇的調度所搶佔。與[使用者群組參數表](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)中所述的[!DNL Memory Budget Monitor]搭配使用。
