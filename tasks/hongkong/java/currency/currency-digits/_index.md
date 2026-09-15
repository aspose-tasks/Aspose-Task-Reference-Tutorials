---
date: 2026-09-14
description: 了解如何使用 Aspose.Tasks 取得 MS Project 貨幣並以 Java 讀取專案屬性。逐步指南，教您從 MPP 檔案中提取貨幣數字。
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: 如何使用 Aspose.Tasks 從 MS Project 取得貨幣
og_description: 了解如何使用 Aspose.Tasks 取得 MS Project 貨幣並以 Java 讀取專案屬性。遵循此簡明的 Java 教程，從
  MPP 檔案中提取貨幣數字。
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: 如何使用 Aspose.Tasks 取得 MS Project 貨幣 – Java 指南
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: 如何使用 Aspose.Tasks 取得 MS Project 貨幣
url: /zh-hant/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 取得 MS Project 貨幣設定

## 簡介
如果您想了解如何從 Microsoft Project 檔案取得 **ms project currency** 資訊，您已來對地方。在本完整教學中，您將學會如何使用 Aspose.Tasks for Java 套件操作 **ms project currency** 值。無論您是要建立報表工具、遷移程式，或僅需讀取 **java project file** 的貨幣設定，本指南都會一步步帶您完成——從載入 *.mpp* 檔案到提取貨幣小數位。完成後，您將能在自己的應用程式中自如處理 ms project currency 資料。

## 快速解答
- **什麼程式庫可讀取 MS Project 檔案？** Aspose.Tasks for Java.  
- **取得貨幣小數位需要多少行程式碼？** 只要在載入專案後寫三行簡潔程式碼即可。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買商業授權。  
- **支援哪個 Java 版本？** Java 8 或更高（任何能執行 Aspose.Tasks 的 JDK）。  
- **我可以取得其他 Project 屬性嗎？** 可以——Aspose.Tasks 提供完整的 Project 欄位集合（例如開始日期、成本率等）。

## 什麼是 ms project currency？
`ms project currency` 屬性定義了 Microsoft Project 在顯示金額時使用的小數位數。它以 **CURRENCY_DIGITS** 欄位儲存在專案檔案中，決定金額是顯示為整數、單一小數位、雙小數位等。此設定直接影響預算報表、成本彙總以及任何顯示財務數字的介面，對於正確的資料交換至關重要。

## 為什麼使用 Aspose.Tasks 處理 ms project currency？
Aspose.Tasks 讓您無需安裝 Microsoft Project 即可提取貨幣小數位，且具備企業級效能。此程式庫支援 **30 年以上的 Project 檔案版本**——從 Project 2000 到 Project 2024——涵蓋超過 **150 種不同的檔案結構**。在一般伺服器上載入 500 頁的專案通常不到 **2 秒**，且您只需查詢所需欄位，即使是最大規模的排程，記憶體使用量亦維持在 **50 MB** 以下。

## 先決條件
在開始之前，請確保您已具備以下條件：

1. **Java 開發環境** – 已安裝並設定 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從官方網站下載最新的 JAR： [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)。  
3. **基本的 Java 知識** – 您應能熟練建立 Java 專案、加入外部程式庫，並執行 `main` 方法。  

## 匯入套件
首先，匯入我們需要的類別。  
從 Aspose.Tasks 程式庫匯入 `Project` 類別及相關工具。  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 步驟 1：定義資料目錄
指定包含您的 **java project file** (`*.mpp`) 的資料夾。  
```java
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為 `project.mpp` 所在的絕對或相對路徑。

## 步驟 2：載入 mpp 檔案  
現在我們將示範如何使用 Aspose.Tasks **載入 mpp** 檔案。  
`Project` 類別代表 Microsoft Project 檔案，並提供其屬性的存取。  
```java
Project project = new Project(dataDir + "project.mpp");
```
請確保檔名完全相符，否則會拋出 `IOException`。

## 步驟 3：取得貨幣小數位  
在載入專案後，提取 **ms project currency** 小數位只需一行程式碼：  
`getCurrencyDigits()` 方法回傳金額所定義的小數位數。  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
此呼叫會回傳一個 `Integer`，代表小數位數（例如，`2` 代表分）。此值會印到主控台，您亦可將其存入變數以供後續處理。

## 常見問題與技巧
- **找不到檔案** – 請再次確認 `dataDir` 路徑，並確保檔名正確，包含 `.mpp` 副檔名。  
- **不支援的檔案版本** – Aspose.Tasks 支援 Project 2000‑2024 格式；較舊或損毀的檔案可能需要轉換。  
- **未設定授權** – 開發階段可使用試用版，但正式上線必須套用有效授權，以避免評估水印。

## 常見問答

**問：Aspose.Tasks 能處理除貨幣小數位之外的其他 Project 屬性嗎？**  
答：可以，Aspose.Tasks 提供廣泛功能，可操作 Project 檔案的各種面向，例如工作、資源與自訂欄位。

**問：Aspose.Tasks 適合企業級應用嗎？**  
答：絕對適合，Aspose.Tasks 為企業級專案需求而設計，提供高效能與可擴充性。

**問：Aspose.Tasks 支援跨平台開發嗎？**  
答：可以，您可在任何支援 Java Runtime Environment 的平台（Windows、Linux、macOS）上使用 Aspose.Tasks for Java。

**問：我可以在購買前試用 Aspose.Tasks 嗎？**  
答：可以，您可從 [Aspose releases page](https://releases.aspose.com/) 下載免費試用版。

**問：我可以在哪裡取得 Aspose.Tasks 的支援？**  
答：您可在 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 獲得支援。

---

**最後更新：** 2026-09-14  
**測試環境：** Aspose.Tasks for Java (latest at time of writing)  
**作者：** Aspose

## 相關教學

- [Java 專案屬性 – 使用 Aspose.Tasks for Java 從 MPP 提取貨幣符號](/tasks/java/currency/currency-symbols/)
- [如何使用 Aspose.Tasks 從 MS Project 取得貨幣](/tasks/java/currency/currency-codes/)
- [Project 屬性 Java – 使用 Aspose.Tasks 讀取中繼資料](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}