---
description: 要啟用受控實驗，具有Web或應用程式伺服器管理員訪問權限的人員必須修改安裝感測器的Web群集中每個Web或應用程式伺服器上感測器配置檔案（通常使用txlogd.conf命名）中的ExpFile參數。
solution: Analytics,Analytics
title: 啟用受控實驗
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---


# 啟用受控實驗{#enabling-controlled-experimentation}

要啟用受控實驗，具有Web或應用程式伺服器管理員訪問權限的人員必須修改安裝感測器的Web群集中每個Web或應用程式伺服器上感測器配置檔案（通常使用txlogd.conf命名）中的ExpFile參數。

此外，此檔案中的其他兩個參數也可修改，以實作測試工具（ExpCookieURL參數）或重新映射您網站的大部分區域（ExpPartialMatch參數）。 本章提供了有關這些參數的詳細資訊。

**要編輯txlogd.conf檔案**

如果您有管理員存取權，請完成下列步驟。 如果您沒有管理員存取權，請連絡您的系統架構設計人員以要求變更，並提供下列步驟。

1. 導覽至您 [!DNL Sensor] 所安裝之Web叢集中之Web或應用程式伺服器上的安裝資 [!DNL Sensor] 料夾。
1. 使用文 [!DNL Sensor] 字編輯器開啟配置檔案(通常使用 [!DNL txlogd.conf]命名)，並按修改ExpFile參數中指 [示編輯檔案](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

   (或者，在修 [改ExpCookieURL參數（可選）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)[和修改ExpPartialMatch參數（可選）中](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e)。)

1. 儲存並關閉檔案。
1. 對安裝Web群集的每個Web或應用程式伺服器重複此 [!DNL Sensor] 過程。
