---
title: Hỗ trợ các hàm đánh giá trong công thức Aspose.Tasks
linktitle: Hỗ trợ các hàm đánh giá trong công thức Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách hỗ trợ đánh giá các hàm MS Project trong công thức Aspose.Tasks bằng Java. Tăng năng suất của bạn với Aspose.Tasks.
weight: 10
url: /vi/java/formulas/evaluation-functions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hỗ trợ các hàm đánh giá trong công thức Aspose.Tasks


## Giới thiệu
Aspose.Tasks cho Java là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project theo chương trình. Một trong những tính năng chính của nó là khả năng hỗ trợ đánh giá các chức năng MS Project trong các công thức Aspose.Tasks. Khả năng này cho phép người dùng thực hiện các phép tính và phân tích phức tạp trực tiếp trong các ứng dụng Java của họ.
## Điều kiện tiên quyết
Trước khi bắt đầu tích hợp các hàm MS Project vào công thức Aspose.Tasks, hãy đảm bảo bạn có những điều sau:
1. Môi trường phát triển Java: Đảm bảo rằng bạn đã cài đặt Java trên hệ thống của mình cùng với một IDE tương thích để phát triển Java như IntelliJ IDEA hoặc Eclipse.
2.  Aspose.Tasks for Java Library: Tải xuống và đưa thư viện Aspose.Tasks for Java vào dự án Java của bạn. Bạn có thể tải nó xuống từ[Trang tải xuống Aspose.Tasks cho Java](https://releases.aspose.com/tasks/java/).
## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói cần thiết trong lớp Java của bạn để sử dụng các chức năng của Aspose.Tasks:
```java
import com.aspose.tasks.*;
```

## Bước 1: Tạo đối tượng dự án mới
 Đầu tiên, tạo một cái mới`Project`đối tượng để làm việc với:
```java
Project project = new Project();
```
Điều này khởi tạo một dự án trống mới.
## Bước 2: Xác định thuộc tính mở rộng cho nhiệm vụ
Tiếp theo, xác định thuộc tính mở rộng cho tác vụ. Thuộc tính này sẽ chứa dữ liệu tùy chỉnh được liên kết với các tác vụ:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 Ở đây, chúng tôi tạo một thuộc tính mở rộng thuộc loại`Number` với tên "Sine" cho các nhiệm vụ.
## Bước 3: Thêm thuộc tính mở rộng vào dự án
Thêm định nghĩa thuộc tính mở rộng vào danh sách các thuộc tính mở rộng của dự án:
```java
project.getExtendedAttributes().add(attr);
```
Điều này thêm thuộc tính tùy chỉnh cho dự án.
## Bước 4: Tạo một tác vụ mới
Bây giờ, hãy tạo một nhiệm vụ mới trong dự án:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Điều này thêm một nhiệm vụ mới có tên "Nhiệm vụ" vào dự án.
## Bước 5: Liên kết thuộc tính mở rộng với nhiệm vụ
Liên kết thuộc tính mở rộng được tạo trước đó với tác vụ:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
Điều này liên kết thuộc tính mở rộng "Sine" với nhiệm vụ.

## Phần kết luận
Tóm lại, việc tích hợp các hàm MS Project vào các công thức Aspose.Tasks trong Java là một quá trình đơn giản. Bằng cách làm theo các bước được cung cấp, bạn có thể sử dụng hiệu quả các khả năng mạnh mẽ của Aspose.Tasks dành cho Java để thao tác và phân tích các tệp Microsoft Project theo chương trình.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks dành cho Java có thể xử lý các công thức MS Project phức tạp không?
Trả lời: Có, Aspose.Tasks for Java hỗ trợ đánh giá nhiều chức năng MS Project, cho phép thực hiện các phép tính phức tạp trong các ứng dụng Java.
### Câu hỏi: Aspose.Tasks dành cho Java có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?
Trả lời: Có, Aspose.Tasks for Java hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.
### Câu hỏi: Tôi có thể dùng thử Aspose.Tasks cho Java trước khi mua không?
 Trả lời: Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Tasks cho Java từ trang web[đây](https://purchase.aspose.com/buy).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho Java?
Trả lời: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Có giấy phép tạm thời dành cho Aspose.Tasks dành cho Java không?
 Trả lời: Có, bạn có thể lấy giấy phép tạm thời cho mục đích thử nghiệm từ trang web Aspose[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
