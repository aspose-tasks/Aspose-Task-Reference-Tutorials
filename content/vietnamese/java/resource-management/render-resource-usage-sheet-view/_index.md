---
title: Kết xuất mức sử dụng tài nguyên và chế độ xem trang tính trong Aspose.Tasks
linktitle: Kết xuất mức sử dụng tài nguyên và chế độ xem trang tính trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách hiển thị các dạng xem Trang tính và Sử dụng Tài nguyên Dự án MS trong Aspose.Tasks cho Java. Làm theo hướng dẫn từng bước của chúng tôi để tạo báo cáo PDF chi tiết một cách dễ dàng.
type: docs
weight: 16
url: /vi/java/resource-management/render-resource-usage-sheet-view/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng Aspose.Tasks cho Java để hiển thị các dạng xem Trang tính và Sử dụng Tài nguyên Dự án MS. Aspose.Tasks là một thư viện Java mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project mà không cần cài đặt Microsoft Project.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo rằng bạn đã cài đặt Bộ công cụ phát triển Java trên hệ thống của mình. Bạn có thể tải xuống và cài đặt phiên bản JDK mới nhất từ trang web của Oracle.
2.  Aspose.Tasks for Java: Tải xuống và cài đặt thư viện Aspose.Tasks for Java từ[trang tải xuống](https://releases.aspose.com/tasks/java/).

## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết vào dự án Java của mình:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Bước 1: Đọc dự án nguồn
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Data Directory";
// Đọc nguồn Dự án
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
Trong bước này, chúng tôi chỉ định đường dẫn đến tệp Dự án nguồn (`ResourceUsageView.mpp` ) và sử dụng`Project` lớp đọc nó.
## Bước 2: Xác định SaveOptions với cài đặt TimeScale bắt buộc
```java
// Xác định SaveOptions với cài đặt TimeScale được yêu cầu là Ngày
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Ở đây, chúng tôi xác định`SaveOptions` với yêu cầu`TimeScale` cài đặt. Trong ví dụ này, chúng tôi đặt`TimeScale` đến Ngày.
## Bước 3: Đặt định dạng bản trình bày thành ResourceUsage
```java
// Đặt định dạng Bản trình bày thành ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Chúng tôi đặt định dạng trình bày thành`ResourceUsage`, cho biết rằng chúng tôi muốn hiển thị chế độ xem Sử dụng tài nguyên.
## Bước 4: Lưu dự án
```java
// Lưu dự án
project.save(dataDir + days, options);
```
Cuối cùng, chúng ta lưu Project với các tùy chọn đã chỉ định. Trong ví dụ này, tệp đầu ra sẽ được lưu dưới dạng`result_days.pdf`.
## Bước 5: Hiển thị chế độ xem cho các cài đặt thang thời gian khác
Lặp lại các bước từ 2 đến 4 để hiển thị các chế độ xem với các cài đặt TimeScale khác nhau (ThirdsOfMonths và Tháng).
```java
// Đặt cài đặt Thang thời gian thành ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Lưu dự án
project.save(thirds, options);
// Đặt cài đặt Thang thời gian thành Tháng
options.setTimescale(Timescale.Months);
// Lưu dự án
project.save(dataDir + months, options);
```
 Đảm bảo thay đổi`Timescale` cài đặt phù hợp cho từng chế độ xem.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá cách sử dụng Aspose.Tasks cho Java để hiển thị các dạng xem Trang tính và Sử dụng Tài nguyên Dự án MS. Bằng cách làm theo các bước được nêu ở trên, bạn có thể tạo các chế độ xem này ở định dạng PDF một cách hiệu quả, tạo điều kiện trực quan hóa và phân tích dữ liệu dự án của bạn tốt hơn.
## Câu hỏi thường gặp
### Aspose.Tasks có thể hiển thị các chế độ xem khác ngoài Sử dụng tài nguyên và Trang tính không?
Aspose.Tasks hỗ trợ hiển thị nhiều chế độ xem khác nhau như Biểu đồ Gantt, Cách sử dụng tác vụ và chế độ xem Lịch, cùng với các chế độ xem khác.
### Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?
Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.
### Tôi có thể tùy chỉnh giao diện của chế độ xem được hiển thị bằng Aspose.Tasks không?
Tuyệt đối! Aspose.Tasks cung cấp các tùy chọn mở rộng để tùy chỉnh giao diện và bố cục của các chế độ xem được hiển thị cho phù hợp với yêu cầu cụ thể của bạn.
### Aspose.Tasks có yêu cầu cài đặt Microsoft Project trên hệ thống không?
Không, Aspose.Tasks là một thư viện độc lập và không yêu cầu cài đặt Microsoft Project để hoạt động.
### Người dùng Aspose.Tasks có được hỗ trợ kỹ thuật không?
 Có, người dùng Aspose.Tasks có thể tận dụng hỗ trợ kỹ thuật thông qua[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).