---
description: 安裝後，由Adobe核發的數位憑證會當成您執行報表伺服器的金鑰。
title: 重新驗證數位憑證
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 13%

---

# 重新驗證數位憑證{#re-validating-the-digital-certificate}

安裝後，由Adobe核發的數位憑證會當成您執行報表伺服器的金鑰。

**建議的頻率：** 視需要

若要正常運作，數位憑證必須是最新的。

若要保持最新狀態，您的數位憑證必須定期重新驗證(通常每30天重新驗證一次，但視您與Adobe的合約而定)。 如果您的電腦可存取網際網路，重新驗證程序會完全透明。[!DNL Report Server] 自動連線至Adobe授權伺服器，並視需要重新驗證憑證。如果您的電腦沒有網際網路連線，您必須從Adobe授權伺服器下載經過驗證的新憑證，然後依照[下載與安裝數位憑證](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)中的步驟，將其安裝在您的電腦上。
