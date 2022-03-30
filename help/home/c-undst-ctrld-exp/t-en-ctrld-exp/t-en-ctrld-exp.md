---
description: 要啟用受控實驗，對Web或應用程式伺服器具有管理員訪問權限的人必須修改安裝感測器的Web群集中每個Web或應用程式伺服器上感測器配置檔案（通常使用txlogd.conf命名）中的ExpFile參數。
solution: Analytics
title: 啟用受控實驗
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# 啟用受控實驗{#enabling-controlled-experimentation}

要啟用受控實驗，對Web或應用程式伺服器具有管理員訪問權限的人必須修改安裝感測器的Web群集中每個Web或應用程式伺服器上感測器配置檔案（通常使用txlogd.conf命名）中的ExpFile參數。

此外，可以修改此檔案中的兩個其他參數，以實現測試工具（ExpCookieURL參數）或重新映射網站的大部分（ExpPartialMatch參數）。 本章提供了有關這些參數的詳細資訊。

**編輯txlogd.conf檔案**

如果您具有管理員訪問權限，請完成以下步驟。 如果您沒有管理員訪問權限，請與系統架構師聯繫以請求更改，並提供以下步驟。

1. 導航到 [!DNL Sensor] 在Web群集中的Web或應用程式伺服器上安裝資料夾 [!DNL Sensor] 已安裝。
1. 開啟 [!DNL Sensor] 配置檔案(通常使用 [!DNL txlogd.conf])使用文本編輯器並編輯檔案，如中所示 [修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

   （可選） [修改ExpCookieURL參數（可選）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) 和 [修改ExpPartialMatch參數（可選）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e)。)

1. 保存並關閉檔案。
1. 對Web群集中的每個Web或應用程式伺服器重複此過程， [!DNL Sensor] 已安裝。
