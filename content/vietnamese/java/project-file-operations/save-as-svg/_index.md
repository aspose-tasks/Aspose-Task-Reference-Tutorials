---
title: Chuyển đổi MS Project sang SVG trong Java
linktitle: Lưu dưới dạng SVG trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách lưu tệp Microsoft Project dưới dạng SVG trong Java bằng thư viện Aspose.Tasks. Hướng dẫn từng bước với các ví dụ về mã.
type: docs
weight: 18
url: /vi/java/project-file-operations/save-as-svg/
---
## Giới thiệu
Aspose.Tasks cho Java là một thư viện mạnh mẽ để làm việc với các tệp quản lý dự án, cho phép các nhà phát triển thao tác với dữ liệu dự án, thực hiện các hoạt động khác nhau và tạo báo cáo một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ khám phá cách lưu dự án dưới dạng SVG bằng Aspose.Tasks cho Java. SVG (Đồ họa vectơ có thể mở rộng) là định dạng được sử dụng rộng rãi để hiển thị đồ họa vector trên web, cung cấp khả năng mở rộng và hiển thị chất lượng cao.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
### Môi trường phát triển Java
Đảm bảo bạn đã cài đặt Bộ công cụ phát triển Java (JDK) trên hệ thống của mình. Bạn có thể tải xuống và cài đặt JDK từ trang web của Oracle.
### Aspose.Tasks cho Thư viện Java
 Tải xuống và cài đặt thư viện Aspose.Tasks cho Java từ trang web. Bạn có thể tìm thấy liên kết tải xuống trong tài liệu được cung cấp[đây](https://releases.aspose.com/tasks/java/).

## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết trong chương trình Java của mình để hoạt động với các chức năng Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Bây giờ hãy chia ví dụ được cung cấp thành nhiều bước:
## Bước 2: Xác định thư mục dữ liệu
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"`với đường dẫn đến thư mục chứa tệp dự án của bạn.
## Bước 3: Tải tệp dự án
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Bước này tải tệp dự án có tên "HomeMovePlan.mpp" từ thư mục dữ liệu đã chỉ định.
## Bước 4: Lưu dưới dạng SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Bước này lưu dự án đã tải dưới dạng SVG với tên "project5.svg" trong thư mục dữ liệu đã chỉ định.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách lưu dự án dưới dạng SVG bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước được cung cấp, bạn có thể chuyển đổi các tệp dự án sang định dạng SVG một cách hiệu quả, cho phép tích hợp liền mạch với các ứng dụng hoặc công cụ trực quan dựa trên web.
## Câu hỏi thường gặp
### Aspose.Tasks cho Java có tương thích với tất cả các phiên bản của tệp Microsoft Project không?
Có, Aspose.Tasks for Java hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.
### Tôi có thể tùy chỉnh giao diện của đầu ra SVG không?
Có, bạn có thể tùy chỉnh giao diện của đầu ra SVG bằng cách điều chỉnh các tham số như phông chữ, màu sắc và cấu hình bố cục.
### Aspose.Tasks cho Java có yêu cầu giấy phép sử dụng thương mại không?
 Có, cần có giấy phép hợp lệ để sử dụng Aspose.Tasks cho Java với mục đích thương mại. Bạn có thể lấy giấy phép từ trang web[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể dùng thử Aspose.Tasks cho Java trước khi mua không?
 Có, bạn có thể yêu cầu dùng thử miễn phí Aspose.Tasks cho Java từ trang web[đây](https://purchase.aspose.com/buy) để đánh giá các tính năng và khả năng của nó.
### Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?
 Bạn có thể nhận hỗ trợ cho Aspose.Tasks for Java bằng cách truy cập diễn đàn[đây](https://forum.aspose.com/c/tasks/15), nơi bạn có thể đặt câu hỏi và tương tác với cộng đồng.