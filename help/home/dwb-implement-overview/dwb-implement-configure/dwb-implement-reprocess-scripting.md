---
description: 本節是快速指南，提供設定和排程指令碼以每週重新處理日誌檔案所需的最低步驟。 這可作為參考指南，用於設定或修改您的設定檔。
title: 執行每週重新處理的指令碼
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
exl-id: f1b6f12e-629e-47c7-aa15-41f76d1c3192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# 執行每週重新處理的指令碼{#scripting-to-weekly-reprocess}

{{eol}}

本節是快速指南，提供設定和排程指令碼以每週重新處理日誌檔案所需的最低步驟。 這可作為參考指南，用於設定或修改您的設定檔。

## 什麼是重新處理 {#section-7e335aacc199488592e78a835e2649fe}

根據資料來源、離線資料來源或時段的變更，將資料載入至DWB。 指令碼會在 *Log Processing.cfg* 檔案。

## 先決條件 {#section-804acce5df4942469c9313535627038a}

報表套裝ID、DWB中應提供的月數資料。 Perl64資料夾應可在C:\ drive中使用。

## 重新處理記錄檔 {#section-565d3e1f0df14127a97d9beecd14f02f}

在windows命令指令碼中提供上述詳細資訊（必要條件） *Reprocess.bat* 可用資料夾 *\scripts\日誌處理* 主FSU伺服器。

此指令碼將內部調用兩個客戶端特定指令碼：一個用於重新處理資料，另一個用於電子郵件警報。 這兩個指令碼也可在 *\scripts\日誌處理* 檔案夾。

指令碼會變更 *Log Processing.cfg* 檔案。

## 記錄檔的滾動視窗 {#section-ed5f44d890b34523ab33da7aa0ae3990}

在windows命令指令碼中提供詳細資訊（必要條件） *logprocessingdate.bat* 可用資料夾 *\scripts\Scriptositor* FSU伺服器上。 此指令碼將內部調用兩個客戶端特定指令碼：一個用於設定日誌的開始日期，另一個用於電子郵件警報。 這兩個指令碼在* \scripts\Scripository*中也可用

在* logprocessingdate.bat*檔案中提供報表套裝ID和月數。

指令碼會變更 *Log Processing.cfg*.

>[!NOTE]
>
>若 *Scripository* 資料夾無法使用，請依照下列程式複製 *Scripository* 資料夾，並使用客戶專屬的詳細資訊在上述檔案中進行變更。 並提供您的電子郵件地址，以在發生任何錯誤時收到警報。

## 排程指令碼 {#section-063cf0c755dc47d28d60947d8d43d0e9}

請按照以下步驟調度Windows任務調度程式中的指令碼。

1. 在Windows的任務調度程式中調度指令碼。

   * 開啟任務調度程式：以滑鼠右鍵按一下 **任務調度程式庫** 按一下 **建立任務**.

   * 在 **一般** 頁簽提供任務名並選擇 **選項**.

   * 在 **觸發器** 按一下 **新增** 新窗戶就會開啟。

   * 在 **動作** 按一下 **新增** 新窗戶就會開啟。 然後提供指令碼詳細資訊和其他選項。 （從開始會有放置指令碼的路徑）。

1. 驗證：按一下右鍵並運行作業，並驗證 *Log processing.cfg* 檔案。 系統會傳送電子郵件至指令碼中提供的電子郵件ID。
