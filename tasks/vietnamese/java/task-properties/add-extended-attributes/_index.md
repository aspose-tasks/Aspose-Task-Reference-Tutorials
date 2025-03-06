---
title: Thêm thuộc tính mở rộng vào nhiệm vụ trong Aspose.Tasks
linktitle: Thêm thuộc tính mở rộng vào nhiệm vụ trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Khám phá sức mạnh của Aspose.Tasks Java trong việc tùy chỉnh các tệp Microsoft Project với các thuộc tính mở rộng. Nâng cao khả năng quản lý dự án của bạn một cách dễ dàng.
weight: 11
url: /vi/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm thuộc tính mở rộng vào nhiệm vụ trong Aspose.Tasks

## Giới thiệu
Nâng cao khả năng quản lý dự án của bạn là rất quan trọng để theo dõi nhiệm vụ và quản lý tài nguyên hiệu quả. Aspose.Tasks for Java cung cấp một giải pháp mạnh mẽ cho các nhà phát triển Java để thao tác các tệp Microsoft Project một cách liền mạch. Trong hướng dẫn này, chúng ta sẽ khám phá cách thêm các thuộc tính mở rộng vào các tác vụ bằng Aspose.Tasks cho Java, cho phép bạn tùy chỉnh và sắp xếp dữ liệu dự án theo yêu cầu cụ thể của mình.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Kiến thức cơ bản về lập trình Java.
-  Aspose.Tasks cho thư viện Java đã được cài đặt. Bạn có thể tải nó xuống từ[trang mạng](https://releases.aspose.com/tasks/java/).
- Môi trường phát triển tích hợp Java (IDE) được cài đặt trên hệ thống của bạn.
## Gói nhập khẩu
Trong dự án Java của bạn, hãy nhập các gói cần thiết để truy cập các chức năng của Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Bây giờ, hãy chia từng ví dụ thành nhiều bước:
## 1. Thêm thuộc tính văn bản thuần túy
1. Đặt đường dẫn thư mục tài liệu:
```java
String dataDir = "Your Document Directory";
```
2. Tạo một dự án mới:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Tạo Định nghĩa thuộc tính mở rộng của loại Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Thêm định nghĩa vào bộ sưu tập Thuộc tính mở rộng của dự án:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Thêm nhiệm vụ vào dự án:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Tạo Thuộc tính mở rộng từ Định nghĩa thuộc tính:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Gán một giá trị cho Thuộc tính mở rộng được tạo:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Thêm thuộc tính mở rộng vào nhiệm vụ:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Lưu dự án:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Thêm thuộc tính văn bản với tùy chọn tra cứu
Thực hiện theo các bước tương tự như trên, thay thế Text1 bằng Text2 và tùy chỉnh các giá trị tra cứu.
## 3. Thêm thuộc tính thời lượng với tùy chọn tra cứu
Thực hiện theo các bước tương tự như trên, thay thế Text1 bằng Duration2 và tùy chỉnh các giá trị tra cứu.
## Phần kết luận
Bằng cách làm theo hướng dẫn từng bước này, bạn đã học được cách tận dụng Aspose.Tasks cho Java để thêm các thuộc tính mở rộng cho các tác vụ trong tệp Microsoft Project của mình. Tùy chỉnh này cho phép bạn điều chỉnh phương pháp quản lý dự án của mình, nâng cao tính linh hoạt và hiệu quả.
## Các câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho Java với các thư viện Java khác không?
Trả lời: Có, Aspose.Tasks cho Java có thể được tích hợp liền mạch vào các dự án Java của bạn và nó hoạt động tốt với các thư viện Java khác.
### Câu hỏi: Aspose.Tasks dành cho Java có phù hợp với các ứng dụng quản lý dự án quy mô lớn không?
Đáp: Hoàn toàn có thể, Aspose.Tasks dành cho Java được thiết kế để xử lý các dự án có quy mô khác nhau, bao gồm cả các ứng dụng quy mô lớn.
### Câu hỏi: Có bất kỳ cân nhắc cấp phép nào khi sử dụng Aspose.Tasks cho Java trong một dự án thương mại không?
 Đáp: Có, hãy đảm bảo xem lại thông tin cấp phép được cung cấp trên[Trang web Aspose.Tasks](https://purchase.aspose.com/buy).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ hoặc trợ giúp với Aspose.Tasks cho Java?
 Đáp: Hãy ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được cộng đồng hỗ trợ và thảo luận.
### Câu hỏi: Tôi có thể dùng thử Aspose.Tasks cho Java trước khi mua không?
 Trả lời: Có, bạn có thể truy cập phiên bản dùng thử miễn phí[đây](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
