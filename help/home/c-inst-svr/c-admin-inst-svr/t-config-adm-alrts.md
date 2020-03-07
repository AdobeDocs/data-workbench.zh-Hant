---
description: 管理警報會在Insight Server在正常作業過程中偵測到錯誤時，傳送電子郵件通知給指定的電子郵件地址。
solution: Insight
title: 配置管理警報
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置管理警報{#configuring-administrative-alerts}

管理警報會在Insight Server在正常作業過程中偵測到錯誤時，傳送電子郵件通知給指定的電子郵件地址。

**建議頻率：** 製作前

>[!NOTE]
>
>使用管理警報時，需要 [!DNL Insight Server] 有權訪問轉發SMTP伺服器，以通過電子郵件發送警報。

電子郵件通知的收件人應是主要系統管理人員和主要利益相關者。

管理警報文 [!DNL Administrative Alerts.cfg]件用於配置管理警報 [!DNL Insight Server]。

>[!NOTE]
>
>如果正在運行群集，則必須在群集中的主系統上建立或修改 [!DNL Insight Server] 警報。

**建立或修改管理警報**

1. 在「 [!DNL Insight]>」標籤 [!DNL Admin] 中， [!DNL Dataset and Profile] 按一下縮圖以開 **[!UICONTROL Servers Manager]** 啟「伺服器管理員」工作區。
1. 按一下右鍵要配置的 [!DNL Insight Server] 表徵圖，然後按一下 **[!UICONTROL Server Files]**。
1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Components]** 查看其內容。 文 [!DNL Administrative Alerts.cfg] 件位於此目錄中。
1. 按一下右鍵*伺服器名稱*列中的複選標籤，然 [!DNL Administrative Alerts.cfg] 後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在的 [!DNL Temp] 列中 [!DNL Administrative Alerts.cfg]。
1. 在欄中以滑鼠右鍵按一下新建立的核取標 [!DNL Temp] 記，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Insight]**。
1. 在視窗 [!DNL Administrative Alerts.cfg] 中，按一 **[!UICONTROL component]** 下以檢視其內容。
1. 視需要填寫參數。 如需此檔案中可用參數的清單，請參閱管理 [警報組態設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)。

   ![步驟資訊](assets/cfg_adminalerts_examplevalues.png)

1. 執行下列動作，將變更儲存至伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]按一下右鍵列中檔案的複選標籤，然 [!DNL Temp] 後選擇 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

1. （可選）如果您在群集中工作，並且希望對每個資料處理單元應用相同的管理警報，則必須將更新的檔案複製並貼上到主安裝目錄 [!DNL Administrative Alerts.cfg] 內 [!DNL Components for Processing Servers] 的文 [!DNL Insight Server] 件夾中。
