---
title: Xác định phiên bản dự án MS với Aspose.Tasks
linktitle: Xác định phiên bản dự án với Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách xác định phiên bản của tệp MS Project theo lập trình bằng Aspose.Tasks cho Java. Hướng dẫn từng bước với các ví dụ về mã.
weight: 12
url: /vi/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xác định phiên bản dự án MS với Aspose.Tasks

## Giới thiệu
Hướng dẫn này sẽ hướng dẫn bạn sử dụng Aspose.Tasks cho Java để xác định phiên bản của tệp MS Project theo từng bước. Aspose.Tasks là một API Java mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project mà không yêu cầu cài đặt Microsoft Project.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Tệp JAR Aspose.Tasks cho Java: Tải xuống thư viện Aspose.Tasks cho Java từ[trang mạng](https://releases.aspose.com/tasks/java/) và thêm nó vào dự án Java của bạn.
3. Tệp dự án MS: Chuẩn bị tệp MS Project (định dạng XML) để thử nghiệm.

## Gói nhập khẩu
Trước khi đi sâu vào mã, hãy nhập các gói cần thiết:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Bước 1: Thiết lập dự án
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"` với đường dẫn đến thư mục chứa tệp MS Project của bạn.
## Bước 2: Tải dự án
```java
Project project = new Project(dataDir + "input.xml");
```
 Thay thế`"input.xml"` với tên tệp MS Project của bạn.
## Bước 3: Xác định phiên bản dự án
```java
//Hiển thị thuộc tính phiên bản dự án
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Đoạn mã này truy xuất và in phiên bản cũng như ngày lưu cuối cùng của tệp MS Project.
## Bước 4: Hiển thị kết quả
```java
//Hiển thị kết quả chuyển đổi.
System.out.println("Process completed Successfully");
```
Dòng này cho biết sự hoàn thành của quá trình.

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách xác định phiên bản của tệp MS Project bằng Aspose.Tasks cho Java. Bằng cách làm theo hướng dẫn từng bước, bạn có thể làm việc hiệu quả với các tệp MS Project trong ứng dụng Java của mình mà không gặp rắc rối.

## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều ngôn ngữ lập trình bao gồm .NET, Java và C++.
### Câu hỏi: Aspose.Tasks có phù hợp với các dự án quy mô lớn không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks được thiết kế để xử lý các dự án ở mọi quy mô một cách dễ dàng.
### Câu hỏi: Tôi có thể tùy chỉnh dữ liệu dự án bằng Aspose.Tasks không?
Trả lời: Có, bạn có thể thao tác dữ liệu dự án, sửa đổi nhiệm vụ, tài nguyên, v.v. bằng cách sử dụng Aspose.Tasks.
### Câu hỏi: Aspose.Tasks có yêu cầu cài đặt Microsoft Project không?
Trả lời: Không, Aspose.Tasks hoạt động độc lập và không yêu cầu cài đặt Microsoft Project.
### Câu hỏi: Aspose.Tasks có hỗ trợ kỹ thuật không?
 Đáp: Có, bạn có thể nhận hỗ trợ kỹ thuật từ diễn đàn Aspose.Tasks tại[đây](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
