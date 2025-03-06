---
title: Xử lý các thuộc tính mở rộng trong dự án Aspose.Tasks
linktitle: Xử lý các thuộc tính mở rộng trong dự án Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách xử lý các thuộc tính mở rộng trong các dự án Aspose.Tasks bằng Java một cách hiệu quả. Hướng dẫn từng bước để quản lý dự án hiệu quả.
type: docs
weight: 13
url: /vi/java/project-management/extended-attributes/
---
## Giới thiệu
Quản lý các thuộc tính mở rộng trong quản lý dự án là rất quan trọng để tùy chỉnh và nâng cao dữ liệu dự án. Aspose.Tasks for Java cung cấp các công cụ mạnh mẽ để xử lý các thuộc tính mở rộng trong tệp MS Project một cách hiệu quả. Hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình theo từng bước, đảm bảo bạn nắm bắt kỹ lưỡng từng khái niệm.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Kiến thức cơ bản về lập trình Java.
2. JDK (Bộ công cụ phát triển Java) được cài đặt trên hệ thống của bạn.
3. Thư viện Aspose.Tasks for Java được tải xuống và thiết lập trong dự án Java của bạn.
## Gói nhập khẩu
Trước tiên, hãy nhập các gói cần thiết để bắt đầu:
```java
import java.util.Date;
import com.aspose.tasks.*;
```
## Bước 1: Xác định thư mục dữ liệu
```java
String dataDir = "Your Data Directory";
```
 Đảm bảo thay thế`"Your Data Directory"` với đường dẫn đến thư mục dữ liệu của dự án của bạn.
## Bước 2: Tải tệp dự án
```java
Project prj = new Project(dataDir + "project5.mpp");
```
 Dòng này tải tệp dự án có tên`"project5.mpp"`.
## Bước 3: Truy cập định nghĩa thuộc tính mở rộng
```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```
Ở đây, chúng tôi lấy tập hợp các định nghĩa thuộc tính mở rộng từ dự án.
## Bước 4: Tạo định nghĩa thuộc tính mở rộng
```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```
 Đoạn mã này tạo ra một định nghĩa thuộc tính mở rộng cho các tác vụ, chỉ định loại trường tùy chỉnh là`Start` và tên thuộc tính như`"Start 7"`.
## Bước 5: Thêm định nghĩa vào dự án
```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```
Chúng tôi thêm định nghĩa thuộc tính mở rộng mới được tạo vào cả dự án và tập hợp các định nghĩa thuộc tính.
## Bước 6: Truy cập tác vụ và thuộc tính mở rộng
```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```
Ở đây, chúng tôi truy xuất một nhiệm vụ từ dự án và các thuộc tính mở rộng liên quan của nó.
## Bước 7: Tạo phiên bản thuộc tính mở rộng
```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```
Bước này tạo một phiên bản của thuộc tính mở rộng dựa trên định nghĩa thuộc tính được xác định trước đó.
## Bước 8: Đặt giá trị thuộc tính
```java
Date date = new Date();
ea.setDateValue(date);
```
Chúng tôi đặt giá trị của thuộc tính mở rộng, trong trường hợp này là giá trị ngày.
## Bước 9: Thêm thuộc tính vào tác vụ
```java
eas.add(ea);
```
Cuối cùng, chúng tôi thêm thuộc tính mở rộng vào tác vụ.
## Bước 10: Lưu dự án
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
Dòng này lưu dự án đã sửa đổi với thuộc tính mở rộng được thêm vào tệp XML.
## Phần kết luận
Trong hướng dẫn này, bạn đã học cách xử lý các thuộc tính mở rộng trong dự án Aspose.Tasks bằng Java. Bằng cách làm theo các bước này, bạn có thể quản lý dữ liệu dự án tùy chỉnh một cách hiệu quả, nâng cao khả năng quản lý dự án của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều ngôn ngữ lập trình bao gồm Java, .NET và C++.
### Câu hỏi: Aspose.Tasks có bản dùng thử miễn phí không?
Đáp: Có, bạn có thể tải xuống bản dùng thử miễn phí từ trang web Aspose.Tasks.
### Câu hỏi: Tôi có thể tùy chỉnh các loại thuộc tính mở rộng không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks cho phép bạn xác định các loại thuộc tính mở rộng tùy chỉnh phù hợp với nhu cầu dự án của bạn.
### Câu hỏi: Làm cách nào tôi có thể truy cập tài liệu Aspose.Tasks?
 Trả lời: Bạn có thể tìm thấy tài liệu toàn diện trên trang web Aspose.Tasks[tài liệu](https://reference.aspose.com/tasks/java/).
### Câu hỏi: Người dùng Aspose.Tasks có được hỗ trợ kỹ thuật không?
 Trả lời: Có, bạn có thể truy cập hỗ trợ kỹ thuật thông qua diễn đàn Aspose.Tasks[trang mạng](https://forum.aspose.com/c/tasks/15).