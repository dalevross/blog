---
layout: post
title: "Coding Through the Alphabet - Fibonacci in XSLT"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in XSLT. Part of Coding Through The Alphabet."
tags:
  - XSLT
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
---

XSLT is a language for transforming XML documents. It is Turing-complete and capable of general computation through recursive templates, as demonstrated in this Fibonacci implementation.

## How to test

**Prerequisites:** `xsltproc`

- Ubuntu/Debian: `sudo apt install xsltproc`
- macOS: Pre-installed (or `brew install libxslt`)

```bash
xsltproc fibonacci.xsl input.xml
```

**Expected output:**
```
0
1
1
2
3
5
8
13
21
34
```

## Source Code

```xslt
<?xml version="1.0" encoding="UTF-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

  <xsl:output method="text"/>

  <xsl:template match="/">
    <xsl:call-template name="fibonacci">
      <xsl:with-param name="a" select="0"/>
      <xsl:with-param name="b" select="1"/>
      <xsl:with-param name="count" select="10"/>
    </xsl:call-template>
  </xsl:template>

  <xsl:template name="fibonacci">
    <xsl:param name="a"/>
    <xsl:param name="b"/>
    <xsl:param name="count"/>
    <xsl:if test="$count > 0">
      <xsl:value-of select="$a"/>
      <xsl:text>&#10;</xsl:text>
      <xsl:call-template name="fibonacci">
        <xsl:with-param name="a" select="$b"/>
        <xsl:with-param name="b" select="$a + $b"/>
        <xsl:with-param name="count" select="$count - 1"/>
      </xsl:call-template>
    </xsl:if>
  </xsl:template>

</xsl:stylesheet>
```
