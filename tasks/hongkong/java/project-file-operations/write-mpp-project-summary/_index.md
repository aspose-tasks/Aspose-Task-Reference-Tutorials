---
title: 在Aspose.Tasks中撰寫MPP專案摘要
linktitle: 在Aspose.Tasks中撰寫MPP專案摘要
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks 在 Java 中撰寫 MPP 專案摘要。輕鬆設定和檢索項目資訊。
weight: 27
url: /zh-hant/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在Aspose.Tasks中撰寫MPP專案摘要

## 介紹
在本教程中，我們將學習如何利用 Aspose.Tasks for Java 撰寫 MPP 專案摘要。 Aspose.Tasks 是一個功能強大的 Java 函式庫，用於處理 Microsoft Project 檔案。透過執行下面概述的步驟，您將能夠使用此程式庫設定和檢索有關項目的各種摘要資訊。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Tasks for Java：下載並安裝 Aspose.Tasks for Java 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).
3. 整合開發環境 (IDE)：選擇 Java 開發的首選 IDE，例如 IntelliJ IDEA、Eclipse 或 NetBeans。

## 導入包
首先，將必要的套件匯入到您的 Java 類別中：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## 第 1 步：設定項目並定義摘要訊息
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
//使用專案文件的路徑初始化新的 Project 對象
Project project = new Project(dataDir + "project.mpp");
//設定有關項目的摘要信息
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
//設定專案的建立日期
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
//為專案設定關鍵字
project.set(Prj.KEYWORDS, "MPP Aspose");
//設定項目的最後列印日期
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## 第 2 步：儲存項目摘要信息
```java
//以 MPP 格式儲存項目
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
//顯示成功訊息
System.out.println("Process completed Successfully");
```
## 第 3 步：閱讀項目摘要信息
```java
//閱讀項目摘要信息
project = new Project(dataDir + "MppAspose.xml");
//項目的印刷作者
System.out.println("Author: " + project.get(Prj.AUTHOR));
//印刷項目的最後一位作者
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
//列印項目的修訂號
System.out.println("Revision: " + project.get(Prj.REVISION));
//列印項目的關鍵字
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
//印刷項目的評論
System.out.println("Comments: " + project.get(Prj.COMMENTS));
//列印專案的建立日期
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
//列印項目的關鍵字（再次）
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
//列印項目的最後列印日期
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## 結論
在本教學中，我們介紹如何使用 Aspose.Tasks for Java 撰寫 MPP 專案摘要。透過執行這些步驟，您可以有效地設定和檢索有關專案文件的各種摘要資訊。 Aspose.Tasks 簡化了在 Java 應用程式中使用 Microsoft Project 檔案的過程，提供了強大的功能和易用性。
## 常見問題解答
### Q：我可以將 Aspose.Tasks for Java 與其他 Java 函式庫一起使用嗎？
答：是的，Aspose.Tasks for Java 可以與其他 Java 函式庫無縫集成，以增強您的專案管理能力。
### Q：Aspose.Tasks for Java 有試用版嗎？
答：是的，您可以從以下位置下載免費試用版：[這裡](https://releases.aspose.com/).
### Q：Aspose.Tasks for Java 的更新頻率是多少？
答：Aspose.Tasks for Java 會定期更新，以確保與最新版本的 Java 和 Microsoft Project 檔案相容。
### Q：我可以進一步自訂專案摘要資訊嗎？
答：當然，Aspose.Tasks for Java 提供了廣泛的選項，可根據您的特定要求自訂專案摘要資訊。
### Q：在哪裡可以獲得 Aspose.Tasks for Java 的支援？
答：您可以從 Aspose.Tasks 社群論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
