---
date: 2025-12-18
description: Tìm hiểu cách tạo view trong Aspose.Tasks cho Java, bao gồm cách lưu
  view dự án và thiết lập các thuộc tính view. Nâng cao hiệu quả quản lý dự án với
  các view tùy chỉnh MS Project được thiết kế riêng.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Cách tạo View - Các chế độ xem tùy chỉnh của MS Project trong Aspose.Tasks'
url: /vi/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo View: Các View Tùy chỉnh trong MS Project bằng Aspose.Tasks

## Giới thiệu
Nếu bạn đang tìm **cách tạo chế độ xem** phù hợp với yêu cầu báo cáo độc lập của dự án, thì bạn đã đến đúng nơi. Trong quản lý dự án, tùy chỉnh các chế độ xem có thể cải thiện đáng kể độ rõ ràng và hiệu quả khi xử lý nhiệm vụ và nguồn lực. **Aspose.Tasks for Java** cung cấp cho bạn một API phong phú để **chế độ xem tùy chỉnh java**‑style, cho phép bạn điều chỉnh chế độ xem của MS Project một cách chính xác theo nhu cầu. Trong hướng dẫn này, chúng tôi sẽ thực hiện quy trình từng bước từ công việc thiết lập dự án đến lưu trữ xem dự án.

## Trả lời nhanh
- **Mục đích chính là gì?** Tạo và lưu trữ một chế độ xem MS Project tùy chỉnh bằng Aspose.Tasks for Java.
- **Lớp nào tạo chế độ xem?** `GanttChartView` (hoặc các loại chế độ xem khác).
- **Làm sao để xem hiện thị trong menu?** Đặt `view.setShowInMenu(true)`.
- **Làm sao để lưu cùng xem dự án?** Sử dụng `MPPSaveOptions` với `setWriteViewData(true)`.
- **Có cần giấy phép không?** Có, cần một giấy phép Aspose.Tasks hợp lệ để sử dụng trong môi trường sản xuất.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:

### Môi trường phát triển Java
Đảm bảo Java đã được cài đặt trên hệ thống của bạn.

### Aspose.Tasks cho Java
Tải xuống và cài đặt Aspose.Tasks cho Java từ [tại đây](https://releases.aspose.com/tasks/java/).

## Nhập gói
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

## Bước 1: Thiết lập Dự án
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## Bước 2: Tạo Khung nhìn
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## Bước 3: Tùy chỉnh Thuộc tính Khung nhìn *(thiết lập thuộc tính khung nhìn)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### Cách hiển thị Menu Khung nhìn
Lệnh `view.setShowInMenu(true)` đảm bảo view mới tạo sẽ xuất hiện trong **view menu** của MS Project, giúp người dùng cuối truy cập nhanh chóng.

## Bước 4: Điều chỉnh Cài đặt Khung nhìn
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## Bước 5: Thêm Khung nhìn vào Dự án *(thêm khung nhìn tùy chỉnh bằng Java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## Bước 6: Lưu dự án *(lưu chế độ xem dự án)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### Tại sao việc Lưu Khung nhìn Dự án lại quan trọng
Thiết lập `options.setWriteViewData(true)` thông báo cho Aspose.Tasks **lưu thông tin view dự án** vào file MPP, vì vậy view tùy chỉnh sẽ được giữ lại qua các phiên làm việc.

## Bước 7: Kiểm tra Thuộc tính Khung nhìn
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## Các trường hợp sử dụng phổ biến
- **Báo cáo của các bên liên quan:** Tạo một chế độ xem chỉ hiển thị các cấp độ quan trọng và các nhiệm vụ quan trọng.
- **Phân bổ nguồn lực:** Xây dựng một chế độ xem danh sách nguồn lực cùng với các nhiệm vụ được giao để kiểm tra năng lượng nhanh chóng.
- **Tài liệu sẵn sàng in:** Điều chỉnh trang cài đặt (như trong Bước 4) để tạo các bản sao dự án có thể được sử dụng.

## Mẹo khắc phục sự cố
- **Xem không xuất hiện trong Menu:** Kiểm tra lại công việc gọi `view.setShowInMenu(true)` trước khi lưu.
- **Thiếu cột trong bản in:** Đảm bảo `setFirstColumnsCount` khớp với số cột bạn cần và bật `setPrintFirstColumnsCountOnAllPages(true)`.
- **Ngoại lệ giấy phép:** Nếu gặp lỗi giấy phép, hãy xác nhận rằng hợp lệ giấy phép Aspose.Tasks đã được tải trước khi tạo đối tượng `Project`.

## Câu hỏi thường gặp
### Q1: Tôi có thể tùy chỉnh các dạng hiển thị ngoài biểu đồ Gantt không?

A: Có, Aspose.Tasks for Java cung cấp tính linh hoạt để tùy chỉnh nhiều loại dạng hiển thị khác nhau ngoài biểu đồ Gantt, bao gồm bảng và đồ thị.

### Q2: Aspose.Tasks for Java có phù hợp với các dự án quy mô lớn không?

A: Chắc chắn rồi. Thư viện được thiết kế để xử lý các dự án ở mọi quy mô, cung cấp hiệu suất mạnh mẽ và quản lý bộ nhớ hiệu quả.

### Q3: Aspose.Tasks for Java có hỗ trợ xuất các dạng hiển thị sang các định dạng khác nhau không?

A: Có, bạn có thể xuất các dạng hiển thị sang PDF, XLSX, HTML và các định dạng khác, đảm bảo chia sẻ liền mạch trên các nền tảng.

### Q4: Tôi có thể tự động hóa việc tạo các dạng hiển thị tùy chỉnh bằng Aspose.Tasks for Java không?

A: Chắc chắn rồi. API cho phép tự động hóa hoàn toàn, cho phép bạn tạo và quản lý các dạng hiển thị tùy chỉnh theo chương trình.

### Q5: Có diễn đàn cộng đồng nào để hỗ trợ Aspose.Tasks for Java không?

A: Vâng, bạn có thể tìm kiếm sự trợ giúp và tương tác với những người dùng khác trong diễn đàn [Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được giải đáp các thắc mắc và thảo luận liên quan đến Java.

---

**Cập nhật lần cuối:** 18/12/2025
**Đã kiểm thử với:** Aspose.Tasks for Java 24.12
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}