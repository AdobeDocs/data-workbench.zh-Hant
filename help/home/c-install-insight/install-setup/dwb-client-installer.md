---
description: 「資料工作台」提供安裝工作站（用戶端）應用程式的設定精靈。
title: 工作站設定嚮導
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: b5a22e7a050d7c01570286dcb54e368f7ecdbcd8

---


# 工作站設定嚮導{#workstation-setup-wizard}

「資料工作台」提供安裝工作站（用戶端）應用程式的設定精靈。

## 使用安裝嚮導安裝工作站 {#section-58da9bb6196c46eab3b54146913fdcb8}

啟動安裝嚮導執行檔並逐步執行每個步驟以安裝工作站客戶端程式。 安裝工作站後，您可以連接到伺服器和配置檔案。

1. 按兩下工作站安裝程式執行檔。
1. 按一下 **是** ，允許程式安裝在Windows上。
1. 為設定 **嚮導選擇** 「語言」。

   嚮導將開啟：

   ![](assets/6_4_workstation_wizard.png)

1. 按一 **下** 「歡迎使用資 **料工作台設定精靈」對話方塊上的「下一步** 」。

1. 選擇安裝新 **安裝** ，或 **升級或修復現有安裝** 。

   **「新安裝** 」會覆寫任何先前安裝的檔案。

   **升級** ，將工作站更新為最新版本，或者讓您修復現有安裝。 資料工作台將比較已安裝的 **Insight.exe** 檔案，並在有較新版本的用戶端時執行工作站設定精靈。

1. 選擇安裝位置：

   **典型** ，安裝到預設資料夾和位置。

   * 程式檔案預設保存為：

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * 資料檔案（描述檔、憑證、追蹤記錄檔和使用者檔案）預設會儲存為：

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >一開始 ****** 將會安裝不含伺服器詳細資訊的一般Insight.cfg檔案。 建議您使用新安裝的 ***Insight.cfg*** 檔案並加以自訂，而非從先前的安裝移動檔案。 由於安裝工作站的路徑已經更改，因此建議添加字型、刪除 *User資料夾*，以及刪除*TraceFileComponent *。

1. （可選）選 **擇「自定** 」以選擇語言包以及程式和資料檔案的位置。
1. 在「開始」菜 **單中選擇快捷方式的位置**。

   ![](assets/6_4_workstation_wizard_folder.png)

   單 **擊「不建立開始菜單」資料夾** ，不在Windows開始菜單上安裝快捷方式。

1. 按&#x200B;**「下一步」。** 將顯示選定檔案位置路徑和語言的摘要。 按一下&#x200B;**安裝.**

1. 找到「資 **料工作台憑證」**。

   如果安裝精靈在安裝期間找不到資料工作台憑證，則會開啟對話方塊以瀏覽憑證的位置( **.pem** 檔案，預設位於用戶端 **Certificates資料夾)，或按一下「** Skip **** 」在安裝後尋找憑證。

   找到 **證書後** ，按一下「安裝」。

1. 安裝精靈完成並安裝資料工作台後，按一下「完 **成** 」以完成安裝。

   >[!NOTE]
   >
   >工作站設定嚮導的預設日誌位置，位 **[!DNL 於C:\Users\<userName>`\AppData\Local\Temp.]**

   選取「啟 **動應用程式** 」核取方塊，以在設定後開啟工作台。

1. **配置檔案中** ，與伺服器的 **[!DNL Insight.cfg]** 連接。

   在安裝工作站後，「增強工作站配置體驗」工作區將會開啟，其中包含在 [](/help/home/c-get-started/c-insght-config-param.md)** Insight.cfg檔案中輸入伺服器連線資訊的其他資訊，以及從下拉式清單中選取描述檔的選項。 您也可以檢視伺服器的連線狀態。

   ![](assets/6_4_workstation_install_conf_conn.png)

## 安裝資料夾 {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

「資料工作台」檔案夾結構有兩個安裝位置：

* **Program Files** The **Insight.exe** and supporting client files(**Insight.ini**) are revault at

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* Appdata **資料夾** 。

   **Insight.cfg**、描述檔、憑證、追蹤記錄檔和使用者檔案現在預設位於

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   您可以在檔案中設定 **Appdata** 檔案夾的 `Insight.ini` 路徑：

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## 卸載工作站 {#section-5ce2e233fe4348469ef1b3c451dd5b70}

資料工作台現在包含可執行檔，以解除安裝工作站(預設位於 **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**)。

啟動並遵循步驟，從硬碟移除「資料工作台工作站」檔案。

>[!NOTE]
>
>您可以使用「開始 **功能表」中的「解除安裝資料工作台」(** Uninstall Data Workbench **)捷徑，或從「 >」(** >)，從資料夾啟動unins000.exe執行檔 **[!UICONTROL Control Panel]****[!UICONTROL Program and Features]**。
