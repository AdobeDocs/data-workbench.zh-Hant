---
description: 安裝後，由Adobe核發的數位憑證會成為可讓您執行報表伺服器的金鑰。
title: 重新驗證數位憑證
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 13%

---

# 重新驗證數位憑證{#re-validating-the-digital-certificate}

安裝後，由Adobe核發的數位憑證會成為可讓您執行報表伺服器的金鑰。

**建議頻率：** 視需要

若要正常運作，數位憑證必須為最新。

若要保持最新狀態，您的數位憑證必須定期重新驗證(通常每30天一次，但這可能因您與Adobe的協定而有所不同)。 如果您的電腦可存取網際網路，重新驗證程序會完全透明。[!DNL Report Server] 會自動連線至Adobe授權伺服器，並視需要重新驗證憑證。如果您的電腦無法訪問網際網路，則必須從Adobe許可證伺服器下載經過驗證的新證書，然後使用[下載和安裝數字證書](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)中提供的步驟在您的電腦上安裝。
