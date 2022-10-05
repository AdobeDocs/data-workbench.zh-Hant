---
description: 套用至「設定檔管理器」的Internal.cfg檔案，可防止使用者透過「設定檔」、「Dimension」、「報表」、「工作區」、「量度」和「篩選器」管理員對自訂設定檔進行變更。
title: 在工作站中鎖定設定檔
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
exl-id: 2604ceea-0e55-4ae7-a286-e5257e974a64
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 5%

---

# 在工作站中鎖定設定檔{#locking-profiles-in-the-workstation}

{{eol}}

套用至「設定檔管理器」的Internal.cfg檔案，可防止使用者透過「設定檔」、「Dimension」、「報表」、「工作區」、「量度」和「篩選器」管理員對自訂設定檔進行變更。

您可以儲存 **[!DNL Internal.cfg]** 檔案至您的自訂設定檔（位於「設定檔管理員」中）。 此設定檔案可防止使用者在管理員中工作時覆寫多個檔案(從 **管理** > **設定檔** 功能表)。

**在配置檔案管理器中鎖定配置檔案**

1. 在工作區中，按一下滑鼠右鍵 **管理** > **設定檔管理員**.

1. 在 **設定檔管理員**，按一下右鍵 **[!DNL Context > Internal.cfg]** 和 **使本地**.

1. 在中按一下右鍵複選標籤 **使用者** 欄和儲存到 `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**附註**:儲存時，只會防止管理員變更設定檔檔案 **[!DNL Internal.cfg]** 設定檔管理員中的自訂設定檔。 您仍可使用 **保存到伺服器** 命令。
