---
title: Giảm khoảng cách giữa danh sách nhiệm vụ và chân trang trong Aspose.Tasks
linktitle: Giảm khoảng cách giữa danh sách nhiệm vụ và chân trang trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách giảm khoảng cách giữa danh sách nhiệm vụ và chân trang của MS Project bằng Aspose.Tasks cho Java. Tối ưu hóa bố cục tài liệu dự án một cách dễ dàng.
type: docs
weight: 10
url: /vi/java/project-file-operations/reduce-gap-tasks-list-footer/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc giảm khoảng cách giữa danh sách tác vụ và chân trang trong tệp Microsoft Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn sẽ có thể tối ưu hóa bố cục tài liệu dự án của mình một cách dễ dàng.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Tasks for Java Library: Tải xuống và đưa thư viện Aspose.Tasks for Java vào dự án của bạn. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).

## Gói nhập khẩu
Trước khi đi sâu vào phần mã hóa, hãy nhập các gói cần thiết:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Bước 1: Cung cấp đường dẫn đến thư mục dữ liệu của bạn
```java
String dataDir = "Your Data Directory";
```
 Đảm bảo thay thế`"Your Data Directory"` với đường dẫn đến thư mục dữ liệu thực tế nơi tệp Microsoft Project của bạn (`HomeMovePlan.mpp` trong ví dụ này) được định vị.
## Bước 2: Đọc tệp MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Dòng mã này đọc tệp Microsoft Project có tên`HomeMovePlan.mpp`.
## Bước 3: Đặt tùy chọn ImageSave
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Định cấu hình các tùy chọn lưu ảnh, cài đặt`ReduceFooterGap` ĐẾN`true` để giảm khoảng cách giữa danh sách nhiệm vụ và chân trang.
## Bước 4: Lưu dưới dạng hình ảnh
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Lưu dự án dưới dạng hình ảnh với các tùy chọn đã định cấu hình.
## Bước 5: Đặt PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Xác định các tùy chọn lưu PDF, đảm bảo thiết lập`ReduceFooterGap` ĐẾN`true`.
## Bước 6: Lưu dưới dạng PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Lưu dự án dưới dạng PDF với các tùy chọn đã định cấu hình.
## Bước 7: Đặt HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // đặt thành đúng
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Chỉ định các tùy chọn, cài đặt lưu HTML`ReduceFooterGap` ĐẾN`true`.
## Bước 8: Lưu dưới dạng HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Lưu dự án dưới dạng tệp HTML với các tùy chọn đã định cấu hình.

## Phần kết luận
Tóm lại, việc giảm khoảng cách giữa danh sách tác vụ và chân trang trong tệp Microsoft Project là một quá trình đơn giản với Aspose.Tasks dành cho Java. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tối ưu hóa bố cục tài liệu dự án của mình một cách hiệu quả.

## Câu hỏi thường gặp

### Câu hỏi: Aspose.Tasks có tương thích với tất cả các phiên bản Microsoft Project không?

Trả lời: Aspose.Tasks hỗ trợ các định dạng Microsoft Project 2003-2019, đảm bảo khả năng tương thích trên nhiều phiên bản khác nhau.

### Câu hỏi: Tôi có thể tùy chỉnh hình thức của chân trang trong tài liệu dự án của mình không?

Trả lời: Có, Aspose.Tasks cung cấp các tùy chọn mở rộng để tùy chỉnh giao diện của chân trang, bao gồm giảm khoảng cách và điều chỉnh vị trí nội dung.

### Câu hỏi: Aspose.Tasks có hỗ trợ lưu dự án ở các định dạng khác ngoài PNG, PDF và HTML không?

Trả lời: Có, Aspose.Tasks hỗ trợ nhiều định dạng, bao gồm XLSX, XML và MPP, cùng nhiều định dạng khác.

### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks không?

 Đáp: Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Tasks từ[đây](https://releases.aspose.com/).

### Câu hỏi: Tôi có thể nhận hỗ trợ ở đâu nếu gặp bất kỳ sự cố nào khi sử dụng Aspose.Tasks?

 Trả lời: Bạn có thể nhận trợ giúp từ diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).