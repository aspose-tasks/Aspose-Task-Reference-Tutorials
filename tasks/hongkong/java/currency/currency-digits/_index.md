---
date: 2026-02-10
description: 學習如何取得貨幣值、讀取 MS Project 檔案，並使用 Aspose.Tasks 在 Java 中轉換專案檔。一步一步的指南，教您提取貨幣數字。
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 從 MS Project 取得貨幣
url: /zh-hant/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 從 MS Project 獲取貨幣資訊

## 介紹
如果你想了解 **如何取得貨幣** 資訊從 Microsoft Project 檔案，你已經來對地方了。在本完整教學中，你將學會 **如何使用 ms project currency** 值，透過 Aspose.Tasks for Java 函式庫。無論你是要建立報表工具、遷移程式，或只是需要讀取 **java 專案檔案** 的貨幣設定，本指南都會一步步帶領你——從載入 *.mpp* 檔案到擷取貨幣位數。完成後，你將能在自己的應用程式中自如處理 ms project currency 資料。

## 快速解答
- **什麼程式庫可讀取 MS Project 檔案？** Aspose.Tasks for Java。  
- **取得貨幣位數需要多少行程式碼？** 只要在載入專案後寫三行簡潔程式碼。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式環境需購買商業授權。  
- **支援哪個 Java 版本？** Java 8 或以上（任何能執行 Aspose.Tasks 的 JDK）。  
- **我可以取得其他 Project 屬性嗎？** 可以 – Aspose.Tasks 提供完整的 Project 欄位（例如開始日期、成本率等）。

## 什麼是 ms project currency？
`ms project currency` 指的是 Microsoft Project 在顯示金額時使用的數值精度（小數位數）。它以 **CURRENCY_DIGITS** 屬性儲存在 Project 檔案中，決定金額是以整數、單小數、雙小數等形式呈現。

## 為什麼使用 Aspose.Tasks 處理 ms project currency？
- **不需要安裝 Microsoft Project** – 可直接在任何支援 Java 的平台上處理 *.mpp* 檔案。  
- **強型別安全** – API 回傳強型別值，減少解析錯誤。  
- **效能最佳化** – 快速載入大型專案，僅提取所需欄位。  
- **跨平台** – 可在 Windows、Linux 或 macOS 上執行，無需修改。

## 前置條件
在開始之前，請確保你具備以下條件：

1. **Java 開發環境** – 已安裝並設定 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從官方網站下載最新 JAR： [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)。  
3. **基本的 Java 知識** – 需要能建立 Java 專案、加入外部函式庫，並執行 `main` 方法。  

## 匯入套件
首先，匯入我們需要的類別。  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 步驟 1：定義資料目錄
指定包含你的 **java 專案檔案** (`*.mpp`) 的資料夾。  
```java
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為 `project.mpp` 所在的絕對或相對路徑。

## 步驟 2：載入 MPP 檔案  
現在我們來看看 **如何載入 mpp** 檔案，使用 Aspose.Tasks。  
```java
Project project = new Project(dataDir + "project.mpp");
```
確保檔名完全相符；否則會拋出 `IOException`。

## 步驟 3：取得貨幣位數  
專案載入後，擷取 **ms project currency** 位數只需要一行程式碼：  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
此呼叫會回傳一個 `Integer`，代表小數位數（例如 `2` 代表分）。結果會印到主控台，你也可以將其存入變數以便後續處理。

## 常見問題與技巧
- **找不到檔案** – 再次確認 `dataDir` 路徑，並確保檔名正確且包含 `.mpp` 副檔名。  
- **不支援的檔案版本** – Aspose.Tasks 支援 Project 2000‑2024 格式；較舊或損毀的檔案可能需要轉換。  
- **未設定授權** – 開發階段可使用試用版，但正式環境必須套用有效授權以避免評估浮水印。

## 常見問答

**Q:** Aspose.Tasks 能處理除貨幣位數之外的其他 Project 屬性嗎？  
**A:** 可以，Aspose.Tasks 提供廣泛功能，讓你操作 Project 檔案的各種面向，如工作、資源與自訂欄位。

**Q:** Aspose.Tasks 適合企業級應用嗎？  
**A:** 絕對適合，Aspose.Tasks 設計符合企業級專案的需求，提供高效能與可擴充性。

**Q:** Aspose.Tasks 支援跨平台開發嗎？  
**A:** 可以，您可以在任何支援 Java 執行環境的作業系統（Windows、Linux、macOS）上使用 Aspose.Tasks for Java。

**Q:** 我可以在購買前試用 Aspose.Tasks 嗎？  
**A:** 可以，您可從 [此處](https://releases.aspose.com/) 下載免費試用版。

**Q:** 我可以從哪裡取得 Aspose.Tasks 的支援？  
**A:** 您可以在 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 上取得支援。

## 結論
你現在已了解 **如何取得貨幣** 位數，從 MS Project 檔案使用 Aspose.Tasks for Java。流程簡單：載入專案、呼叫 `project.get(Prj.CURRENCY_DIGITS)`，然後在應用程式中使用結果。歡迎以相同模式探索其他專案屬性，並將此邏輯整合至更大型的報表或遷移解決方案中。

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks for Java (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}