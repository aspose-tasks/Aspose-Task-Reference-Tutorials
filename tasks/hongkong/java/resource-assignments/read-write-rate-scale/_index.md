---
title: Aspose.Tasks 中資源分配的讀寫速率範圍
linktitle: Aspose.Tasks 中資源分配的讀寫速率範圍
second_title: Aspose.Tasks Java API
description: 透過這個綜合教程，了解如何在 Aspose.Tasks for Java 中有效管理資源分配比例。
weight: 20
url: /zh-hant/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中資源分配的讀寫速率範圍

## 介紹
在本教程中，我們將深入研究使用 Aspose.Tasks for Java 來管理資源分配率比例，Aspose.Tasks for Java 是一個用於以程式設計方式處理 Microsoft Project 檔案的強大函式庫。透過執行這些步驟，您將能夠有效地操作 Java 應用程式中資源分配的速率比例設定。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. Java 開發環境：確保您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Aspose.Tasks for Java Library：下載並安裝 Aspose.Tasks for Java 函式庫[這裡](https://releases.aspose.com/tasks/java/).

## 導入包
首先，您需要匯入必要的套件才能使用 Aspose.Tasks 功能。 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## 第 1 步：設定您的項目
首先設定您的 Java 專案並將 Aspose.Tasks 庫包含在您的依賴項中。
## 第 2 步：載入專案文件
將您想要使用的專案檔案載入到您的 Java 應用程式中。
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## 第 3 步：新增任務
將新任務新增到您的專案中。
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## 第 4 步：定義資源
定義物質和非物質資源並指定其類型。
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## 步驟 5：為任務分配資源
將先前定義的資源及其費率等級類型指派給任務。
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## 第 6 步：儲存項目
保存具有修改後的資源分配的項目。
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## 第 7 步：檢索資源分配
重新載入已儲存的項目並檢索資源分配以驗證費率比例設定。
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## 結論
在 Aspose.Tasks for Java 中管理資源分配比例對於有效的專案管理至關重要。透過遵循此逐步指南，您可以無縫地操作 Java 應用程式中資源分配的速率比例設定。
## 常見問題解答
### Q1：我可以在任何 Java IDE 中使用 Aspose.Tasks for Java 嗎？
答：是的，Aspose.Tasks for Java 與所有主要 Java IDE 相容，包括 IntelliJ IDEA、Eclipse 和 NetBeans。
### Q2：Aspose.Tasks 是否支援 MPP 以外的其他檔案格式？
答：是的，Aspose.Tasks 支援各種檔案格式，包括 MPP、XML 和 HTML。
### Q3：Aspose.Tasks適合企業級專案管理嗎？
答：當然，Aspose.Tasks 提供了管理任何規模專案的全面功能，使其適合企業級專案管理。
### 問題 4：我可以在費率範圍之外進一步自訂資源分配嗎？
答：是的，Aspose.Tasks 提供了廣泛的自訂資源分配功能，包括成本、工時和工期調整。
### Q5：有 Aspose.Tasks 支援的社群論壇嗎？
答：是的，您可以在 Aspose.Tasks 論壇上找到支援並與其他使用者互動[這裡](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
