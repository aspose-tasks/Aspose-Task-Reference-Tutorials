---
date: 2025-12-23
description: 學習如何使用 Aspose.Tasks for Java 建立 MPP 摘要並更新專案作者。輕鬆設定與取得專案資訊。
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 建立 MPP 摘要並更新專案作者
url: /zh-hant/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中編寫 MPP 專案摘要

## 介紹
在本教學中，您將使用 Aspose.Tasks for Java 程式庫 **建立 MPP 摘要** 資訊於 Microsoft Project 檔案，並學習如何 **更新專案作者** 資料。無論您是開發專案管理工具或是自動化報表，透過程式碼控制摘要屬性都能節省時間，並確保各專案的一致性。

## 快速解答
- **「建立 MPP 摘要」是什麼意思？** 這表示設定 Microsoft Project 中「專案摘要資訊」對話方塊所顯示的高階專案屬性（作者、版本、關鍵字等）。  
- **哪個程式庫負責此功能？** Aspose.Tasks for Java 提供流暢的 API 以讀寫這些屬性。  
- **我需要授權嗎？** 有免費試用版可供使用，但正式環境必須購買商業授權。  
- **我可以在檔案儲存後再變更作者嗎？** 可以——只要呼叫 `project.set(Prj.AUTHOR, "New Author")` 並重新儲存檔案，即可 **更新專案作者**。  
- **支援哪些檔案格式？** 完全支援 MPP 與 XML（SaveFileFormat.Xml）。

## 什麼是「建立 MPP 摘要」？
建立 MPP 摘要即是填寫專案的中繼資料——作者、版本號、關鍵字、備註、建立日期與列印日期。這些中繼資料儲存在「專案摘要資訊」記錄中，並會顯示於 Microsoft Project 的 **檔案 → 資訊** 頁面。

## 為什麼要更新專案作者？
保持 **專案作者** 資訊的正確性對於稽核、協作與報告至關重要。當多位團隊成員共同參與時，您可能需要 **更新專案作者** 以反映最新變更或正確歸屬工作。

## 前置條件
1. 已在電腦上安裝 Java Development Kit (JDK)。  
2. Aspose.Tasks for Java – 從 [此處](https://releases.aspose.com/tasks/java/) 下載。  
3. 使用 IntelliJ IDEA、Eclipse 或 NetBeans 等開發環境。

## 匯入套件
首先，將必要的套件匯入您的 Java 類別中：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## 步驟 1：設定專案並定義摘要資訊
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
上述程式碼中，我們 **建立 MPP 摘要** 欄位，如作者、版本與關鍵字。您亦可稍後透過呼叫 `project.set(Prj.AUTHOR, "New Name")` 來 **更新專案作者**。

## 步驟 2：儲存專案摘要資訊
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
儲存專案會將剛才定義的所有摘要資料寫入檔案。

## 步驟 3：讀取專案摘要資訊
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
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
此程式碼片段示範如何 **讀回** 摘要資訊，以確認 **建立 MPP 摘要** 的操作已成功。

## 常見問題與解決方案
- **讀取後出現 Null 值：** 確認專案已成功儲存後再重新載入，並檢查檔案路徑與權限。  
- **日期格式差異：** `project.get(Prj.CREATION_DATE)` 會回傳 `java.util.Date`。若需自訂顯示格式，可使用 `SimpleDateFormat`。  
- **未設定授權：** 若未提供有效授權，Aspose.Tasks 會以評估模式執行，可能會嵌入浮水印。請在程式碼開頭盡早註冊授權。

## 常見問答
**Q: 我可以將 Aspose.Tasks for Java 與其他 Java 程式庫一起使用嗎？**  
A: 可以，Aspose.Tasks for Java 能夠無縫整合其他 Java 程式庫，以增強您的專案管理功能。

**Q: 是否提供 Aspose.Tasks for Java 的試用版？**  
A: 有，您可從 [此處](https://releases.aspose.com/) 下載免費試用版。

**Q: Aspose.Tasks for Java 更新頻率為何？**  
A: Aspose.Tasks for Java 會定期更新，以確保與最新的 Java 版本及 Microsoft Project 檔案相容。

**Q: 我可以進一步自訂專案摘要資訊嗎？**  
A: 當然可以，Aspose.Tasks for Java 提供豐富的選項，讓您依需求自訂專案摘要資訊。

**Q: 我該從哪裡取得 Aspose.Tasks for Java 的支援？**  
A: 您可前往 Aspose.Tasks 社群論壇取得協助，連結在 [此處](https://forum.aspose.com/c/tasks/15)。

## 結論
在本教學中，我們示範了如何 **建立 MPP 摘要** 資料、**更新專案作者**，以及使用 Aspose.Tasks for Java 驗證這些變更。透過自動化這些步驟，您即可完整掌控專案中繼資料，讓應用程式更具韌性，專案報告也更為精確。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}