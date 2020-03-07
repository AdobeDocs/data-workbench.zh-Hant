---
description: 通常，資料工作台伺服器會在收到傳入的使用者查詢時加以回覆，並持續提供結果和即時更新，直到使用者不再請求為止。
solution: Analytics
title: 查詢隊列
topic: Data workbench
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 查詢隊列{#query-queue}

通常，資料工作台伺服器會在收到傳入的使用者查詢時加以回覆，並持續提供結果和即時更新，直到使用者不再請求為止。

有時，尤其是在擁有許多資料工作台使用者的系統上，活動查詢的數目需要的系統資源比伺服器上的可用資源多。 [!DNL Query Queue] 允許伺服器將某些查詢暫時保留，直到提供答案所需的資源可用為止。 該 [!DNL Query Queue] 功能還提供了根據各種參數對查詢進行優先順序排序的功能，以便在資源爭用時，優先順序較高的查詢首先得到回答。

來自單一用戶端或報告伺服器的查詢會放在一串中，並排程為單位。 您可以配置資源監視器以限制查詢使用的特定系統資源量。 當被監控的資源允許調度另一個查詢簇時，調度優先順序最高的簇。 由於資源限制，尚未排程查詢的用戶不會收到錯誤，但會收到查詢已排入佇列的通知，並且用戶可以繼續處理本地示例。

預設配置包括對的簡單配置 [!DNL Query Queue]，但將其禁用。 管理員可以啟用或禁用 [!DNL Query Queue]、配置資源監視器以確定用於查詢的各種資源的數量，以及為不同用戶配置複雜的優先順序策略。

**若要設定Server.cfg檔案，請[!DNL Query Queuing]**

1. 按一 [!DNL Server.cfg] 下 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** >以開啟 **[!UICONTROL Dataset]**。
1. 按一下滑鼠右 **[!UICONTROL Server.cfg]** 鍵，並將它設為本機以供編輯。
1. 展開 [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. 設定下列參數：

   * **使用者群組：** 可讓您設定原則、使用者和佇列優先順序。 如需 [定義，請參閱查詢佇列使用者群組](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) 。

   * **活動：** （向量）啟用或停用 [!DNL Query Queue]。 有效值為true或false。 預設設定為false。

   * **預設使用者群組：** （字串）輸入新增使用者的使用者群組名稱（如果使用者未列在任何使用者群組中）。
   * **資源監視器：** （向量）按一下滑鼠右鍵以新增資源監視程式。 您可以指定監視內 [!DNL Query Queue] 存還是查詢數。 按一下右鍵以 **[!UICONTROL Resource Monitor]** 選擇「記憶體預算監視器」或「查詢數監視器」。 如需詳 [細資訊，請參閱查詢佇列資源監](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) 視程式。

   * **Untouchable Priority:** (Int)指定優先順序大於或等於此值的串絕不會被搶佔以調度高優先順序的串。 與「用戶組參數」( [!DNL Memory Budget Monitor] User Group Parameters)表 [中所述一起使用](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)。

