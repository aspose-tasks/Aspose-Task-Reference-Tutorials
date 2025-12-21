---
date: 2025-12-21
description: Tìm hiểu cách lưu dự án dưới dạng mẫu, xuất MPP sang CSV và chuyển đổi
  MPP sang văn bản bằng Aspose.Tasks cho Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Lưu Dự Án dưới dạng Mẫu, CSV và Văn bản với Aspose.Tasks cho Java
url: /vi/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu Dự Án dưới dạng Mẫu, CSV và Văn Bản với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách lưu dự án dưới dạng mẫu** và cách xuất các tệp Microsoft Project (MPP) sang định dạng CSV và văn bản thuần bằng thư viện Aspose.Tasks cho Java. Dù bạn cần tạo một mẫu dự án có thể tái sử dụng, tạo báo cáo CSV cho phân tích, hay trích xuất văn bản đơn giản để tích hợp, các bước sau sẽ hướng dẫn bạn thực hiện nhanh chóng và hiệu quả.

## Câu trả lời nhanh
- **Có thể xuất MPP sang CSV không?** Có – sử dụng `project.save(..., SaveFileFormat.CSV)`.  
- **Cách xuất ra văn bản?** Lưu với `SaveFileFormat.TEXT`.  
- **“Lưu dự án dưới dạng mẫu” làm gì?** Nó tạo một tệp `.mpt` loại bỏ các giá trị thực tế và baseline, sẵn sàng để tái sử dụng.  
- **Có cần giấy phép không?** Có bản dùng thử; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Yêu cầu phiên bản Java nào?** Hỗ trợ Java 8+.

## “Lưu dự án dưới dạng mẫu” là gì?
Lưu dự án dưới dạng mẫu (`.mpt`) ghi lại cấu trúc, phân cấp nhiệm vụ và phân công nguồn lực trong khi loại bỏ ngày bắt đầu/kết thúc thực tế và dữ liệu baseline. Điều này làm cho mẫu trở nên lý tưởng để tái sử dụng bố cục dự án chuẩn cho nhiều dự án mới.

## Tại sao nên dùng Aspose.Tasks cho Java?
Aspose.Tasks cho phép bạn thao tác các tệp Microsoft Project mà không cần cài đặt Microsoft Project. Nó hỗ trợ **cách xuất MPP**, **cách xuất văn bản**, và **chuyển đổi MPP sang CSV**, tất cả từ mã Java thuần, rất phù hợp cho tự động hoá phía máy chủ, pipeline CI, hoặc tiện ích desktop.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã:

1. Cài đặt Java Development Kit (JDK) 8 trở lên.  
2. Thêm thư viện Aspose.Tasks cho Java vào dự án. Tải về tại [here](https://releases.aspose.com/tasks/java/).  
3. Có kiến thức cơ bản về cú pháp Java và cấu hình dự án Maven/Gradle.

## Nhập các gói
Đầu tiên, nhập các lớp cần thiết vào tệp nguồn Java của bạn:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Lưu dự án dưới dạng CSV (Xuất MPP sang CSV)
Xuất tệp MPP sang CSV hữu ích cho việc phân tích dữ liệu trong Excel hoặc công cụ BI.

### Bước 1: Tải dự án
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Bước 2: Lưu dưới dạng CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Lưu dự án dưới dạng Văn Bản (Cách xuất Văn Bản)
Nếu bạn cần một biểu diễn văn bản thuần của các nhiệm vụ, nguồn lực hoặc phân công, hãy lưu dự án dưới dạng tệp văn bản.

### Bước 1: Tải dự án
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Bước 2: Lưu dưới dạng Văn Bản
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Lưu dự án dưới dạng Mẫu (Tạo Mẫu Dự Án Java)
Tạo một mẫu có thể tái sử dụng sẽ loại bỏ ngày thực tế và baseline, để lại khung xương sạch sẽ cho các dự án mới.

### Bước 1: Tải dự án
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Bước 2: Đặt tùy chọn mẫu
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Bước 3: Lưu dưới dạng mẫu
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Các vấn đề thường gặp & Mẹo
- **File không tìm thấy:** Đảm bảo đường dẫn tới `YourProject.mpp` là đúng hoặc sử dụng đường dẫn tuyệt đối.  
- **Lỗi giấy phép:** Nếu không có giấy phép hợp lệ, thư viện sẽ chạy ở chế độ đánh giá và có thể thêm watermark. Áp dụng giấy phép sớm trong mã (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Dự án lớn:** Đối với các tệp MPP rất lớn, cân nhắc tăng kích thước heap JVM (`-Xmx2g`) để tránh `OutOfMemoryError`.

## Kết luận
Chúng ta đã tìm hiểu **cách lưu dự án dưới dạng mẫu**, cũng như **cách xuất MPP sang CSV** và **cách chuyển MPP sang văn bản** bằng Aspose.Tasks cho Java. Những khả năng này cho phép bạn tự động hoá việc xử lý dữ liệu dự án, tạo mẫu tái sử dụng, và tích hợp thông tin dự án vào các hệ thống khác — mà không cần cài đặt Microsoft Project.

## Câu hỏi thường gặp
### H: Aspose.Tasks cho Java có thể xử lý các tệp dự án phức tạp không?
Đ: Chắc chắn! Aspose.Tasks cho Java có thể xử lý các dự án với độ phức tạp đa dạng, cung cấp hỗ trợ toàn diện cho các định dạng tệp Microsoft Project.  
### H: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
Đ: Có, bạn có thể tải bản dùng thử miễn phí của Aspose.Tasks cho Java tại [here](https://releases.aspose.com/).  
### H: Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho Java ở đâu?
Đ: Bạn có thể truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận trợ giúp hoặc đặt câu hỏi liên quan đến Aspose.Tasks cho Java.  
### H: Có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?
Đ: Có, bạn có thể mua giấy phép tạm thời tại [here](https://purchase.aspose.com/temporary-license/), cho phép bạn đánh giá toàn bộ tiềm năng của thư viện.  
### H: Aspose.Tasks cho Java có tương thích với các hệ điều hành khác nhau không?
Đ: Có, Aspose.Tasks cho Java tương thích với nhiều hệ điều hành, bao gồm Windows, macOS và Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2025-12-21  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất)  
**Tác giả:** Aspose  

---