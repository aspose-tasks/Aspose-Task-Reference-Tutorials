---
title: Đọc thuộc tính tiền tệ trong dự án Aspose.Tasks
linktitle: Đọc thuộc tính tiền tệ trong dự án Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách trích xuất thông tin tiền tệ từ các tệp MS Project bằng Aspose.Tasks cho Java. Hướng dẫn từng bước được cung cấp.
type: docs
weight: 10
url: /vi/java/currency-properties/read-properties/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng Aspose.Tasks cho Java để đọc các thuộc tính tiền tệ từ các tệp Microsoft Project. Aspose.Tasks là một API Java mạnh mẽ cho phép các nhà phát triển thao tác với các tài liệu Microsoft Project mà không yêu cầu cài đặt Microsoft Project. Bằng cách làm theo các bước được nêu bên dưới, bạn sẽ có thể trích xuất thông tin liên quan đến tiền tệ một cách dễ dàng.
## Điều kiện tiên quyết
Trước khi tiếp tục với hướng dẫn này, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Tasks for Java JAR: Tải xuống thư viện Aspose.Tasks for Java từ[đây](https://releases.aspose.com/tasks/java/) và đưa nó vào dự án Java của bạn.
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết vào lớp Java của bạn:
```java
import com.aspose.tasks.*;
```
## Bước 1: Thiết lập thư mục dự án của bạn
Trước tiên, hãy thiết lập thư mục dự án nơi chứa tệp Microsoft Project của bạn. Bạn có thể xác định đường dẫn thư mục này như sau:
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"` với đường dẫn thực tế đến thư mục dự án của bạn.
## Bước 2: Tạo phiên bản Project Reader
 Khởi tạo một`Project` đối tượng bằng cách cung cấp đường dẫn đến tệp Microsoft Project của bạn:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Đảm bảo thay thế`"project.mpp"` với tên tệp MS Project của bạn.
## Bước 3: Hiển thị thuộc tính tiền tệ
Truy xuất và hiển thị các thuộc tính tiền tệ từ tệp dự án:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Đoạn mã này lấy thông tin như mã tiền tệ, chữ số, ký hiệu và vị trí ký hiệu từ tệp MS Project và in chúng ra bảng điều khiển.
## Bước 4: Hoàn tất quy trình
Cuối cùng, in thông báo cho biết quá trình đã hoàn tất thành công:
```java
System.out.println("Process completed Successfully");
```
## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá cách đọc các thuộc tính tiền tệ từ các tệp Microsoft Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước đã nêu, bạn có thể dễ dàng trích xuất thông tin liên quan đến tiền tệ từ các tệp dự án của mình theo chương trình, cho phép tích hợp liền mạch vào các ứng dụng Java của bạn.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có tương thích với tất cả các phiên bản Microsoft Project không?
Trả lời: Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, bao gồm các tệp MPP được tạo bởi MS Project 2003-2021.
### Câu hỏi: Tôi có thể sửa đổi thuộc tính tiền tệ bằng Aspose.Tasks không?
Trả lời: Có, Aspose.Tasks cho phép bạn đọc và sửa đổi các thuộc tính tiền tệ trong tệp MS Project theo chương trình.
### Câu hỏi: Aspose.Tasks có phù hợp cho mục đích sử dụng thương mại không?
 Trả lời: Có, Aspose.Tasks là một thư viện thương mại được thiết kế để sử dụng chuyên nghiệp. Bạn có thể mua giấy phép[đây](https://purchase.aspose.com/buy).
### Câu hỏi: Aspose.Tasks có cung cấp bản dùng thử miễn phí không?
 Đáp: Có, bạn có thể dùng thử miễn phí Aspose.Tasks từ[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm kiếm trợ giúp hoặc hỗ trợ cho Aspose.Tasks ở đâu?
 Trả lời: Bạn có thể truy cập diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15) cho bất kỳ sự trợ giúp hoặc thắc mắc.