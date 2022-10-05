---
description: 要啟用受控實驗，具有Web或應用程式伺服器管理員訪問權限的人必須修改Sensor配置檔案（通常使用txlogd.conf）中ExpFile參數，該參數位於安裝Sensor的Web群集中的每個Web或應用程式伺服器上。
solution: Analytics
title: 啟用受控實驗
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# 啟用受控實驗{#enabling-controlled-experimentation}

{{eol}}

要啟用受控實驗，具有Web或應用程式伺服器管理員訪問權限的人必須修改Sensor配置檔案（通常使用txlogd.conf）中ExpFile參數，該參數位於安裝Sensor的Web群集中的每個Web或應用程式伺服器上。

此外，此檔案中的其他兩個參數可修改為實作測試工具（ExpCookieURL參數）或重新映射您網站的大部分區段（ExpPartialMatch參數）。 本章提供這些參數的詳細資訊。

**若要編輯txlogd.conf檔案**

如果您有管理員存取權，請完成下列步驟。 如果您沒有管理員訪問權限，請與系統架構師聯繫以請求更改，並向他們提供以下步驟。

1. 導覽至 [!DNL Sensor] 安裝資料夾(位於 [!DNL Sensor] 已安裝。
1. 開啟 [!DNL Sensor] 組態檔(通常以 [!DNL txlogd.conf])，使用文字編輯器並編輯檔案，如 [修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   （可選） [修改ExpCookieURL參數（選用）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) 和 [修改ExpPartialMatch參數（選用）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. 儲存並關閉檔案。
1. 對於Web群集上的每個Web或應用程式伺服器， [!DNL Sensor] 已安裝。
