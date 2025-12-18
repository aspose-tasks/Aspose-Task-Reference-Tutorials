---
date: 2025-12-18
description: Tìm hiểu cách tạo view trong Aspose.Tasks cho Java, bao gồm cách lưu
  view dự án và thiết lập các thuộc tính view. Nâng cao hiệu quả quản lý dự án với
  các view tùy chỉnh MS Project được thiết kế riêng.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Cách tạo View: Các chế độ xem tùy chỉnh của MS Project trong Aspose.Tasks'
url: /vi/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo View: Các View Tùy Chỉnh trong MS Project bằng Aspose.Tasks

## Introduction
Nếu bạn đang tìm **cách tạo view** phù hợp với nhu cầu báo cáo độc đáo của dự án, bạn đã đến đúng nơi. Trong quản lý dự án, việc tùy chỉnh các view có thể cải thiện đáng kể độ rõ ràng và hiệu quả khi xử lý nhiệm vụ và nguồn lực. **Aspose.Tasks for Java** cung cấp cho bạn một API phong phú để **thêm custom view java**‑style, cho phép bạn điều chỉnh các view của MS Project chính xác theo nhu cầu. Trong hướng dẫn này, chúng tôi sẽ đi qua quy trình từng bước, từ việc thiết lập dự án đến lưu view dự án.

## Quick Answers
- **Mục đích chính là gì?** Tạo và lưu trữ một custom MS Project view bằng Aspose.Tasks for Java.  
- **Lớp nào tạo view?** `GanttChartView` (hoặc các loại view khác).  
- **Làm sao để view xuất hiện trong menu?** Đặt `view.setShowInMenu(true)`.  
- **Làm sao để lưu view cùng dự án?** Sử dụng `MPPSaveOptions` với `setWriteViewData(true)`.  
- **Có cần giấy phép không?** Có, cần một giấy phép Aspose.Tasks hợp lệ để sử dụng trong môi trường sản xuất.

## Prerequisites
Trước khi bắt đầu, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:

### Java Development Environment
Đảm bảo Java đã được cài đặt trên hệ thống của bạn.

### Aspose.Tasks for Java
Tải xuống và cài đặt Aspose.Tasks for Java từ [here](https://releases.aspose.com/tasks/java/).

## Import Packages
Đầu tiên, nhập các package cần thiết vào dự án Java của bạn:
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```

## Step 1: Set Up Project
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## Step 2: Create View
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## Step 3: Customize View Properties *(set view properties)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### How to Show View Menu
Lệnh `view.setShowInMenu(true)` đảm bảo view mới tạo sẽ xuất hiện trong **view menu** của MS Project, giúp người dùng cuối truy cập nhanh chóng.

## Step 4: Tune View Settings
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## Step 5: Add View to Project *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## Step 6: Save Project *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### Why Saving the Project View Matters
Thiết lập `options.setWriteViewData(true)` thông báo cho Aspose.Tasks **lưu thông tin view dự án** vào file MPP, vì vậy view tùy chỉnh sẽ được giữ lại qua các phiên làm việc.

## Step 7: Check View Properties
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## Common Use Cases
- **Stakeholder Reporting:** Tạo một view chỉ hiển thị các mốc quan trọng cấp cao và các nhiệm vụ quan trọng.  
- **Resource Allocation:** Xây dựng một view liệt kê nguồn lực cùng với các nhiệm vụ được giao để kiểm tra năng lực nhanh chóng.  
- **Print‑Ready Documents:** Điều chỉnh cài đặt trang (như trong Step 4) để tạo ra các bản sao dự án có thể in được.

## Troubleshooting Tips
- **View Not Appearing in Menu:** Kiểm tra lại việc gọi `view.setShowInMenu(true)` trước khi lưu.  
- **Missing Columns in Printout:** Đảm bảo `setFirstColumnsCount` khớp với số cột bạn cần và bật `setPrintFirstColumnsCountOnAllPages(true)`.  
- **License Exceptions:** Nếu gặp lỗi giấy phép, xác nhận rằng file giấy phép Aspose.Tasks hợp lệ đã được tải trước khi tạo đối tượng `Project`.

## Frequently Asked Questions
### Q1: Can I customize views beyond Gantt charts?
A: Yes, Aspose.Tasks for Java provides flexibility to customize various types of views beyond Gantt charts, including tables and graphs.

### Q2: Is Aspose.Tasks for Java suitable for large‑scale projects?
A: Absolutely. The library is engineered to handle projects of any size, offering robust performance and memory management.

### Q3: Does Aspose.Tasks for Java support exporting views to different formats?
A: Yes, you can export views to PDF, XLSX, HTML, and other formats, ensuring seamless sharing across platforms.

### Q4: Can I automate the creation of custom views using Aspose.Tasks for Java?
A: Certainly. The API enables full automation, allowing you to programmatically generate and manage custom views.

### Q5: Is there a community forum for Aspose.Tasks for Java support?
A: Yes, you can find assistance and engage with other users in the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for Java‑related queries and discussions.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}