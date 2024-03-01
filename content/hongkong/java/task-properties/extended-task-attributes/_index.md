---
title: Aspose.Tasks 中的擴充任務屬性
linktitle: Aspose.Tasks 中的擴充任務屬性
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks for Java 中的擴充任務屬性。逐步指南、常見問題和支援。立即優化您的專案管理！
type: docs
weight: 16
url: /zh-hant/java/task-properties/extended-task-attributes/
---
## 介紹
歡迎閱讀我們關於在 Aspose.Tasks for Java 中利用擴充任務屬性的綜合指南。 Aspose.Tasks 是一個功能強大的 Java 程式庫，可讓您無縫地處理 Microsoft Project 文件。在本教程中，我們將深入研究擴展任務屬性，並示範如何利用它們來增強專案管理能力。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
- Java 程式設計的基礎知識。
- 在您的電腦上安裝了 Java 開發工具包 (JDK)。
- 整合開發環境 (IDE)，例如 IntelliJ 或 Eclipse。
## 導入包
首先匯入必要的套件來啟動您的 Aspose.Tasks 專案：
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
現在，讓我們將該範例分解為多個步驟來引導您完成該過程：
## 第 1 步：存取任務和擴充屬性
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## 步驟 2：檢索欄位 ID 和值 GUID
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## 步驟 3：處理不同的屬性類型
```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```
對專案中的每個任務重複這些步驟，以探索和操作擴展任務屬性。
## 結論
總之，理解並利用 Aspose.Tasks for Java 中的擴充任務屬性可以顯著增強您的專案管理能力。本指南為您開始這趟旅程奠定了堅實的基礎。
## 經常問的問題
### 我可以透過程式修改擴展任務屬性嗎？
是的，您可以使用 Aspose.Tasks for Java 來修改擴充任務屬性。請參閱文件以取得詳細說明。
### 有試用版嗎？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Tasks for Java 的支援？
如需支持，請訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
### 我怎麼才能獲得臨時許可證？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以購買完整版的 Aspose.Tasks for Java？
您可以購買完整版[這裡](https://purchase.aspose.com/buy).