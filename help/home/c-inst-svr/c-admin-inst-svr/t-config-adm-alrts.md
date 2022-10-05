---
description: 管理警報會在Insight Server在正常作業過程中偵測到錯誤時，傳送電子郵件通知給指定的電子郵件地址。
title: 設定管理警報
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# 設定管理警報{#configuring-administrative-alerts}

{{eol}}

管理警報會在Insight Server在正常作業過程中偵測到錯誤時，傳送電子郵件通知給指定的電子郵件地址。

**建議頻率：** 生產前

>[!NOTE]
>
>使用管理警報需要 [!DNL Insight Server] 有權訪問轉發SMTP伺服器以通過電子郵件發送警報。

電子郵件通知的收件者應是主要系統管理人員和主要利害關係人。

管理警報檔案， [!DNL Administrative Alerts.cfg]，用於為 [!DNL Insight Server].

>[!NOTE]
>
>如果運行群集，則必須在主伺服器上建立或修改警報 [!DNL Insight Server] 在叢集中。

**建立或修改管理警報**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。
1. 以滑鼠右鍵按一下 [!DNL Insight Server] 要配置，請按一下 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL Administrative Alerts.cfg] 檔案位於此目錄中。
1. 按一下右鍵*伺服器名稱*列中的複選標籤， [!DNL Administrative Alerts.cfg] 按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Administrative Alerts.cfg].
1. 在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 在 [!DNL Administrative Alerts.cfg] 按一下 **[!UICONTROL component]** 來檢視其內容。
1. 視需要填寫參數。 如需此檔案中可用參數的清單，請參閱 [管理警報組態設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![步驟資訊](assets/cfg_adminalerts_examplevalues.png)

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄和選取 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. （可選）如果您在叢集中工作，且想要將相同的管理警報套用至每個資料處理單元，您必須複製並貼上更新的 [!DNL Administrative Alerts.cfg] 檔案 [!DNL Components for Processing Servers] 資料夾 [!DNL Insight Server] 安裝目錄。
