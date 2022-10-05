---
description: 驗證和設定歷史資料摘要所需最低步驟的快速指南。
title: 驗證歷史資料摘要
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
exl-id: 5a5e2cca-2fab-48a0-b58d-a8c46114b9a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 5%

---

# 驗證歷史資料摘要{#validating-historical-data-feeds}

{{eol}}

驗證和設定歷史資料摘要所需最低步驟的快速指南。

## 資料摘要一致性驗證步驟 {#section-777b2c627a354627a02feb9461e23038}

1. 登入 *齒* (https://oasis.omniture.com/drteeth/)
1. 前往「SiteCatalyst管理員 — >資料摘要定義（新）」
1. 跳到伺服器位置(例如 達拉斯，倫敦……) 視您的組織所在位置而定。
1. 提供RSID並選取摘要類型Insight ，然後按一下 *搜尋*.

   ![](assets/dwb_impl_historical.png)

1. 識別客戶的實際摘要名稱。
1. 按一下「動作」區段中的「歷史記錄」 。 ![](assets/dwb_impl_historical1.png)

   檢查狀態欄位中是否有任何錯誤，如果有些摘要處於錯誤狀態，請選取摘要，然後按一下重新處理。 如果多個請求發生錯誤，請傳送電子郵件至 *`dataworkbench@adobe.com`* 包含要重新處理的摘要ID和報表套裝詳細資訊。

1. 驗證後將檢查NAS位置的原始資料夾中的日誌。
