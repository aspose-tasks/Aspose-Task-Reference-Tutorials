---
date: 2025-12-05
description: 學習如何使用 Aspose.Tasks for Java 高效處理 MS Project 的貨幣位數。一步一步的指南，涵蓋 Java 專案檔案處理以及如何載入
  MPP 檔案。
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 處理 MS Project 貨幣位數
url: /zh-hant/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 處理 MS Project 貨幣位數

## 簡介
在本完整教學中，您將學會 **如何使用 Aspose.Tasks for Java 套件處理 MS Project 貨幣** 值。無論您是要建立報表工具、遷移程式，或只是需要從 **java 專案檔** 讀取貨幣設定，本指南都會一步步帶您完成——從載入 *.mpp* 檔案到抽取貨幣位數。完成後，您將能在自己的應用程式中自如處理 MS Project 貨幣資料。

## 快速答覆
- **哪個函式庫可讀取 MS Project 檔案？** Aspose.Tasks for Java。  
- **取得貨幣位數需要多少行程式碼？** 載入專案後只需三行簡潔程式碼。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式環境需購買商業授權。  
- **支援哪個 Java 版本？** Java 8 或以上（任何可執行 Aspose.Tasks 的 JDK）。  
- **我可以取得其他 Project 屬性嗎？** 可以 – Aspose.Tasks 提供完整的 Project 欄位（例如開始日期、成本費率等）。

## 什麼是 MS Project 貨幣？
`ms project currency` 指的是 Microsoft Project 在顯示金額時所使用的數值精度（小數位數）。它在專案檔中以 **CURRENCY_DIGITS** 屬性儲存，決定金額是以整數、單小數、雙小數等方式呈現。

## 為什麼使用 Aspose.Tasks 來處理 MS Project 貨幣？
- **不需安裝 Microsoft Project** – 直接在任何支援 Java 的平台上操作 *.mpp* 檔案。  
- **強型別安全** – API 回傳強型別值，減少解析錯誤。  
- **效能優化** – 快速載入大型專案，僅抽取所需欄位。  
- **跨平台** – 可在 Windows、Linux 或 macOS 上執行，無需修改。

## 先決條件
在開始之前，請確保您具備以下條件：

1. **Java 開發環境** – 已安裝並設定 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從官方網站下載最新 JAR： [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)。  
3. **基本的 Java 知識** – 能建立 Java 專案、加入外部函式庫，並執行 `main` 方法。

## 匯入套件
首先，匯入我們需要的類別。  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 步驟 1：定義資料目錄
指定包含您的 **java 專案檔** (`*.mpp`) 的資料夾。  
```java
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為 `project.mpp` 所在的絕對或相對路徑。

## 步驟 2：載入 MPP 檔案  
現在我們將示範 **如何使用 Aspose.Tasks 載入 mpp** 檔案。  
```java
Project project = new Project(dataDir + "project.mpp");
```
確保檔名完全相符；否則會拋出 `IOException`。

## 步驟 3：取得貨幣位數  
在載入專案後，提取 **MS Project 貨幣** 位數只需一行程式碼：  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
此呼叫會回傳一個 `Integer`，表示小數位數（例如 `2` 代表分）。此值會印到主控台，您亦可將其存入變數以供後續處理。

## 常見問題與提示
- **找不到檔案** – 再次確認 `dataDir` 路徑，並確保檔名正確且包含 `.mpp` 副檔名。  
- **不支援的檔案版本** – Aspose.Tasks 支援 Project 2000‑2024 格式；較舊或損毀的檔案可能需要先轉換。  
- **未設定授權** – 開發階段可使用試用版，但正式上線必須套用有效授權，以免出現評估水印。

## 常見問答

**Q: Aspose.Tasks 能處理除貨幣位數之外的其他 Project 屬性嗎？**  
A: 可以，Aspose.Tasks 提供廣泛功能，可操作 Task、Resource、Custom Field 等多種 Project 資訊。

**Q: Aspose.Tasks 適合企業級應用嗎？**  
A: 絕對適合，Aspose.Tasks 為企業級專案設計，具備高效能與可擴充性。

**Q: Aspose.Tasks 支援跨平台開發嗎？**  
A: 支援，您可在任何支援 Java Runtime Environment 的平台（Windows、Linux、macOS）上使用 Aspose.Tasks for Java。

**Q: 我可以先試用 Aspose.Tasks 再決定是否購買嗎？**  
A: 可以，您可從[此處](https://releases.aspose.com/)下載免費試用版。

**Q: 我該向哪裡尋求 Aspose.Tasks 的支援？**  
A: 您可在 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)取得支援。

---

**最後更新：** 2025-12-05  
**測試環境：** Aspose.Tasks for Java 24.11（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}