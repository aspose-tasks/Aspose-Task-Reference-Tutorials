---
date: 2026-02-13
description: Học cách tạo báo cáo dự án bằng cách tạo một đối tượng dự án trong Java,
  thêm các thuộc tính mở rộng và sử dụng các hàm đánh giá với Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Tạo Báo Cáo Dự Án – Tạo Đối Tượng Dự Án Java
url: /vi/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hỗ trợ các hàm Đánh giá trong Aspose.Tasks Formulas

## Giới thiệu
Aspose.Tasks for Java cho phép bạn **tạo báo cáo dự án** bằng cách tạo một **đối tượng dự án** trong Java và đánh giá các hàm Microsoft Project trực tiếp trong mã của bạn. Bằng cách nhúng các công thức này, bạn có thể thực hiện các phép tính phức tạp, tạo báo cáo tùy chỉnh và tự động phân tích dự án mà không cần rời khỏi môi trường phát triển. Trong hướng dẫn này, chúng ta sẽ đi qua việc tạo đối tượng dự án, thêm thuộc tính mở rộng, và sử dụng các hàm đánh giá để **thêm dữ liệu trường tùy chỉnh cho nhiệm vụ**.

## Câu trả lời nhanh
- **“create project object java” có nghĩa là gì?** Nó tạo một thể hiện `Project` trong bộ nhớ mà bạn có thể thao tác bằng chương trình.  
- **Thư viện nào cần thiết?** Aspose.Tasks for Java (tải về từ trang chính thức).  
- **Có cần giấy phép không?** Cần một giấy phép Aspose.Tasks tạm thời hoặc đầy đủ cho môi trường sản xuất; có bản dùng thử miễn phí.  
- **Tôi có thể sử dụng trường tùy chỉnh không?** Có – bạn có thể **thêm thuộc tính mở rộng** vào các nhiệm vụ và coi chúng như các trường tùy chỉnh.  
- **Có tương thích với tất cả định dạng tệp Project không?** Aspose.Tasks hỗ trợ các định dạng MPP, MPT và XML.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

1. **Môi trường phát triển Java** – JDK 8+ và một IDE như IntelliJ IDEA hoặc Eclipse.  
2. **Thư viện Aspose.Tasks for Java** – Tải về và đưa vào dự án từ [trang tải Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Nhập các gói
Thêm namespace Aspose.Tasks vào lớp Java của bạn để có thể làm việc với dự án, nhiệm vụ và thuộc tính mở rộng:

```java
import com.aspose.tasks.*;
```

## Tạo Báo cáo Dự án – Tạo Đối tượng Dự án Java
Khởi tạo một đối tượng `Project` mới. Đối tượng này sẽ là container cho tất cả các nhiệm vụ, nguồn lực và dữ liệu tùy chỉnh mà bạn sẽ định nghĩa.

```java
Project project = new Project();
```

Dòng trên **tạo project object java** ban đầu trống và sẵn sàng để tùy chỉnh.

## Cách Thêm Thuộc tính Mở rộng
Định nghĩa một thuộc tính mở rộng sẽ lưu trữ dữ liệu số tùy chỉnh (ví dụ: giá trị sin) cho mỗi nhiệm vụ.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Ở đây chúng ta **thêm thuộc tính mở rộng** loại `Number` có tên “Sine” và liên kết nó với các nhiệm vụ.

## Thêm Thuộc tính Mở rộng vào Dự án
Đăng ký định nghĩa thuộc tính với dự án để mọi nhiệm vụ đều có thể tham chiếu tới nó.

```java
project.getExtendedAttributes().add(attr);
```

## Tạo Nhiệm vụ Mới
Thêm một nhiệm vụ đơn giản có tên “Task” dưới nhiệm vụ gốc của dự án.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Liên kết Thuộc tính Mở rộng với Nhiệm vụ
Gắn thuộc tính mở rộng đã định nghĩa trước đó vào nhiệm vụ vừa tạo.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Bây giờ nhiệm vụ chứa trường tùy chỉnh “Sine” mà bạn có thể sử dụng trong công thức hoặc các phép tính. Đây cũng là cách bạn **thêm dữ liệu trường tùy chỉnh cho nhiệm vụ** một cách lập trình.

## Tại sao nên dùng Các hàm Đánh giá?
Nhúng các hàm MS Project vào công thức Aspose.Tasks cho phép bạn:

- Thực hiện các phép tính ngay lập tức (ví dụ, `Sin([Start])`) mà không cần công cụ bên ngoài.  
- Giữ toàn bộ logic dự án trong một codebase duy nhất, dễ bảo trì.  
- Tạo báo cáo động phản ánh các thay đổi dữ liệu thời gian thực, giúp bạn **tự động tạo báo cáo dự án**.

## Các vấn đề Thường gặp và Giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Công thức trả về `NaN`** | Kiểm tra xem loại trường tùy chỉnh có khớp với kiểu số mong đợi hay không. |
| **Thuộc tính mở rộng không hiển thị** | Đảm bảo định nghĩa thuộc tính đã được thêm vào dự án **trước** khi tạo nhiệm vụ. |
| **Lỗi giấy phép** | Cài đặt giấy phép **Aspose.Tasks** tạm thời hoặc đầy đủ; chế độ dùng thử có thể giới hạn một số tính năng. |
| **Thiếu giấy phép tạm thời** | Lấy **giấy phép tạm thời** từ trang web Aspose. |

## Câu hỏi Thường gặp

**H: Aspose.Tasks for Java có thể xử lý các công thức MS Project phức tạp không?**  
Đ: Có, Aspose.Tasks for Java hỗ trợ đánh giá một loạt các hàm MS Project, cho phép thực hiện các phép tính phức tạp trong ứng dụng Java.

**H: Aspose.Tasks for Java có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
Đ: Có, Aspose.Tasks for Java hỗ trợ nhiều phiên bản tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.

**H: Tôi có thể thử Aspose.Tasks for Java trước khi mua không?**  
Đ: Có, bạn có thể tải phiên bản dùng thử miễn phí của Aspose.Tasks for Java từ trang web [tại đây](https://purchase.aspose.com/buy).

**H: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Tasks for Java?**  
Đ: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks [tại đây](https://forum.aspose.com/c/tasks/15).

**H: Có giấy phép tạm thời cho Aspose.Tasks for Java không?**  
Đ: Có, bạn có thể lấy giấy phép tạm thời để thử nghiệm từ trang web Aspose [tại đây](https://purchase.aspose.com/temporary-license/).

## Kết luận
Bằng cách thực hiện các bước trên, bạn đã học được cách **tạo project object**, **thêm thuộc tính mở rộng**, và tận dụng các hàm đánh giá để **tự động tạo báo cáo dự án**. Giờ đây bạn có thể mở rộng nền tảng này để xây dựng các phân tích dự án phong phú hơn, bảng điều khiển tùy chỉnh, hoặc công cụ lập lịch tự động — tất cả đều được hỗ trợ bởi Aspose.Tasks for Java.

---

**Cập nhật lần cuối:** 2026-02-13  
**Kiểm tra với:** Aspose.Tasks for Java 24.10  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}