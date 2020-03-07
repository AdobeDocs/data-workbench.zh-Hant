---
description: 本節是快速指南，提供設定和排程指令碼以每週重新處理記錄檔所需的最低步驟。 這可用作設定或修改配置式的參考指南。
title: 對每週重新處理的指令碼
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 對每週重新處理的指令碼{#scripting-to-weekly-reprocess}

本節是快速指南，提供設定和排程指令碼以每週重新處理記錄檔所需的最低步驟。 這可用作設定或修改配置式的參考指南。

## 什麼是重新處理 {#section-7e335aacc199488592e78a835e2649fe}

根據資料來源、離線資料來源或時段的變更，將資料載入至DWB。 指令碼將重新處理 *Log Processing.cfg檔案中的開始日期* 參數。

## 必備條件 {#section-804acce5df4942469c9313535627038a}

報表套裝ID,DWB中應提供月份資料數。 Perl64資料夾應在C:\ drive資料夾中可用。

## 重新處理記錄檔 {#section-565d3e1f0df14127a97d9beecd14f02f}

在Windows命令指令碼 *Reprocess.bat中提供上述詳細資訊（必要條件）* ，可在主 *FSU伺服器的資料夾\scripts\Log Processing中* 獲得。

此指令碼將在內部調用兩個客戶端特定指令碼：一個用於重新處理資料，另一個用於發送電子郵件警報。 這兩個指令碼也可在\scripts\Log Processing資料 *夾中* 。

此指令碼會變更 *Log Processing.cfg檔案中的重新處理參數* 。

## 日誌滾動窗口 {#section-ed5f44d890b34523ab33da7aa0ae3990}

在管理FSU伺服器的資料夾\scripts\Scripository中，提 *供windows命令指令碼logprocessingdate.bat* (必要條件 ** )的詳細資訊。 此指令碼將在內部調用兩個客戶端特定指令碼：一個用於設定日誌的開始日期，另一個用於電子郵件警報。 這兩個指令碼也可在* \scripts\Scripository*中取得

在* logprocessingdate.bat*檔案中提供報表套裝ID和月數。

指令碼會變更 *Log Processing.cfg中的開始日期參數*。

>[!NOTE]
>
>如果「 *Scripository* 」資料夾不可用，請遵循以下流程來複製「 *Scriptository* 」資料夾，並使用特定於客戶的詳細資訊在上述檔案中進行更改。 並提供您的電子郵件地址，以在發生任何錯誤時獲得警報。

## 計畫指令碼 {#section-063cf0c755dc47d28d60947d8d43d0e9}

請遵循下列步驟，在Windows任務調度程式中調度指令碼。

1. 在Windows的任務調度程式中調度指令碼。

   * 開啟任務調度程式：按一下右鍵「任務調 **度程式庫」** ，然後按一下 **建立任務**。

   * 在「一 **般** 」標籤中提供任務名稱並選擇 **選項**。

   * 在「觸發 **器** 」標籤下，按 **一下「新增** 」，新視窗將會開啟。

   * 在「動 **作** 」標籤下，按一 **下「新增** 」，新視窗將會開啟。 然後提供指令碼詳細資訊和其他選項。 （開始於將有放置指令碼的路徑）。

1. 驗證：按一下右鍵並運行作業，並驗證 *Log processing.cfg檔案中的更改* 。 電子郵件會傳送至指令碼中提供的電子郵件ID。

