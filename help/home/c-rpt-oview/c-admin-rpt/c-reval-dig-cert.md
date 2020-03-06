---
description: 安裝後，Adobe核發的數位憑證會當成您執行報表伺服器的金鑰。
solution: Analytics
title: 重新驗證數位憑證
topic: Data workbench
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 重新驗證數位憑證{#re-validating-the-digital-certificate}

安裝後，Adobe核發的數位憑證會當成您執行報表伺服器的金鑰。

**建議頻率：** 視需要

若要正常運作，數位憑證必須是最新的。

若要保持最新狀態，您的數位憑證必須定期重新驗證（通常每30天重新驗證一次，但視您與Adobe的合約而定）。 如果您的電腦可以存取網際網路，重新驗證程式會完全透明。 [!DNL Report Server] 自動連線至Adobe License Server，並在需要時重新驗證憑證。 如果您的電腦沒有網際網路連線，您必須從Adobe License Server下載經過驗證的新憑證，然後依照「下載並安裝數位憑證」中的步驟，將其安裝在您的 [電腦上](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)。
