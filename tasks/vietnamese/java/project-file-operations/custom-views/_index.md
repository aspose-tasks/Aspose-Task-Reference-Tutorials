---
date: 2026-05-26
description: Tìm hiểu cách thêm chế độ xem vào dự án bằng Aspose.Tasks cho Java, lưu
  chế độ xem tùy chỉnh và thiết lập các thuộc tính chế độ xem để tạo báo cáo MS Project
  mạnh mẽ.
keywords:
- add view to project
- save custom view
- persist custom view
- create gantt chart view
- set view properties
linktitle: Chế Độ Xem Tùy Chỉnh trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to add view to project using Aspose.Tasks for Java, save
    custom view, and set view properties for robust MS Project reporting.
  headline: How to Add View to Project with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes – Aspose.Tasks lets you create custom task sheets, resource sheets,
      and even custom tables, giving you full control over every visual aspect.
    question: Can I customize views beyond Gantt charts?
  - answer: Absolutely. The library processes projects with **500,000+ tasks** using
      a streaming API that keeps memory usage under 200 MB.
    question: Is Aspose.Tasks for Java suitable for large‑scale projects?
  - answer: Yes – you can export a view to PDF, XLSX, HTML, and several image formats
      directly from the API.
    question: Does Aspose.Tasks for Java support exporting views to different formats?
  - answer: Certainly. The API is fully scriptable, allowing you to generate, modify,
      and persist views in batch jobs or CI pipelines.
    question: Can I automate the creation of custom views using Aspose.Tasks for Java?
  - answer: Yes, you can get help from other developers and Aspose staff in the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks for Java support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách Thêm Chế Độ Xem vào Dự Án với Aspose.Tasks
url: /vi/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm View vào Dự Án với Aspose.Tasks

## Giới thiệu
Nếu bạn đang tìm kiếm **cách thêm view vào dự án** để báo cáo của bạn khớp chính xác với nhu cầu của các bên liên quan, bạn đã đến đúng nơi. Tùy chỉnh các view trong MS Project cho phép bạn hiển thị dữ liệu quan trọng nhất, loại bỏ sự lộn xộn và tăng tốc quá trình ra quyết định. **Aspose.Tasks for Java** cung cấp một API mạnh mẽ, an toàn kiểu dữ liệu, cho phép bạn tạo, cấu hình và lưu trữ các view tùy chỉnh trực tiếp trong tệp MPP. Trong hướng dẫn này, chúng tôi sẽ đi qua từng bước — từ chuẩn bị môi trường đến lưu view — để bạn có thể cung cấp một giải pháp hoàn thiện, có thể tái sử dụng.

## Câu trả lời nhanh
- **Mục đích chính là gì?** Thêm view vào dự án và lưu nó trong tệp MPP bằng Aspose.Tasks for Java.  
- **Lớp nào tạo view?** `GanttChartView` (hoặc các loại view khác như `TaskSheetView`).  
- **Làm thế nào để view hiển thị trong menu?** Gọi `view.setShowInMenu(true)` trước khi lưu.  
- **Làm sao lưu view cùng dự án?** Sử dụng `MPPSaveOptions` với `setWriteViewData(true)`.  
- **Có cần giấy phép không?** Có – cần một giấy phép Aspose.Tasks hợp lệ cho các triển khai sản xuất.

## “Thêm view vào dự án” là gì?
*Thêm một view vào dự án* có nghĩa là tạo một biểu diễn trực quan mới (ví dụ: biểu đồ Gantt, bảng công việc) và nhúng định nghĩa của nó vào tệp MPP để Microsoft Project có thể hiển thị sau này. Thao tác này hoàn toàn được thực hiện bằng chương trình với Aspose.Tasks, loại bỏ các bước thủ công trong giao diện người dùng.

## Tại sao nên sử dụng các view tùy chỉnh?
Aspose.Tasks hỗ trợ **hơn 50 thuộc tính liên quan đến view** và có thể xử lý các dự án với **hàng trăm nghìn công việc** mà không cần tải toàn bộ tệp vào bộ nhớ. Bằng cách định nghĩa một view một lần và lưu trữ nó, bạn đảm bảo báo cáo nhất quán cho tất cả các thành viên trong nhóm và giảm rủi ro lỗi cấu hình thủ công.

## Yêu cầu trước
- **Java Development Kit** (JDK 8 trở lên) đã được cài đặt và cấu hình trên máy của bạn.  
- Thư viện **Aspose.Tasks for Java** – tải xuống từ [here](https://releases.aspose.com/tasks/java/).  
- Tệp **giấy phép Aspose.Tasks** hợp lệ cho việc sử dụng trong môi trường sản xuất (bản dùng thử miễn phí hoạt động cho mục đích đánh giá).

## Nhập các gói
Các lớp `GanttChartView`, `MPPSaveOptions` và các lớp liên quan nằm trong không gian tên `com.aspose.tasks`. Nhập chúng ở đầu tệp nguồn của bạn:

`GanttChartView` đại diện cho định nghĩa view biểu đồ Gantt.  
`MPPSaveOptions` điều khiển cách dự án được lưu, bao gồm dữ liệu view.  
`Project` là lớp chính đại diện cho tệp MS Project.  
`View` là lớp cơ sở cho tất cả các loại view.  

```text
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
```

## Bước 1: Thiết lập Dự án
Tạo một thể hiện `Project` mới hoặc tải một tệp hiện có. Đối tượng này chứa tất cả dữ liệu dự án, bao gồm công việc, nguồn lực và các view. `Prj` cung cấp các khóa hằng cho các thuộc tính dự án như tên dự án.

```text
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
```

## Bước 2: Tạo View
`GanttChartView` là biểu diễn của Aspose.Tasks cho biểu đồ Gantt cổ điển. Nó cho phép bạn kiểm soát các cột, kiểu thanh, thang thời gian và nhiều hơn nữa.

```text
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```
```

## Bước 3: Tùy chỉnh Thuộc tính View *(set view properties)*
Ở đây bạn có thể tinh chỉnh giao diện của view: đặt cột hiển thị đầu tiên, xác định màu thanh, và điều chỉnh độ chi tiết của thang thời gian. `setShowInMenu(boolean)` xác định view có xuất hiện trong menu của MS Project hay không. `setHighlightFilter(boolean)` cho biết bộ lọc có được làm nổi bật cho view hay không.

```text
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```
```

### Cách hiển thị menu View
Gọi `view.setShowInMenu(true)` đảm bảo view mới tạo xuất hiện trong menu **View** của MS Project, cung cấp cho người dùng cuối quyền truy cập ngay lập tức mà không cần cấu hình thêm.

## Bước 4: Điều chỉnh Cài đặt View
Các cài đặt nâng cao như bố cục trang, tùy chọn in và độ rộng cột được cấu hình trong bước này. Việc điều chỉnh đúng cách đảm bảo các báo cáo đã in khớp với view trên màn hình.

```text
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```
```

## Bước 5: Thêm View vào Dự án *(add custom view java)*
Sau khi cấu hình view, thêm nó vào bộ sưu tập `Views` của dự án. `getViews()` trả về bộ sưu tập các view trong dự án. Bước này thực sự **thêm view vào dự án** để nó trở thành một phần của cấu trúc nội bộ của tệp.

```text
```java
// Add the view to our project
project.getViews().add(view);
```
```

## Bước 6: Lưu Dự án *(save project view)*
Khi lưu dự án, bạn phải yêu cầu Aspose.Tasks ghi dữ liệu view. Lớp `MPPSaveOptions` điều khiển hành vi này. `setWriteViewData(boolean)` chỉ định bộ lưu phải nhúng định nghĩa view.

```text
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```
```

### Tại sao việc lưu View của Dự án lại quan trọng
Cài đặt `options.setWriteViewData(true)` yêu cầu Aspose.Tasks nhúng định nghĩa view tùy chỉnh vào tệp MPP. Nếu không có cờ này, view sẽ chỉ tồn tại trong bộ nhớ và biến mất sau khi tệp được đóng.

## Bước 7: Kiểm tra Thuộc tính View
Sau khi lưu, bạn có thể tải lại dự án và xác minh rằng view hiển thị đúng trong giao diện người dùng và tất cả các thuộc tính (cột, kiểu thanh, v.v.) được giữ nguyên.

```text
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```
```

## Các trường hợp sử dụng phổ biến
- **Báo cáo cho các bên liên quan:** Hiển thị chỉ các mốc quan trọng và các công việc trên đường đi quan trọng cho cấp quản lý cao.  
- **Phân bổ nguồn lực:** Hiển thị nguồn lực cạnh nhau với các công việc được giao để lập kế hoạch năng lực.  
- **Ảnh chụp sẵn sàng in:** Cấu hình kích thước trang, hướng và hiển thị cột để tạo PDF sạch sẽ cho việc xem xét ngoại tuyến.

## Mẹo khắc phục sự cố
- **View không xuất hiện trong menu:** Đảm bảo `view.setShowInMenu(true)` được gọi *trước* khi lưu và `MPPSaveOptions.setWriteViewData(true)` được bật.  
- **Cột thiếu trong bản in:** Kiểm tra `setFirstColumnsCount` khớp với số cột bạn đã định nghĩa và bật `setPrintFirstColumnsCountOnAllPages(true)`.  
- **Lỗi giấy phép:** Tải tệp giấy phép bằng `License license = new License(); license.setLicense("Aspose.Tasks.lic");` trước khi tạo bất kỳ đối tượng `Project` nào.

## Câu hỏi thường gặp

**Q: Tôi có thể tùy chỉnh view ngoài biểu đồ Gantt không?**  
A: Có – Aspose.Tasks cho phép bạn tạo các bảng công việc tùy chỉnh, bảng nguồn lực, và thậm chí các bảng tùy chỉnh, cung cấp cho bạn toàn quyền kiểm soát mọi khía cạnh trực quan.

**Q: Aspose.Tasks for Java có phù hợp cho các dự án quy mô lớn không?**  
A: Hoàn toàn. Thư viện xử lý các dự án với **hơn 500.000 công việc** bằng API streaming giữ mức sử dụng bộ nhớ dưới 200 MB.

**Q: Aspose.Tasks for Java có hỗ trợ xuất view sang các định dạng khác không?**  
A: Có – bạn có thể xuất một view sang PDF, XLSX, HTML và một số định dạng ảnh trực tiếp từ API.

**Q: Tôi có thể tự động tạo các view tùy chỉnh bằng Aspose.Tasks for Java không?**  
A: Chắc chắn. API hoàn toàn có thể script, cho phép bạn tạo, sửa đổi và lưu trữ các view trong các công việc batch hoặc pipeline CI.

**Q: Có diễn đàn cộng đồng nào hỗ trợ Aspose.Tasks cho Java không?**  
A: Có, bạn có thể nhận trợ giúp từ các nhà phát triển khác và nhân viên Aspose trong [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Cập nhật lần cuối:** 2026-05-26  
**Kiểm thử với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách Tạo Tệp MPP – Tạo & Lưu Dự án Trống ở Định dạng MPP với Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Đặt Thư mục Dữ liệu cho View Biểu đồ Gantt trong Aspose.Tasks](/tasks/java/project-configuration/configure-gantt-chart/)
- [Tải Tệp MPP Java - Quản lý Thuộc tính Dự án với Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}