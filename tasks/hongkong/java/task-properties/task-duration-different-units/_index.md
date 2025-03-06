---
title: 使用 Aspose.Tasks 不同單位的任務持續時間
linktitle: 使用 Aspose.Tasks 不同單位的任務持續時間
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks 探索 Java 專案中的任務持續時間管理。準確計算和轉換持續時間（以分鐘、天、小時、週和月為單位）。
type: docs
weight: 32
url: /zh-hant/java/task-properties/task-duration-different-units/
---
## 介紹
在專案管理領域，理解和管理任務持續時間是一個關鍵面向。 Aspose.Tasks for Java 提供了一個強大的工具集來有效地處理這個問題。在本教程中，我們將指導您使用 Aspose.Tasks 檢索不同單位的任務持續時間。
## 先決條件
在我們深入學習本教學之前，請確保您具備以下條件：
- 安裝了 Java 開發工具包 (JDK)
-  Java 函式庫的 Aspose.Tasks。你可以下載它[這裡](https://releases.aspose.com/tasks/java/)
- 對 Java 程式設計有基本的了解
## 導入包
在您的 Java 專案中，包含 Aspose.Tasks 函式庫。在程式碼開頭新增以下導入語句：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## 第 1 步：設定您的項目
首先在您首選的整合開發環境 (IDE) 中建立一個新的 Java 專案。確保在專案的依賴項中包含 Aspose.Tasks 庫。
## 第 2 步：閱讀項目模板
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//讀取 MS Project 範本文件
String fileName = dataDir + "project.xml";
//將輸入檔讀取為 Project
Project project = new Project(fileName);
```
確保更換`"Your Document Directory"`與專案文件的實際路徑。
## 第 3 步：檢索任務
```java
//取得任務以不同格式計算其持續時間
Task task = project.getRootTask().getChildren().getById(1);
```
在這裡，我們從專案中獲取一個任務。調整`getById(1)`基於您的專案的任務 ID。
## 第 4 步：持續時間（以分鐘為單位）
```java
//取得持續時間（以分鐘為單位）
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
此步驟計算任務持續時間（以分鐘為單位）。
## 第 5 步：持續時間（以天為單位）
```java
//取得持續時間（以天為單位）
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
此步驟計算任務持續時間（以天為單位）。
## 第 6 步：持續時間（以小時為單位）
```java
//取得持續時間（以小時為單位）
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
此步驟計算任務持續時間（以小時為單位）。
## 第 7 步：持續時間（以周為單位）
```java
//取得持續時間（以週為單位）
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
此步驟計算任務持續時間（以週為單位）。
## 步驟 8：持續時間（以月為單位）
```java
//取得持續時間（以月為單位）
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
此步驟計算任務持續時間（以月為單位）。
## 結論
使用 Aspose.Tasks for Java 可以輕鬆管理任務持續時間。本教學逐步引導您完成整個過程，清楚地介紹了不同的時間單位。
## 經常問的問題
### Q：我可以在任何 Java IDE 中使用 Aspose.Tasks for Java 嗎？
是的，Aspose.Tasks for Java 與任何 Java 整合開發環境 (IDE) 相容。
### Q：如何取得 Microsoft Project 檔案中的任務 ID？
您可以檢查專案檔案或使用 Aspose.Tasks API 以程式設計方式擷取任務 ID。
### Q：Aspose.Tasks 適合處理大型專案嗎？
絕對地。 Aspose.Tasks 旨在有效地處理不同規模的專案。
### Q：在哪裡可以找到更多文件？
參觀[文件](https://reference.aspose.com/tasks/java/)以獲得綜合資源。
### Q：我可以在購買前試用 Aspose.Tasks for Java 嗎？
是的，您可以探索[免費試用](https://releases.aspose.com/)來評估其能力。