---
title: Viết và đọc các công thức dự án MS trong Aspose.Tasks
linktitle: Viết và đọc công thức trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách viết và đọc các công thức MS Project một cách hiệu quả với Aspose.Tasks cho Java. Nâng cao kỹ năng quản lý dự án của bạn.
type: docs
weight: 12
url: /vi/java/formulas/write-read-formulas/
---
## Giới thiệu
Trong lĩnh vực quản lý dự án, việc xử lý dữ liệu hiệu quả là điều tối quan trọng. Aspose.Tasks cho Java là một giải pháp mạnh mẽ hỗ trợ thao tác và trích xuất dữ liệu từ các tệp Microsoft Project. Một tính năng mạnh mẽ mà nó cung cấp là khả năng viết và đọc các công thức MS Project. Hướng dẫn này sẽ hướng dẫn bạn quy trình tận dụng chức năng này để nâng cao các nhiệm vụ quản lý dự án của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt Java trên hệ thống của mình.
2.  Aspose.Tasks cho Java: Tải xuống và cài đặt Aspose.Tasks cho Java từ[đây](https://releases.aspose.com/tasks/java/).
3. Môi trường phát triển tích hợp (IDE): Chọn IDE ưa thích của bạn để phát triển Java.

## Nhập gói
Để bắt đầu, hãy nhập các gói cần thiết vào dự án Java của bạn:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Bước 1: Thiết lập thư mục dữ liệu
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Data Directory";
```
Trong bước này, hãy xác định thư mục chứa các tệp MS Project của bạn.
## Bước 2: Tải tệp dự án
```java
Project project = new Project(dataDir + "project.mpp");
```
Tại đây, hãy tải tệp MS Project vào một`Project` đối tượng để thao tác.
## Bước 3: Xác định công thức tùy chỉnh
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
Bước này liên quan đến việc tạo trường tùy chỉnh với công thức tăng gấp đôi chi phí nhiệm vụ.
## Bước 4: Thêm nhiệm vụ và đặt chi phí
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Ở đây, một nhiệm vụ mới được thêm vào và chi phí của nó được đặt thành 100.
## Bước 5: Lưu tệp dự án
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Cuối cùng, lưu tệp dự án đã sửa đổi.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá cách viết và đọc các công thức MS Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn có thể thao tác dữ liệu dự án một cách hiệu quả để đáp ứng các yêu cầu cụ thể của mình.
## Câu hỏi thường gặp
### Aspose.Tasks có tương thích với tất cả các phiên bản MS Project không?
Aspose.Tasks cung cấp khả năng tương thích với nhiều phiên bản khác nhau của MS Project, đảm bảo tính linh hoạt cho người dùng.
### Tôi có thể tích hợp Aspose.Tasks vào dự án Java hiện tại của mình không?
Tuyệt đối! Aspose.Tasks cung cấp khả năng tích hợp liền mạch với các dự án Java thông qua việc sử dụng API đơn giản.
### Có bất kỳ hạn chế nào đối với các loại công thức tôi có thể tạo không?
Với Aspose.Tasks, bạn có thể linh hoạt hơn trong việc tạo các công thức tùy chỉnh phù hợp với nhu cầu dự án của mình.
### Aspose.Tasks có hỗ trợ triển khai đa nền tảng không?
Có, Aspose.Tasks hỗ trợ triển khai trên nhiều nền tảng, nâng cao tính linh hoạt của nó.
### Làm cách nào tôi có thể nhận được hỗ trợ kỹ thuật cho Aspose.Tasks?
 Để được hỗ trợ kỹ thuật và hỗ trợ cộng đồng, hãy truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).