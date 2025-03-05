---
title: Lưu dưới dạng CSV, văn bản và mẫu trong Aspose.Tasks
linktitle: Lưu dưới dạng CSV, văn bản và mẫu trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách lưu tệp Microsoft Project ở định dạng CSV, Văn bản và Mẫu bằng Aspose.Tasks cho Java.
type: docs
weight: 16
url: /vi/java/project-file-operations/save-csv-text-template/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách lưu tệp dự án ở nhiều định dạng khác nhau như CSV, Văn bản và Mẫu bằng Aspose.Tasks cho Java. Aspose.Tasks là một thư viện Java mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project mà không cần cài đặt Microsoft Project.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
2.  Thư viện Aspose.Tasks cho Java được tải xuống và định cấu hình trong dự án Java của bạn. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).
3. Kiến thức cơ bản về ngôn ngữ lập trình Java.

## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết vào tệp Java của mình:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Lưu dự án dưới dạng CSV
Hãy chia nhỏ các bước để lưu dự án dưới dạng CSV:
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
## Lưu dự án dưới dạng văn bản
Đây là cách bạn có thể lưu dự án dưới dạng Văn bản:
### Bước 1: Tải dự án
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Bước 2: Lưu dưới dạng văn bản
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Lưu dự án dưới dạng mẫu
Lưu dự án dưới dạng mẫu bao gồm các bước sau:
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

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách lưu tệp Microsoft Project dưới dạng CSV, Văn bản và Mẫu bằng Aspose.Tasks cho Java. Với các bước đơn giản này, bạn có thể quản lý hiệu quả các tệp dự án của mình ở nhiều định dạng khác nhau, nâng cao năng suất của bạn với tư cách là nhà phát triển Java.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks cho Java có thể xử lý các tệp dự án phức tạp không?
Đ: Chắc chắn rồi! Aspose.Tasks cho Java có thể xử lý các dự án có độ phức tạp khác nhau một cách dễ dàng, cung cấp hỗ trợ toàn diện cho các định dạng tệp Microsoft Project.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
 Đáp: Có, bạn có thể dùng thử miễn phí Aspose.Tasks cho Java từ[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho Java ở đâu?
 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) nếu có bất kỳ trợ giúp hoặc thắc mắc nào liên quan đến Aspose.Tasks for Java.
### Câu hỏi: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?
 Đáp: Có, bạn có thể mua giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/), cho phép bạn đánh giá toàn bộ tiềm năng của thư viện.
### Câu hỏi: Aspose.Tasks dành cho Java có tương thích với các hệ điều hành khác nhau không?
Trả lời: Có, Aspose.Tasks cho Java tương thích với nhiều hệ điều hành khác nhau, bao gồm Windows, macOS và Linux.