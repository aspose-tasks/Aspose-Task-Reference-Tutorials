---
title: 在 Aspose.Tasks 專案中配置甘特圖視圖
linktitle: 在 Aspose.Tasks 專案中配置甘特圖視圖
second_title: Aspose.Tasks Java API
description: 了解如何使用 Java 在 Aspose.Tasks 中配置甘特 MS 專案圖表視圖。自訂項目並在甘特圖中逐步將其視覺化。
weight: 10
url: /zh-hant/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 專案中配置甘特圖視圖

## 介紹
在本教程中，您將學習如何使用 Java 在 Aspose.Tasks 專案中配置甘特 MS 專案圖表視圖。 Aspose.Tasks 是一個功能強大的 Java API，可讓您以程式設計方式處理 Microsoft Project 檔案。透過執行這些步驟，您將能夠根據專案的要求自訂甘特圖視圖。
## 先決條件
在開始之前，請確保您具備以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。
2.  Aspose.Tasks 函式庫：下載並安裝 Aspose.Tasks 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).
3. 整合開發環境 (IDE)：選擇您喜歡的 IDE。本教學使用 IntelliJ IDEA，但您可以使用任何您熟悉的 IDE。
## 導入包
首先，您需要匯入必要的套件以在 Java 專案中使用 Aspose.Tasks。將以下導入語句加入您的 Java 檔案：
```java
import com.aspose.tasks.*;
```
現在，讓我們將配置甘特 MS 專案圖表視圖的過程分解為逐步說明：
## 第1步：設定資料目錄
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`以及專案資料目錄的路徑。
## 步驟2：載入專案文件
```java
Project project = new Project(dataDir + "project.mpp");
```
載入您的專案文件（`project.mpp`在此範例中）使用`Project`來自 Aspose.Tasks 的類別。
## 第 3 步：新增活動
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
使用以下命令在專案中建立新任務`Task`類別並將其新增至根任務的子層級。
## 第 4 步：定義自訂屬性
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
使用定義一個新的自訂屬性`ExtendedAttributeDefinition`類別並將其添加到項目的擴展屬性中。
## 步驟 5：向任務新增自訂屬性
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
使用以下命令將自訂屬性新增至已建立的任務中`createExtendedAttribute`方法。
## 第 6 步：自訂表格
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
透過新增具有指定寬度、標題和對齊方式的文字屬性欄位來自訂表格。
## 第7步：保存項目
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
使用配置的甘特 MS 專案圖表視圖儲存專案。產生的檔案可以在 Microsoft Project 2010 中開啟。
## 結論
恭喜！您已使用 Java 在 Aspose.Tasks 專案中成功配置了甘特 MS 專案圖表視圖。現在您可以根據專案的需求自訂專案屬性並在甘特圖中將它們視覺化。
## 常見問題解答
### Q：我可以將 Aspose.Tasks 與其他程式語言一起使用嗎？
答：是的，Aspose.Tasks 可用於多種程式語言，包括 .NET、Java 和 C++.
### Q：Aspose.Tasks 有免費試用版嗎？
答：是的，您可以從以下位置下載免費試用版：[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到對 Aspose.Tasks 的支援？
答：您可以在以下位置找到支援並提出問題[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
### Q：如何購買 Aspose.Tasks 的授權？
答：您可以從以下位置購買許可證[這裡](https://purchase.aspose.com/buy).
### Q：出於測試目的，我需要臨時許可證嗎？
答：是的，您可以從以下機構獲得臨時許可證：[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
