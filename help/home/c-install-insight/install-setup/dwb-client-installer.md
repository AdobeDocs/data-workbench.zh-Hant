---
description: Data Workbench提供安裝工作站（客戶端）應用程式的設定嚮導。
title: 工作站設定精靈
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
exl-id: bfd9f2ad-282a-4be8-9f66-53e045648ef1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 1%

---

# 工作站設定精靈{#workstation-setup-wizard}

{{eol}}

Data Workbench提供安裝工作站（客戶端）應用程式的設定嚮導。

## 使用安裝精靈安裝工作站 {#section-58da9bb6196c46eab3b54146913fdcb8}

啟動安裝嚮導執行檔，並逐步完成每個步驟以安裝工作站客戶端程式。 安裝工作站後，您可以連線至伺服器和設定檔。

1. 按兩下工作站安裝程式執行檔。
1. 按一下 **是** 允許程式在Windows上安裝。
1. 選取 **語言** 的URL。

   嚮導將開啟：

   ![](assets/6_4_workstation_wizard.png)

1. 按一下 **下一個** 在 **歡迎使用Data Workbench設定精靈** 對話框。

1. 選擇以安裝 **新安裝** 或 **升級或修復** 現有安裝。

   **新安裝** 會覆寫任何先前安裝的檔案。

   **升級** 將您的工作站更新至最新版本，或讓您修復現有安裝。 Data Workbench將比較已安裝 **Insight.exe** 檔案，並在有較新版本的客戶端可用時運行「工作站設定嚮導」。

1. 選擇安裝位置：

   **典型** 安裝至預設資料夾和位置。

   * 預設情況下，程式檔案將保存為：

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * 資料檔案（設定檔、憑證、追蹤記錄和使用者檔案）預設會儲存為：

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >通用 ***Insight.cfg*** 最初將安裝不含伺服器詳細資訊的檔案。 建議您使用新安裝的 ***Insight.cfg*** 檔案，而非從先前安裝移動檔案。 由於安裝工作站的路徑已改變，因此添加了字型，移除了 *使用者資料夾*，並建議移除*TraceFileComponent *。

1. （可選）選取 **自訂** 選擇語言包以及程式和資料檔案的位置。
1. 選擇位置 **「開始」菜單中的快捷方式**.

   ![](assets/6_4_workstation_wizard_folder.png)

   按一下 **不建立「開始」菜單資料夾** 不要在Windows「開始」菜單上安裝快捷方式。

1. 按&#x200B;**「下一步」。** 將顯示所選檔案位置路徑和語言的摘要。 按一下&#x200B;**安裝.**

1. 找出 **Data Workbench憑證**.

   如果安裝精靈在安裝期間找不到Data Workbench憑證，則會開啟對話方塊以瀏覽至憑證的位置( **.pem** 檔案預設位於用戶端中 **憑證** )，或按一下 **略過** 以在安裝後尋找憑證。

   按一下 **安裝** 找到憑證後。

1. 安裝精靈完成並安裝Data Workbench後，按一下 **完成** 完成設定。

   >[!NOTE]
   >
   >工作站設定精靈的預設記錄位置，位於  `C:\Users\<userName>\AppData\Local\Temp`.

   選取 **Launch應用程式** 核取方塊，在設定後開啟工作台。

1. **配置連接** 到伺服器 **[!DNL Insight.cfg]** 檔案。

   安裝工作站後，增強工作站設定體驗工作區將會開啟，並提供關於 [輸入伺服器連接資訊](/help/home/c-get-started/c-insght-config-param.md) 在 *Insight.cfg* 檔案和從下拉式清單中選取設定檔的選項。 您也可以檢視與伺服器的連線狀態。

   ![](assets/6_4_workstation_install_conf_conn.png)

## 安裝資料夾 {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

Data Workbench資料夾結構有兩個安裝位置：

* **程式檔案** 此 **Insight.exe** 和支援的客戶端檔案(**Insight.ini**)現在預設位於

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* 此 **Appdata** 檔案夾。

   **Insight.cfg**、設定檔、憑證、追蹤記錄和使用者檔案現在預設位於

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   您可以為 **Appdata** 檔案夾 `Insight.ini` 檔案：

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## 解除安裝工作站 {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Data Workbench現在包含可解除安裝工作站的執行檔(預設位於 **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**)。

啟動並按照步驟從硬碟中刪除Data Workbench工作站檔案。

>[!NOTE]
>
>您可以啟動 **unins000.exe** 執行檔，使用 **解除安裝Data Workbench** 從「開始」菜單或從 **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
