---
description: 管理警報會在Insight Server在正常作業過程中偵測到錯誤時，傳送電子郵件通知給指定的電子郵件地址。
title: 設定管理警報
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# 設定管理警報{#configuring-administrative-alerts}

管理警報會在Insight Server在正常作業過程中偵測到錯誤時，傳送電子郵件通知給指定的電子郵件地址。

**建議頻率：** 生產前

>[!NOTE]
>
>使用管理警報要求[!DNL Insight Server]有權訪問轉發SMTP伺服器以通過電子郵件發送警報。

電子郵件通知的收件者應是主要系統管理人員和主要利害關係人。

管理警報檔案[!DNL Administrative Alerts.cfg]用於配置[!DNL Insight Server]的管理警報。

>[!NOTE]
>
>如果運行群集，則必須在群集的主[!DNL Insight Server]上建立或修改警報。

**建立或修改管理警報**

1. 在[!DNL Insight]中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要配置的[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以查看其內容。 [!DNL Administrative Alerts.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL Administrative Alerts.cfg]的*伺服器名稱*列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Administrative Alerts.cfg]的[!DNL Temp]列中出現複選標籤。
1. 在[!DNL Temp]欄中按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL Administrative Alerts.cfg]窗口中，按一下&#x200B;**[!UICONTROL component]**&#x200B;查看其內容。
1. 視需要填寫參數。 有關此檔案中可用參數的清單，請參閱[管理警報配置設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)。

   ![步驟資訊](assets/cfg_adminalerts_examplevalues.png)

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，按一下右鍵[!DNL Temp]列中檔案的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

1. （可選）如果您在群集中工作，並且希望將相同的管理警報應用到每個資料處理單元，則必須將更新的[!DNL Administrative Alerts.cfg]檔案複製並貼到主[!DNL Insight Server]安裝目錄的[!DNL Components for Processing Servers]資料夾中。
