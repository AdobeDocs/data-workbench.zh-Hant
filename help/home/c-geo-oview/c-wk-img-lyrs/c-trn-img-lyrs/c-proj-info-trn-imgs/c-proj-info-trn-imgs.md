---
description: Data Workbench Geography支援經緯度投影和通用橫麥卡托(UTM)投影，適用於所有地形影像層來源。
title: 指定地形影像的投影資訊
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%

---

# 指定地形影像的投影資訊{#specifying-projection-information-for-terrain-images}

Data Workbench Geography支援經緯度投影和通用橫麥卡托(UTM)投影，適用於所有地形影像層來源。

原始未投影點陣圖和未投影的一般影像需要投影資訊。 可以指定具有嵌入投影資訊的影像的投影資訊，但通常不需要，因為投影的參數是由嵌入影像本身的大地資料自動確定的。 以下各節提供有關在[!DNL Terrain Images.cfg]檔案中指定這些投影格式的詳細資訊。
