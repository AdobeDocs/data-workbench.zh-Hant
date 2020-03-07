---
description: 使用Insight升級Repeater或複製檔案升級的指示。
solution: Insight
title: 升級中繼器
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 升級中繼器{#upgrading-repeater}

使用Insight升級Repeater或複製檔案升級的指示。

您可以使用下列其中一種方法從Platform 4.x [!DNL Repeater] 或更新版本升級：

* 如果您已建立與之間 [!DNL Insight] 的連 [!DNL Repeater] 線，如 [Creating a Connection Between Insight and Repeater中所述](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)，則可 [!DNL Insight] 用升級 [!DNL Repeater]。 請參 [閱使用Insight升級重複項](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764)。

   -或-

* 如果您無法或未在和之間建立連 [!DNL Insight] 接 [!DNL Repeater]，則必須將升級檔案直接複製到計 [!DNL Repeater] 算機。 請參 [閱複製檔案以升級重複項](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1)。

## 使用Insight升級重複項 {#section-59c24448fd0f45c08abd0245ad746764}

1. 在計 [!DNL Insight] 算機上，將該文 [!DNL bin] 件夾從升級包複製到 [!DNL Insight Server] 安裝目錄的 [!DNL Temp][!DNL Insight] 資料夾。
1. 開始 [!DNL Insight].
1. 在「 [!DNL Insight]>」標籤 [!DNL Admin] 中， [!DNL Dataset and Profile] 按一下縮圖以開 **[!UICONTROL Servers Manager]** 啟「伺服器管理員」工作區。
1. 按一下右鍵要升級的 [!DNL Repeater] 表徵圖，然後按一下 **[!UICONTROL Server Files]**。
1. 在中，執 [!DNL Server Files Manager]行下列操作將升級檔案上載到伺服器：

   1. 找到該文 [!DNL bin] 件夾。
   1. 按一下右鍵Temp目錄中 [!DNL bin] 資料夾的複選標籤，然後選擇 **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*。

>[!NOTE]
>
>您會看到一則訊息，指出此步驟會覆寫伺服器上相同名稱的檔案。 按一 **[!UICONTROL Yes]** 下繼續。

>[!NOTE]
>
>如果您需要上傳其他檔案以完成升 [!DNL Repeater] 級，Adobe會提供相關指示。

將升級檔案上傳至電腦後， [!DNL Repeater] 會自動 [!DNL Repeater] 重新啟動並載入新版本。

## 複製檔案以升級重複項 {#section-202f2209f6604f19a15d96b517ea1bc1}

1. 開啟Adobe提供的升級檔案。 最有可能的是，此檔案是 [!DNL .zip] 用於升級的檔 [!DNL Insight Server]案。
1. 前往您所安裝的目 [!DNL Repeater] 錄(例如 [!DNL D:\Adobe\Repeater])。
1. 複製檔 [!DNL bin] 案中的資料 [!DNL .zip] 夾，並貼到安裝目錄 [!DNL Repeater] 中，以覆寫現有的資料 [!DNL bin] 夾。

>[!NOTE]
>
>如果您需要上傳其他檔案以完成升 [!DNL Insight Server] 級，Adobe會提供相關指示。

將升級檔案複製到電腦後， [!DNL Repeater] 會自動 [!DNL Repeater] 重新啟動並載入新版本。
