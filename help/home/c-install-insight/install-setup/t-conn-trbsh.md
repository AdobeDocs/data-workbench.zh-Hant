---
description: 如果Insight無法使用指定的設定連線至Insight Server, 「伺服器管理員」中會出現紅色節點。
title: 連線疑難排解
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
exl-id: 7938d4d6-e1ab-46d9-9ccb-cf79677c5688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# 連線疑難排解{#connection-troubleshooting}

{{eol}}

如果Insight無法使用指定的設定連線至Insight Server, 「伺服器管理員」中會出現紅色節點。

例如，如果您未正確設定連線，或您沒有檢視的權限，就可能會發生此情況 [!DNL Insight Server’s] 狀態。

**判斷Insight無法建立連線的原因**

1. 按一下右鍵紅色的伺服器節點，然後按一下 **[!UICONTROL Detailed Status]**.
1. 在 [!DNL Detailed Status] 介面，按一下 **[!UICONTROL Network Connections]** 並展開編號的項目。 此 [!DNL Status] 參數提供為何Insight無法建立連線的資訊：

   * 500s中的狀態代碼表示配置錯誤。
   * 狀態代碼403通常表示您沒有查看伺服器狀態的權限。

您可以在 [!DNL insight.log] 檔案。 此日誌檔案位於 [!DNL Trace] 資料夾（位於您安裝Insight的目錄中）。 若要檢視檔案，請在文字編輯器（例如記事本）中開啟檔案。

如果您需要協助，請了解 [!DNL insight.log] 檔案，請首先與系統管理員聯繫。 若需進一步協助，請聯絡Adobe客戶服務。
