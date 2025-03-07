---
title: 在 Java 中將 MS Project 轉換為 SVG
linktitle: 在 Aspose.Tasks 中另存為 SVG
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks 函式庫將 Microsoft Project 檔案儲存為 Java 中的 SVG。帶有程式碼範例的分步指南。
weight: 18
url: /zh-hant/java/project-file-operations/save-as-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中將 MS Project 轉換為 SVG

## 介紹
Aspose.Tasks for Java 是一個功能強大的函式庫，用於處理專案管理文件，允許開發人員操縱專案資料、執行各種操作並高效產生報告。在本教程中，我們將探討如何使用 Aspose.Tasks for Java 將專案儲存為 SVG。 SVG（可擴展向量圖形）是一種廣泛用於在 Web 上顯示向量圖形的格式，提供可擴展性和高品質渲染。
## 先決條件
在我們開始之前，請確保您具備以下條件：
### Java開發環境
確保您的系統上安裝了 Java 開發工具包 (JDK)。您可以從 Oracle 網站下載並安裝 JDK。
### Java 函式庫的 Aspose.Tasks
從網站下載並安裝 Aspose.Tasks for Java 函式庫。您可以在提供的文件中找到下載鏈接[這裡](https://releases.aspose.com/tasks/java/).

## 導入包
首先，您需要在 Java 程式中匯入必要的套件才能使用 Aspose.Tasks 功能。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

現在讓我們將提供的範例分解為多個步驟：
## 第2步：定義資料目錄
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`以及專案文件所在目錄的路徑。
## 第 3 步：載入專案文件
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
此步驟從指定的資料目錄載入名為「HomeMovePlan.mpp」的專案檔案。
## 第 4 步：另存為 SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
此步驟將載入的項目以 SVG 格式儲存在指定的資料目錄中，名稱為「project5.svg」。

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 將專案另存為 SVG。透過遵循提供的步驟，您可以有效地將專案文件轉換為 SVG 格式，從而實現與基於 Web 的應用程式或視覺化工具的無縫整合。
## 常見問題解答
### Aspose.Tasks for Java 是否與所有版本的 Microsoft Project 檔案相容？
是的，Aspose.Tasks for Java 支援各種版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。
### 我可以自訂 SVG 輸出的外觀嗎？
是的，您可以透過調整字體、顏色和佈局配置等參數來自訂 SVG 輸出的外觀。
### Aspose.Tasks for Java 是否需要商業用途授權？
是的，Aspose.Tasks for Java 的商業用途需要有效的授權。您可以從網站取得許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 我可以在購買前試用 Aspose.Tasks for Java 嗎？
是的，您可以從網站要求免費試用 Aspose.Tasks for Java[這裡](https://purchase.aspose.com/buy)評估其特性和功能。
### 在哪裡可以獲得 Aspose.Tasks for Java 的支援？
您可以透過造訪論壇獲得 Aspose.Tasks for Java 的支持[這裡](https://forum.aspose.com/c/tasks/15)，您可以在其中提出問題並與社區互動。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
