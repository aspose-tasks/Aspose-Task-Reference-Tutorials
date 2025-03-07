---
title: Lưu dưới dạng PDF trong Aspose.Tasks
linktitle: Lưu dưới dạng PDF trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách chuyển đổi tệp dự án sang PDF bằng Aspose.Tasks cho Java. Các bước đơn giản để chuyển đổi hiệu quả.
weight: 17
url: /vi/java/project-file-operations/save-as-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu dưới dạng PDF trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình lưu dự án dưới dạng PDF bằng Aspose.Tasks cho Java. Với Aspose.Tasks, bạn có thể chuyển đổi các tệp dự án của mình sang định dạng PDF một cách hiệu quả, đảm bảo tính tương thích và dễ chia sẻ. Hãy đi sâu vào các bước:
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Tasks for Java Library: Tải xuống và cài đặt thư viện Aspose.Tasks. Bạn có thể tìm thấy liên kết tải xuống[đây](https://releases.aspose.com/tasks/java/).
3. Tệp dự án: Chuẩn bị sẵn tệp dự án (ví dụ: HomeMovePlan.mpp) mà bạn muốn chuyển đổi sang PDF.

## Gói nhập khẩu
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Bước 1: Đọc tệp dự án đầu vào
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Đảm bảo bạn thay thế`"Your Data Directory"` với đường dẫn đến thư mục dữ liệu chứa tệp dự án.
## Bước 2: Lưu dự án dưới dạng PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Đoạn mã này lưu dự án dưới dạng tệp PDF có tên "Project5.pdf".
## Bước 3: Điều chỉnh nội dung cho phù hợp với kích thước ô
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Tại đây, chúng tôi đặt các tùy chọn để lưu tệp PDF, bao gồm nội dung phù hợp, khoảng thời gian và định dạng trình bày.
## Bước 4: Ẩn huyền thoại
```java
o.setLegendOnEachPage(false);
```
Bước này ẩn chú thích trên mỗi trang của tệp PDF.
## Bước 5: Lưu dự án với các tùy chọn ứng dụng
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Cuối cùng, mã này lưu dự án với các tùy chọn được áp dụng vào tệp PDF.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.Tasks cho Java để lưu dự án dưới dạng PDF. Bằng cách làm theo các bước đơn giản này, bạn có thể chuyển đổi các tệp dự án của mình một cách hiệu quả để dễ dàng chia sẻ và phân phối.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có tương thích với tất cả các phiên bản Java không?
Trả lời: Có, Aspose.Tasks hỗ trợ các phiên bản Java bắt đầu từ JDK 6 trở lên.
### Hỏi: Tôi có thể tùy chỉnh giao diện của đầu ra PDF không?
Đ: Chắc chắn rồi! Aspose.Tasks cung cấp nhiều tùy chọn khác nhau để tùy chỉnh đầu ra PDF theo yêu cầu của bạn.
### Câu hỏi: Aspose.Tasks có hỗ trợ các định dạng tệp khác để chuyển đổi không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp, bao gồm MPP, XML, XLSX, v.v.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks không?
 Đáp: Có, bạn có thể dùng thử miễn phí Aspose.Tasks từ[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?
 Đáp: Để được hỗ trợ và giúp đỡ, bạn có thể truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
