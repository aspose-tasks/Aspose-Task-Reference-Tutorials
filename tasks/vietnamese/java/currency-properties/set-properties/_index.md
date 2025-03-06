---
title: Đặt thuộc tính tiền tệ trong dự án Aspose.Tasks
linktitle: Đặt thuộc tính tiền tệ trong dự án Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách đặt thuộc tính tiền tệ trong dự án Aspose.Tasks bằng Java. Thao tác dễ dàng với các tệp Microsoft Project.
weight: 11
url: /vi/java/currency-properties/set-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt thuộc tính tiền tệ trong dự án Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách đặt thuộc tính tiền tệ trong các dự án Aspose.Tasks bằng Java. Aspose.Tasks là một thư viện Java mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project theo chương trình.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Tasks for Java Library: Tải xuống và cài đặt thư viện Aspose.Tasks for Java từ[Liên kết tải xuống](https://releases.aspose.com/tasks/java/).
3. Môi trường phát triển tích hợp (IDE): Chọn IDE ưa thích của bạn như Eclipse hoặc IntelliJ IDEA.
## Gói nhập khẩu
Trước tiên, hãy nhập các gói cần thiết để làm việc với Aspose.Tasks trong Java.
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## Bước 1: Đặt thư mục dữ liệu
Đặt thư mục dữ liệu nơi chứa các tệp dự án của bạn.
```java
String dataDir = "Your Data Directory";
```
## Bước 2: Tạo phiên bản dự án
Tạo một phiên bản dự án mới bằng Aspose.Tasks.
```java
Project project = new Project();
```
## Bước 3: Đặt thuộc tính tiền tệ
Bây giờ, hãy đặt thuộc tính tiền tệ cho dự án.
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## Bước 4: Lưu dự án
Lưu dự án với các thuộc tính tiền tệ được cập nhật.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## Bước 5: Hiển thị thông báo hoàn thành
Hiển thị thông báo cho biết quá trình đã hoàn tất thành công.
```java
System.out.println("Process completed Successfully");
```
Chúc mừng! Bạn đã đặt thành công các thuộc tính tiền tệ trong dự án Aspose.Tasks bằng Java.
## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.Tasks cho Java để đặt thuộc tính tiền tệ trong tệp dự án. Với Aspose.Tasks, các nhà phát triển có thể thao tác dữ liệu dự án một cách hiệu quả, biến nó thành công cụ có giá trị cho các ứng dụng quản lý dự án.
## Câu hỏi thường gặp
### Tôi có thể đặt nhiều loại tiền tệ trong một dự án bằng Aspose.Tasks không?
Có, Aspose.Tasks cho phép bạn xử lý nhiều loại tiền tệ trong một tệp dự án.
### Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?
Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.
### Aspose.Tasks có cung cấp hỗ trợ cho các định dạng tiền tệ tùy chỉnh không?
Hoàn toàn có thể, Aspose.Tasks mang đến sự linh hoạt trong việc xác định các định dạng tiền tệ tùy chỉnh để đáp ứng các yêu cầu cụ thể của dự án.
### Tôi có thể tích hợp Aspose.Tasks với các thư viện hoặc khung công tác Java khác không?
Có, Aspose.Tasks có thể được tích hợp liền mạch với các thư viện và khung công tác Java khác, nâng cao chức năng và tính linh hoạt của nó.
### Tôi có thể tìm sự hỗ trợ hoặc hỗ trợ bổ sung cho Aspose.Tasks ở đâu?
 Để được hỗ trợ thêm, bạn có thể truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15), nơi bạn có thể tìm thấy các tài nguyên hữu ích và tương tác với cộng đồng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
