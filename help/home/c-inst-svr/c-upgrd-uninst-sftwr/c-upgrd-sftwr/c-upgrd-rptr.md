---
description: 使用Insight升級Repeater或複製檔案升級的指示。
title: 升級中繼器
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 升級中繼器{#upgrading-repeater}

使用Insight升級Repeater或複製檔案升級的指示。

您可以使用下列其中一種方法從Platform 4.x或更新版本升級[!DNL Repeater]:

* 如果按[建立分析與中繼器之間的連線](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)中所述建立[!DNL Insight]與[!DNL Repeater]之間的連線，您可以使用[!DNL Insight]升級[!DNL Repeater]。 請參閱[使用Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764)升級中繼器。

   -或-

* 如果您無法或未在[!DNL Insight]和[!DNL Repeater]之間建立連接，則必須將升級檔案直接複製到[!DNL Repeater]電腦。 請參閱[複製檔案以升級中繼器](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1)。

## 使用Insight {#section-59c24448fd0f45c08abd0245ad746764}升級中繼器

1. 在[!DNL Insight]電腦上，將[!DNL bin]資料夾從[!DNL Insight Server]升級包複製到[!DNL Insight]安裝目錄的[!DNL Temp]資料夾。
1. 開始 [!DNL Insight].
1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要升級的[!DNL Repeater]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，執行下列操作將升級檔案上載到伺服器：

   1. 找到[!DNL bin]資料夾。
   1. 按一下右鍵Temp目錄中[!DNL bin]資料夾的複選標籤，然後選擇&#x200B;**[!UICONTROL Save Directory to]** > ***[!UICONTROL server name]***。

>[!NOTE]
>
>您會看到一則訊息，指出此步驟會覆寫伺服器上相同名稱的檔案。 按一下&#x200B;**[!UICONTROL Yes]**&#x200B;繼續。

>[!NOTE]
>
>如果您需要上傳其他檔案以完成[!DNL Repeater]升級，Adobe將提供相關指示。

將升級檔案上傳到[!DNL Repeater]電腦後，[!DNL Repeater]將自動重新啟動並載入新版本。

## 複製檔案{#section-202f2209f6604f19a15d96b517ea1bc1}以升級中繼器

1. 開啟由Adobe提供的升級檔。 最有可能的是，此檔案是用於升級[!DNL Insight Server]的[!DNL .zip]檔案。
1. 轉至安裝[!DNL Repeater]的目錄（例如[!DNL D:\Adobe\Repeater]）。
1. 複製[!DNL .zip]檔案中的[!DNL bin]檔案夾，並貼到您的[!DNL Repeater]安裝目錄，以覆寫現有的[!DNL bin]檔案夾。

>[!NOTE]
>
>如果您需要上傳其他檔案以完成[!DNL Insight Server]升級，Adobe將提供相關指示。

將升級檔案複製到[!DNL Repeater]電腦後， [!DNL Repeater]將自動重新啟動並載入新版本。
