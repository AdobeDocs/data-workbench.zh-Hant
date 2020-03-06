---
description: 如果Insight無法使用指定的設定連線至Insight伺服器，則「伺服器管理員」中會顯示紅色節點。
title: 連線疑難排解
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 連線疑難排解{#connection-troubleshooting}

如果Insight無法使用指定的設定連線至Insight伺服器，則「伺服器管理員」中會顯示紅色節點。

例如，如果您未正確設定連線或您沒有檢視狀態的權限，可能會發生此 [!DNL Insight Server’s] 情況。

**判斷Insight無法建立連線的原因**

1. 按一下右鍵紅色伺服器節點，然後按一下 **[!UICONTROL Detailed Status]**。
1. 在介面 [!DNL Detailed Status] 中，按一下 **[!UICONTROL Network Connections]** 並展開編號的項目。 此參 [!DNL Status] 數提供Insight無法建立連線的相關資訊：

   * 500s中的狀態代碼表示配置錯誤。
   * 狀態碼403通常表示您沒有檢視伺服器狀態的權限。

您可以在檔案中檢視其他狀態 [!DNL insight.log] 資訊。 此記錄檔位於您安 [!DNL Trace] 裝Insight之目錄的資料夾中。 若要檢視檔案，請在文字編輯器（例如記事本）中開啟檔案。

如果您需要協助瞭解檔案中的資 [!DNL insight.log] 訊，請先與系統管理員聯絡。 如果您需要進一步的協助，請聯絡Adobe客戶服務。
