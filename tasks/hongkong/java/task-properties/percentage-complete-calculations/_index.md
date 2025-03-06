---
title: Aspose.Tasks 中任務的完成百分比計算
linktitle: Aspose.Tasks 中任務的完成百分比計算
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks for Java 並簡化專案進度追蹤。輕鬆計算任務百分比以實現高效的專案管理。
weight: 25
url: /zh-hant/java/task-properties/percentage-complete-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中任務的完成百分比計算

## 介紹
歡迎閱讀我們關於使用 Aspose.Tasks for Java 掌握任務百分比計算的深入指南。 Aspose.Tasks 是一個功能強大的 Java 函式庫，專為處理 Microsoft Project 檔案而設計，為專案管理提供了一組強大的功能。在本教程中，我們將專注於完成百分比計算，為您提供有效監控和分析專案進度的知識。
## 先決條件
在開始之前，請確保您具備以下先決條件：
- Java 開發環境：確保您的系統上安裝了 Java。
-  Aspose.Tasks 函式庫：下載適用於 Java 的 Aspose.Tasks 函式庫[這個連結](https://releases.aspose.com/tasks/java/).
## 導入包
讓我們先導入 Aspose.Tasks for Java 專案所需的套件。在您的專案中包含以下程式碼片段：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
現在，讓我們分解每個步驟並進行詳細說明。
## 第1步：導入包
第一步，我們匯入必要的套件來設定我們的 Aspose.Tasks 專案。
## 步驟二：設定文檔目錄
使用以下命令定義文件目錄的路徑`dataDir`多變的。確保您的 Microsoft Project 檔案（例如“Software Development.mpp”）位於此目錄中。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
```
## 第三步：載入項目
初始化一個新的`Project`物件並將 Microsoft Project 檔案載入到專案實例中。
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## 步驟 4：檢索任務集合
取得項目的根任務並使用以下命令將其子任務作為集合檢索`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## 第 5 步：列印完成百分比
循環瀏覽集合中的每個任務並列印完成百分比、工作完成百分比和實際完成百分比。
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
對專案中的每項任務重複這些步驟，以深入了解每項任務的進度。
## 結論
恭喜！您已成功掌握使用 Aspose.Tasks for Java 的任務百分比計算。這個強大的程式庫使開發人員能夠有效地管理和分析專案進度。
## 常見問題解答
### Q：在哪裡可以找到 Aspose.Tasks 文件？
文件可用[這裡](https://reference.aspose.com/tasks/java/).
### Q：如何下載 Java 版的 Aspose.Tasks 函式庫？
你可以下載它[這裡](https://releases.aspose.com/tasks/java/).
### Q：有免費試用嗎？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### Q：我可以在哪裡獲得 Aspose.Tasks 的支援？
造訪支援論壇[這裡](https://forum.aspose.com/c/tasks/15).
### Q：如何獲得臨時許可證？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
