---
description: 郵件XSL樣式表的代碼示例。
title: 郵件 XSL 樣式表範例
uuid: 846ddf22-e6da-4d37-ba50-d75f850b9a3f
exl-id: 4b868da4-1a3b-454c-940c-8ffd9644c92a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '24'
ht-degree: 41%

---

# 郵件 XSL 樣式表範例{#sample-mail-xsl-style-sheet}

{{eol}}

郵件XSL樣式表的代碼示例。

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="https://www.w3.org/1999/XSL/Transform">
<xsl:template match="/">
<html>
<body>
<h2>Reports</h2>
<xsl:for-each select="REPORTS/REPORT[@format!='xls']">
<img><xsl:attribute name="src">cid:<xsl:value-of select="PATH"/></xsl:attribute></img><p/>
</xsl:for-each>
</body>
</html>
</xsl:template>
</xsl:stylesheet>
```
