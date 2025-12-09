---
date: 2025-12-09
description: Tìm hiểu cách tạo đối tượng dự án trong Java và hỗ trợ các hàm đánh giá
  trong công thức Aspose.Tasks bằng Java. Khám phá cách tạo thuộc tính mở rộng cho
  các nhiệm vụ.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Tạo Đối tượng Dự án Java – Hỗ trợ các Hàm Đánh giá trong Aspose.Tasks
url: /vi/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hỗ trợ các hàm Đánh giá trong công thức Aspose.Tasks

## Giới thiệu
Aspose.Tasks for Java cho phép bạn **create project object java** các thể hiện và đánh giá các hàm Microsoft Project trực tiếp trong mã Java của bạn. Bằng cách nhúng các công thức này, bạn có thể thực hiện các phép tính phức tạp, tạo báo cáo tùy chỉnh và tự động hoá phân tích dự án mà không cần rời khỏi môi trường phát triển. Hướng dẫn này sẽ đưa bạn qua toàn bộ quy trình — từ việc thiết lập đối tượng dự án đến việc thêm thuộc tính mở rộng có thể chứa dữ liệu tùy chỉnh.

## Câu trả lời nhanh
- **“create project object java” có nghĩa là gì?** Nó tạo một thể hiện `Project` trong bộ nhớ mà bạn có thể thao tác bằng chương trình.  
- **Thư viện nào được yêu cầu?** Aspose.Tasks for Java (tải xuống từ trang chính thức).  
- **Tôi có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất; phiên bản dùng thử miễn phí có sẵn.  
- **Tôi có thể sử dụng trường tùy chỉnh không?** Có – bạn có thể định nghĩa và gắn thuộc tính mở rộng vào các tác vụ.  
- **Điều này có tương thích với tất cả các định dạng tệp Project không?** Aspose.Tasks hỗ trợ các định dạng MPP, MPT và XML.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Môi trường phát triển Java** – JDK 8+ và một IDE như IntelliJ IDEA hoặc Eclipse.  
2. **Thư viện Aspose.Tasks for Java** – Tải xuống và bao gồm thư viện từ [trang tải xuống Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Nhập các gói
Thêm không gian tên Aspose.Tasks vào lớp Java của bạn để có thể làm việc với dự án, tác vụ và thuộc tính mở rộng:

```java
import com.aspose.tasks.*;
```

## Bước 1: Tạo Project Object Java
Khởi tạo một đối tượng `Project` mới. Đối tượng này sẽ đóng vai trò là container cho tất cả các tác vụ, nguồn lực và dữ liệu tùy chỉnh mà bạn sẽ định nghĩa.

```java
Project project = new Project();
```

Dòng trên **creates project object java** khởi tạo một dự án trống, sẵn sàng cho việc tùy biến.

## Bước 2: Cách tạo thuộc tính mở rộng
Định nghĩa một thuộc tính mở rộng sẽ lưu trữ dữ liệu số tùy chỉnh (ví dụ: giá trị sin) cho mỗi tác vụ.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Ở đây chúng ta **create extended attribute** loại `Number` có tên “Sine” và gắn nó vào các tác vụ.

## Bước 3: Thêm thuộc tính mở rộng vào Project
Đăng ký định nghĩa thuộc tính với dự án để mọi tác vụ đều có thể tham chiếu tới nó.

```java
project.getExtendedAttributes().add(attr);
```

## Bước 4: Tạo một tác vụ mới
Thêm một tác vụ đơn giản có tên “Task” dưới tác vụ gốc của dự án.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Bước 5: Gắn thuộc tính mở rộng vào tác vụ
Liên kết thuộc tính mở rộng đã định nghĩa trước đó với tác vụ mới tạo.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Bây giờ tác vụ chứa trường tùy chỉnh “Sine” mà bạn có thể sử dụng trong công thức hoặc các phép tính.

## Tại sao nên sử dụng các hàm đánh giá?
Nhúng các hàm MS Project vào công thức Aspose.Tasks cho phép bạn:

- Thực hiện các phép tính ngay lập tức (ví dụ: `Sin([Start])`) mà không cần công cụ bên ngoài.  
- Giữ toàn bộ logic dự án trong một codebase duy nhất, dễ bảo trì.  
- Tạo báo cáo động phản ánh các thay đổi dữ liệu theo thời gian thực.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Formula returns `NaN`** | Xác minh rằng kiểu trường tùy chỉnh khớp với kiểu số mong đợi. |
| **Extended attribute not visible** | Đảm bảo định nghĩa thuộc tính được thêm vào dự án **trước** khi tạo các tác vụ. |
| **License exception** | Cài đặt giấy phép tạm thời hoặc đầy đủ; chế độ dùng thử có thể giới hạn một số tính năng. |

## Câu hỏi thường gặp

**Q: Aspose.Tasks for Java có thể xử lý các công thức MS Project phức tạp không?**  
A: Có, Aspose.Tasks for Java hỗ trợ đánh giá một loạt các hàm MS Project, cho phép thực hiện các phép tính phức tạp trong ứng dụng Java.

**Q: Aspose.Tasks for Java có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
A: Có, Aspose.Tasks for Java hỗ trợ nhiều phiên bản tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.

**Q: Tôi có thể thử Aspose.Tasks for Java trước khi mua không?**  
A: Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Tasks for Java từ trang web [here](https://purchase.aspose.com/buy).

**Q: Làm thế nào để tôi nhận được hỗ trợ cho Aspose.Tasks for Java?**  
A: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: Có giấy phép tạm thời cho Aspose.Tasks for Java không?**  
A: Có, bạn có thể lấy giấy phép tạm thời để thử nghiệm từ trang web Aspose [here](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2025-12-09  
**Kiểm tra với:** Aspose.Tasks for Java 24.10  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}