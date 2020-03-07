---
description: 快速指南，瞭解驗證和設定歷史資料饋送所需的最低步驟。
title: 驗證歷史資料饋送
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 驗證歷史資料饋送{#validating-historical-data-feeds}

快速指南，瞭解驗證和設定歷史資料饋送所需的最低步驟。

## 資料饋送一致性的驗證步驟 {#section-777b2c627a354627a02feb9461e23038}

1. 登入 *Dreteh* (https://oasis.omniture.com/drteeth/)
1. 前往SiteCatalyst管理員->資料饋送定義（新）
1. 跳至伺服器位置(例如 達拉斯，倫敦……)視貴組織所在位置而定。
1. 提供RSID並選取動態消息類型Insight，然後按一下 *搜尋*。

   ![](assets/dwb_impl_historical.png)

1. 識別客戶的實際動態消息名稱。
1. 按一下「動作區段」中的「步驟記錄」。 ![](assets/dwb_impl_historical1.png)

   檢查狀態欄位中是否有任何錯誤，若有些動態消息處於錯誤狀態，請選取動態消息並按一下重新處理。 如果多個請求發生錯誤，請傳送電子郵件至具有動態消息ID *`dataworkbench@adobe.com`* 和報表套裝詳細資訊以重新處理。

1. 驗證後檢查NAS位置的原始資料夾中的日誌。

