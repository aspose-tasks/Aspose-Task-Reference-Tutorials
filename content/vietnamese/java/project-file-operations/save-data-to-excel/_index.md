---
title: Lưu dữ liệu dự án MS vào Excel trong Aspose.Tasks
linktitle: Lưu dữ liệu vào Excel trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách lưu dữ liệu Microsoft Project vào tệp Excel bằng Aspose.Tasks cho Java. Tích hợp dễ dàng cho các nhà phát triển Java.
type: docs
weight: 19
url: /vi/java/project-file-operations/save-data-to-excel/
---
## Giới thiệu
Aspose.Tasks for Java là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project theo chương trình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình lưu dữ liệu từ tệp Dự án sang tệp Excel theo từng bước.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo rằng bạn đã cài đặt Java trên hệ thống của mình. Bạn có thể tải xuống và cài đặt phiên bản JDK mới nhất từ trang web của Oracle.
2.  Aspose.Tasks cho Thư viện Java: Tải xuống thư viện Aspose.Tasks cho Java từ[Liên kết tải xuống](https://releases.aspose.com/tasks/java/) và đưa nó vào dự án Java của bạn.

## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết trong mã Java của mình để hoạt động với Aspose.Tasks.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Hãy chia ví dụ được cung cấp thành nhiều bước:
## Bước 1: Xác định đường dẫn thư mục dữ liệu
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"`với đường dẫn đến thư mục dữ liệu của bạn nơi chứa tệp Dự án.
## Bước 2: Tải tệp dự án
```java
Project project = new Project(dataDir + "project5.mpp");
```
Dòng mã này tải tệp Dự án có tên "project5.mpp" từ thư mục dữ liệu đã chỉ định.
## Bước 3: Lưu dự án dưới dạng XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 Ở đây,`save` phương thức được sử dụng để lưu tệp Dự án đã tải dưới dạng tệp Excel có tên "project1.xlsx" trong cùng thư mục dữ liệu. Chúng tôi chỉ định`SaveFileFormat.Xlsx` tham số để lưu nó ở định dạng XLSX.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách lưu dữ liệu từ tệp Microsoft Project vào tệp Excel bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước được cung cấp, bạn có thể tích hợp liền mạch chức năng này vào các ứng dụng Java của mình.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks cho Java để thao tác dữ liệu dự án theo chương trình không?
Có, Aspose.Tasks dành cho Java cung cấp các tính năng mở rộng để thao tác dữ liệu dự án, bao gồm đọc, ghi và sửa đổi tệp dự án.
### Có bản dùng thử miễn phí dành cho Aspose.Tasks cho Java không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Tasks cho Java từ[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu về Aspose.Tasks cho Java ở đâu?
Bạn có thể tìm tài liệu về Aspose.Tasks for Java[đây](https://reference.aspose.com/tasks/java/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho bất kỳ vấn đề hoặc truy vấn nào liên quan đến Aspose.Tasks cho Java?
 Bạn có thể nhận được hỗ trợ bằng cách truy cập diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?
 Có, bạn có thể mua giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).