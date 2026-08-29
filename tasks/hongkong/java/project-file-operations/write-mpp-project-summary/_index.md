---
date: 2026-03-29
description: 學習如何在 MPP 專案中使用 Aspose.Tasks for Java 設定關鍵字與建立日期。一步步指南，附程式碼範例。
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 在 MPP 專案摘要中設定關鍵字
url: /zh-hant/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 MPP 專案摘要中設定關鍵字與 Aspose.Tasks

## 介紹
在本教學中，您將學習**關鍵字**以及其他摘要資訊的設定方式，使用 Aspose.Tasks for Java 針對 MPP 專案檔。無論您需要嵌入作者資訊、版本號碼，或是自訂的建立日期，本指南都會一步步帶您完成，並提供可直接執行的程式碼範例。完成後，您將能設定關鍵字、設定 Java 建立日期，並從檔案中讀回這些資料。

## 快速解答
- **使用的函式庫是什麼？** Aspose.Tasks for Java  
- **主要目的？** 在 MPP 檔中設定關鍵字、作者資訊與建立日期  
- **程式碼步驟有多少？** 三個簡單的程式碼區塊（初始化、儲存、讀取）  
- **需要授權嗎？** 開發時可使用免費試用版；正式上線需購買商業授權  
- **支援的 Java 版本？** Java 8 及以上  

## 什麼是 MPP 檔中的「設定關鍵字」？
關鍵字是儲存在 Microsoft Project (MPP) 檔案內的中繼資料欄位。它們可協助對專案進行分類、快速搜尋，並為後續工具提供情境資訊。Aspose.Tasks 透過 `Prj.KEYWORDS` 屬性，讓您能以程式方式輕鬆寫入或更新此值。

## 為何使用 Aspose.Tasks for Java 來設定關鍵字與建立日期？
* **完整的 .MPP 相容性** – 支援所有 Project 2007‑2023 版本。  
* **不需 COM 或 Office 安裝** – 純 Java，適合伺服器端環境。  
* **功能豐富的 API** – 除了關鍵字，您還能在一次呼叫中設定作者、版本、註解與日期。  
* **效能最佳化** – 即使是大型專案檔，也能快速讀寫。  

## 前置條件
1. **Java Development Kit (JDK)** – 已安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載最新的 JAR。  
3. **IDE** – IntelliJ IDEA、Eclipse、NetBeans，或您偏好的任何編輯器。  

## 匯入套件
首先，匯入您需要的類別。這些匯入讓您能存取 `Project` 物件、用於摘要欄位的 `Prj` 列舉，以及用於儲存的 `SaveFileFormat` 列舉。

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## 步驟 1：設定專案並定義摘要資訊
建立 `Project` 實例，然後使用 `set` 方法寫入所需的中繼資料。請注意我們如何使用 `Calendar` 物件 **設定關鍵字** 與 **設定 Java 建立日期**。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## 步驟 2：儲存專案摘要資訊
在填寫完欄位後，將變更寫入檔案。此處我們將專案儲存為 XML，以便輕鬆檢視，但您也可以儲存回 MPP 格式。

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## 步驟 3：讀取專案摘要資訊
為了驗證中繼資料是否正確寫入，重新載入檔案並讀取每個屬性。此步驟展示 **設定關鍵字** 的完整端對端運作。

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **`project.get(Prj.CREATION_DATE)` 發生 NullPointerException** | 在儲存前未設定 Calendar。 | 確保在 `save()` 之前呼叫 `project.set(Prj.CREATION_DATE, cal.getTime())`。 |
| **關鍵字未在 Microsoft Project UI 中顯示** | 檔案以 XML 格式儲存並直接在 Project 中開啟。 | 改為儲存為 MPP (`SaveFileFormat.MPP`) 或在 Project 中透過 *Import* 開啟 XML。 |
| **日期值因時區偏移** | Java `Date` 含有時區資訊。 | 若需 UTC 日期，請使用 `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))`。 |

## 常見問與答

**Q: 我可以將 Aspose.Tasks for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Tasks for Java 能無縫整合其他 Java 函式庫，以增強您的專案管理功能。

**Q: 是否提供 Aspose.Tasks for Java 的試用版？**  
A: 有，您可從 [here](https://releases.aspose.com/) 下載免費試用版。

**Q: Aspose.Tasks for Java 更新頻率為何？**  
A: Aspose.Tasks for Java 會定期更新，以確保與最新的 Java 版本及 Microsoft Project 檔案相容。

**Q: 我可以進一步自訂專案摘要資訊嗎？**  
A: 當然可以，Aspose.Tasks for Java 提供豐富的選項，讓您依需求自訂專案摘要資訊。

**Q: 我該從哪裡取得 Aspose.Tasks for Java 的支援？**  
A: 您可於 Aspose.Tasks 社群論壇取得支援，連結在 [here](https://forum.aspose.com/c/tasks/15)。

---

**最後更新：** 2026-03-29  
**測試環境：** Aspose.Tasks for Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}