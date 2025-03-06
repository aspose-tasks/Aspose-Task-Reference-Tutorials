---
title: Công thức dự án MS với Aspose.Tasks cho Java
linktitle: Làm việc với Công thức trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách thao tác các tệp MS Project trong Java bằng thư viện Aspose.Tasks. Tạo, sửa đổi và tính toán các thuộc tính một cách dễ dàng.
weight: 11
url: /vi/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Công thức dự án MS với Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào làm việc với MS Project Formulas bằng cách sử dụng Aspose.Tasks cho Java. Aspose.Tasks là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project theo chương trình. Với các tính năng mở rộng của nó, bạn có thể dễ dàng tạo, đọc, sửa đổi và chuyển đổi các tệp dự án trong các ứng dụng Java.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:
### Môi trường phát triển Java
Đảm bảo bạn đã cài đặt Bộ công cụ phát triển Java (JDK) trên hệ thống của mình. Bạn có thể tải xuống và cài đặt JDK mới nhất từ trang web của Oracle.
### Thư viện Aspose.Tasks
Bạn cần thêm thư viện Aspose.Tasks vào dự án Java của mình. Bạn có thể tải xuống thư viện từ[Trang tải xuống Aspose.Tasks cho Java](https://releases.aspose.com/tasks/java/) và đưa nó vào phần phụ thuộc của dự án của bạn.

## Gói nhập khẩu
Trước khi đi sâu vào các ví dụ, hãy nhập các gói cần thiết vào mã Java của bạn:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Hãy chia nhỏ ví dụ được cung cấp thành nhiều bước:
## Bước 1: Tạo dự án thử nghiệm với trường tùy chỉnh
```java
Project project = CreateTestProjectWithCustomField();
```
 Đầu tiên, tạo một dự án thử nghiệm với trường tùy chỉnh bằng cách sử dụng`CreateTestProjectWithCustomField()` phương pháp. Phương thức này sẽ trả về một đối tượng Project đại diện cho dự án mới được tạo.
## Bước 2: Xác định định nghĩa thuộc tính mở rộng
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Truy xuất định nghĩa thuộc tính mở rộng từ dự án và đặt bí danh và công thức của nó. Trong ví dụ này, chúng tôi đang xác định một thuộc tính để tính số ngày từ ngày kết thúc đến thời hạn.
## Bước 3: Đặt thời hạn cho một nhiệm vụ
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Tạo một đối tượng Lịch và đặt ngày hết hạn. Sau đó, truy xuất một nhiệm vụ từ dự án và đặt thời hạn cho nó bằng cách sử dụng đối tượng Lịch.
## Bước 4: Lưu dự án
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Cuối cùng, lưu dự án vào một tệp có tên và định dạng được chỉ định. Trong trường hợp này, chúng tôi đang lưu nó dưới dạng tệp MPP.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách làm việc với MS Project Formulas bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn có thể thao tác hiệu quả các tệp dự án theo chương trình, thêm các trường tùy chỉnh và tính toán các thuộc tính dựa trên công thức.

## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều ngôn ngữ lập trình khác nhau bao gồm Java, .NET, v.v.
### Câu hỏi: Aspose.Tasks có bản dùng thử miễn phí không?
 Trả lời: Có, bạn có thể tải xuống bản dùng thử miễn phí Aspose.Tasks từ[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm tài liệu về Aspose.Tasks ở đâu?
 Trả lời: Bạn có thể tìm tài liệu về Aspose.Tasks[đây](https://reference.aspose.com/tasks/java/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks?
 A: Để được hỗ trợ, bạn có thể truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Tôi có cần giấy phép tạm thời để sử dụng Aspose.Tasks không?
Đáp: Nếu bạn yêu cầu các tính năng bổ sung, bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
