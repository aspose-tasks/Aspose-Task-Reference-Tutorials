---
title: Định cấu hình Chế độ xem biểu đồ Gantt trong Dự án Aspose.Tasks
linktitle: Định cấu hình Chế độ xem biểu đồ Gantt trong Dự án Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách định cấu hình Chế độ xem biểu đồ dự án Gantt MS trong Aspose.Tasks bằng Java. Tùy chỉnh dự án và trực quan hóa chúng trong biểu đồ Gantt theo từng bước.
weight: 10
url: /vi/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Định cấu hình Chế độ xem biểu đồ Gantt trong Dự án Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ tìm hiểu cách định cấu hình Chế độ xem biểu đồ dự án Gantt MS trong các dự án Aspose.Tasks bằng Java. Aspose.Tasks là một API Java mạnh mẽ cho phép bạn làm việc với các tệp Microsoft Project theo chương trình. Bằng cách làm theo các bước này, bạn sẽ có thể tùy chỉnh chế độ xem biểu đồ Gantt theo yêu cầu của dự án.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt Java trên hệ thống của mình.
2.  Thư viện Aspose.Tasks: Tải xuống và cài đặt thư viện Aspose.Tasks. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).
3. Môi trường phát triển tích hợp (IDE): Chọn một IDE bạn chọn. Hướng dẫn này sử dụng IntelliJ IDEA, nhưng bạn có thể sử dụng bất kỳ IDE nào mà bạn cảm thấy thoải mái.
## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết để làm việc với Aspose.Tasks trong dự án Java của mình. Thêm các câu lệnh nhập sau vào tệp Java của bạn:
```java
import com.aspose.tasks.*;
```
Bây giờ, hãy chia nhỏ quy trình định cấu hình Chế độ xem biểu đồ dự án Gantt MS thành các hướng dẫn từng bước:
## Bước 1: Thiết lập thư mục dữ liệu
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"` với đường dẫn đến thư mục dữ liệu dự án của bạn.
## Bước 2: Tải tệp dự án
```java
Project project = new Project(dataDir + "project.mpp");
```
Tải tập tin dự án của bạn (`project.mpp` trong ví dụ này) bằng cách sử dụng`Project` lớp từ Aspose.Tasks.
## Bước 3: Thêm hoạt động mới
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Tạo một nhiệm vụ mới trong dự án của bạn bằng cách sử dụng`Task` class và thêm nó vào phần tử con của tác vụ gốc.
## Bước 4: Xác định thuộc tính tùy chỉnh
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Xác định thuộc tính tùy chỉnh mới bằng cách sử dụng`ExtendedAttributeDefinition`class và thêm nó vào các thuộc tính mở rộng của dự án.
## Bước 5: Thêm thuộc tính tùy chỉnh vào tác vụ
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Thêm thuộc tính tùy chỉnh vào tác vụ đã tạo bằng cách sử dụng`createExtendedAttribute` phương pháp.
## Bước 6: Tùy chỉnh bảng
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Tùy chỉnh bảng bằng cách thêm trường thuộc tính văn bản với chiều rộng, tiêu đề và căn chỉnh được chỉ định.
## Bước 7: Lưu dự án
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Lưu dự án với Chế độ xem biểu đồ dự án Gantt MS đã được định cấu hình. Tệp kết quả có thể được mở trong Microsoft Project 2010.
## Phần kết luận
Chúc mừng! Bạn đã định cấu hình thành công Chế độ xem biểu đồ dự án Gantt MS trong các dự án Aspose.Tasks bằng Java. Bây giờ bạn có thể tùy chỉnh các thuộc tính dự án và trực quan hóa chúng trong biểu đồ Gantt theo nhu cầu của dự án.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?
Trả lời: Có, Aspose.Tasks có sẵn cho nhiều ngôn ngữ lập trình bao gồm .NET, Java và C++.
### Câu hỏi: Aspose.Tasks có bản dùng thử miễn phí nào không?
 Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?
Đáp: Bạn có thể tìm sự hỗ trợ và đặt câu hỏi trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Làm cách nào tôi có thể mua giấy phép cho Aspose.Tasks?
 Đáp: Bạn có thể mua giấy phép từ[đây](https://purchase.aspose.com/buy).
### Hỏi: Tôi có cần giấy phép tạm thời cho mục đích thử nghiệm không?
 Đáp: Có, bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
