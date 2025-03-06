---
title: 在 Aspose.Tasks 中編寫和讀取 MS 專案公式
linktitle: 在 Aspose.Tasks 中寫入和讀取公式
second_title: Aspose.Tasks Java API
description: 學習使用 Aspose.Tasks for Java 有效率地編寫和讀取 MS Project 公式。提升您的專案管理技能。
weight: 12
url: /zh-hant/java/formulas/write-read-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中編寫和讀取 MS 專案公式

## 介紹
在專案管理領域，有效處理資料至關重要。 Aspose.Tasks for Java 是一個強大的解決方案，有助於從 Microsoft Project 檔案中操作和提取資料。它提供的一項強大功能是能夠編寫和讀取 MS Project 公式。本教學將引導您完成利用此功能來增強專案管理任務的過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。
2.  Aspose.Tasks for Java：從下列位置下載並安裝 Aspose.Tasks for Java：[這裡](https://releases.aspose.com/tasks/java/).
3. 整合開發環境 (IDE)：選擇您首選的 IDE 進行 Java 開發。

## 導入包
首先，將必要的套件匯入您的 Java 專案：
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## 第1步：設定資料目錄
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
```
在此步驟中，定義 MS Project 檔案所在的目錄。
## 步驟2：載入專案文件
```java
Project project = new Project(dataDir + "project.mpp");
```
在這裡，將 MS Project 檔案載入到`Project`用於操縱的對象。
## 第 3 步：定義自訂公式
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
此步驟涉及使用使任務成本加倍的公式建立自訂欄位。
## 步驟 4：新增任務並設定成本
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
這裡新增了一個新任務，並將其成本設為 100。
## 第5步：儲存專案文件
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
最後儲存修改後的工程文件。

## 結論
在本教程中，我們探索如何使用 Aspose.Tasks for Java 編寫和讀取 MS Project 公式。透過執行這些步驟，您可以有效地操作專案資料以滿足您的特定要求。
## 常見問題解答
### Aspose.Tasks 與所有版本的 MS Project 相容嗎？
Aspose.Tasks 提供與各種版本的 MS Project 的兼容性，確保使用者的靈活性。
### 我可以將 Aspose.Tasks 整合到我現有的 Java 專案中嗎？
絕對地！ Aspose.Tasks 透過簡單的 API 使用提供與 Java 專案的無縫整合。
### 我可以建立的公式類型有任何限制嗎？
透過 Aspose.Tasks，您可以非常靈活地根據您的專案需求建立自訂公式。
### Aspose.Tasks支援多平台部署嗎？
是的，Aspose.Tasks 支援跨多個平台部署，增強了其多功能性。
### 我如何獲得 Aspose.Tasks 的技術支援？
如需技術援助和社區支持，請訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
