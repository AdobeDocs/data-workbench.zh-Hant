---
description: 安裝後，Adobe頒發的數字證書將充當用於運行報表伺服器的密鑰。
title: 重新驗證數字證書（概述）
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 10%

---

# 重新驗證數位憑證{#re-validating-the-digital-certificate}

安裝後，Adobe頒發的數字證書將充當用於運行報表伺服器的密鑰。

**推薦頻率：** 根據需要

要正常運行，數字證書必須是最新的。

要保持最新狀態，您的數字證書必須定期進行重新驗證(通常每30天進行一次，但這可能因您與Adobe的協定而異)。 如果您的電腦可存取網際網路，重新驗證程序會完全透明。[!DNL Report Server] 自動連接到Adobe許可證伺服器，並在必要時重新驗證證書。 如果您的電腦沒有Internet訪問權限，則必須從Adobe許可證伺服器下載新的已驗證證書，然後按照中提供的步驟將其安裝到您的電腦上 [下載和安裝數字證書](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)。
