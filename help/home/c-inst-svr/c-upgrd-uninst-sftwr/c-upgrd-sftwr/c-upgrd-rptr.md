---
description: 使用Insight升級中繼器，或複製檔案以升級的指示。
title: 升級中繼器
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 升級中繼器{#upgrading-repeater}

{{eol}}

使用Insight升級中繼器，或複製檔案以升級的指示。

您可以使用下列其中一種方法來升級 [!DNL Repeater] 從Platform 4.x或更新版本：

* 如果您已建立 [!DNL Insight] 和 [!DNL Repeater] 如 [在Insight和中繼器之間建立連線](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)，您可以使用 [!DNL Insight] 升級 [!DNL Repeater]. 請參閱 [使用Insight升級中繼器](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -或-

* 如果您無法或未在 [!DNL Insight] 和 [!DNL Repeater]，您必須將升級檔案直接複製到 [!DNL Repeater] 機器。 請參閱 [複製檔案以升級中繼器](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## 使用Insight升級中繼器 {#section-59c24448fd0f45c08abd0245ad746764}

1. 在 [!DNL Insight] 電腦，複製 [!DNL bin] 資料夾 [!DNL Insight Server] 升級套件至 [!DNL Temp] 資料夾，其中 [!DNL Insight] 已安裝。
1. 開始 [!DNL Insight].
1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。
1. 以滑鼠右鍵按一下 [!DNL Repeater] 要升級，請按一下 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，請執行下列操作將升級檔案上傳至伺服器：

   1. 找出 [!DNL bin] 檔案夾。
   1. 以滑鼠右鍵按一下 [!DNL bin] 檔案夾（位於Temp目錄中），然後選取 **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>您會看到一則訊息，指出此步驟會覆寫伺服器上存在之同名檔案。 按一下 **[!UICONTROL Yes]** 繼續。

>[!NOTE]
>
>如果您需要上傳其他檔案以完成 [!DNL Repeater] 升級，Adobe將提供相關指示。

將升級檔案上傳至 [!DNL Repeater] 機器， [!DNL Repeater] 自動重新啟動並載入新版本。

## 複製檔案以升級中繼器 {#section-202f2209f6604f19a15d96b517ea1bc1}

1. 開啟Adobe提供的升級檔案。 很可能，此檔案是 [!DNL .zip] 升級檔案 [!DNL Insight Server].
1. 轉至安裝的目錄 [!DNL Repeater] (例如， [!DNL D:\Adobe\Repeater])。
1. 複製 [!DNL bin] 資料夾 [!DNL .zip] 檔案並貼到 [!DNL Repeater] 要覆蓋現有安裝目錄 [!DNL bin] 檔案夾。

>[!NOTE]
>
>如果您需要上傳其他檔案以完成 [!DNL Insight Server] 升級，Adobe將提供相關指示。

將升級檔案複製到 [!DNL Repeater] 機器， [!DNL Repeater] 自動重新啟動並載入新版本。
