---
title: Đọc dữ liệu định nghĩa nhóm trong Aspose.Tasks
linktitle: Đọc dữ liệu định nghĩa nhóm trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách đọc dữ liệu định nghĩa nhóm từ các tệp Microsoft Project bằng Aspose.Tasks cho Java. Thực hiện theo hướng dẫn từng bước của chúng tôi.
weight: 10
url: /vi/java/project-data-reading/read-group-definition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc dữ liệu định nghĩa nhóm trong Aspose.Tasks

## Giới thiệu
Aspose.Tasks cho Java là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project một cách dễ dàng. Trong hướng dẫn này, chúng ta sẽ từng bước thực hiện quy trình đọc dữ liệu định nghĩa nhóm từ tệp dự án bằng cách sử dụng Aspose.Tasks cho Java.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Tasks for Java Library: Tải xuống và cài đặt thư viện Aspose.Tasks for Java từ[đây](https://releases.aspose.com/tasks/java/).
3. Môi trường phát triển tích hợp (IDE): Chọn IDE ưa thích của bạn như IntelliJ IDEA hoặc Eclipse.

## Gói nhập khẩu
Trước tiên, hãy nhập các gói cần thiết để bắt đầu làm việc với Aspose.Tasks cho Java.
```java
import com.aspose.tasks.*;
```
## Bước 1: Thiết lập thư mục dữ liệu của bạn
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"` với đường dẫn đến thư mục chứa tệp dự án của bạn.
## Bước 2: Tải tệp dự án
```java
Project project = new Project(dataDir + "project.mpp");
```
 Tải tệp dự án của bạn bằng cách sử dụng`Project` hàm tạo lớp, chuyển đường dẫn đến tệp dự án của bạn.
## Bước 3: Truy xuất số lượng nhóm nhiệm vụ
```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```
 Truy xuất số lượng nhóm nhiệm vụ trong dự án bằng cách sử dụng`getTaskGroups()` phương pháp.
## Bước 4: Truy xuất thông tin nhóm nhiệm vụ
```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```
Truy xuất thông tin về một nhóm nhiệm vụ cụ thể, chẳng hạn như tên của nhóm đó và số lượng tiêu chí nhóm.
## Bước 5: Truy xuất thông tin tiêu chí nhóm
```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```
Truy xuất thông tin về tiêu chí nhóm, chẳng hạn như trường, nhóm trên, màu ô và mẫu.
## Bước 6: Kiểm tra nhóm phụ huynh
```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```
Kiểm tra xem nhóm cha có bằng nhóm nhiệm vụ không.
## Bước 7: Truy xuất thông tin phông chữ của tiêu chí
```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```
Truy xuất thông tin phông chữ cho tiêu chí, chẳng hạn như họ phông chữ, kích thước, kiểu và thứ tự sắp xếp.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách đọc dữ liệu định nghĩa nhóm từ tệp Microsoft Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn có thể trích xuất và sử dụng thông tin nhóm tác vụ một cách hiệu quả trong các ứng dụng Java của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho Java để sửa đổi các tệp dự án không?
Trả lời: Có, Aspose.Tasks cho Java cung cấp các tính năng mở rộng cho cả việc đọc và sửa đổi các tệp Microsoft Project theo chương trình.
### Câu hỏi: Aspose.Tasks dành cho Java có tương thích với tất cả các phiên bản của tệp Microsoft Project không?
Trả lời: Aspose.Tasks for Java hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm các định dạng MPP và XML.
### Câu hỏi: Làm cách nào tôi có thể xử lý lỗi khi làm việc với Aspose.Tasks cho Java?
Trả lời: Bạn có thể triển khai cơ chế xử lý lỗi bằng cách sử dụng các khối thử bắt để xử lý khéo léo các ngoại lệ có thể xảy ra trong quá trình thao tác với tệp.
### Câu hỏi: Aspose.Tasks dành cho Java có hỗ trợ xuất dữ liệu dự án sang các định dạng khác không?
Trả lời: Có, Aspose.Tasks cho Java cho phép bạn xuất dữ liệu dự án sang các định dạng như PDF, XLSX và CSV.
### Câu hỏi: Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Tasks cho Java ở đâu?
 Đáp: Bạn có thể ghé thăm[Aspose.Tasks cho tài liệu Java](https://reference.aspose.com/tasks/java/) để có hướng dẫn toàn diện và tham khảo[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để hỗ trợ cộng đồng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
