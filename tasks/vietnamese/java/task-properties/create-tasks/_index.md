---
date: 2026-09-25
description: Tìm hiểu cách tạo lịch trình dự án trong Java bằng Aspose.Tasks. Hướng
  dẫn này chỉ cho bạn cách thêm summary tasks, quản lý project hierarchy và thiết
  lập document directory một cách hiệu quả.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Tạo Tasks trong Aspose.Tasks
og_description: Tìm hiểu cách tạo lịch trình dự án trong Java bằng Aspose.Tasks. Thực
  hiện các hướng dẫn step‑by‑step để thêm summary tasks, quản lý hierarchy và thiết
  lập document directory.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Cách tạo lịch trình dự án với Aspose.Tasks cho Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Cách tạo lịch trình dự án với Aspose.Tasks cho Java
url: /vi/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo lịch trình dự án với Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **tạo lịch trình dự án** trong một ứng dụng Java bằng Aspose.Tasks. Dù bạn đang xây dựng một danh sách công việc đơn giản hay một công cụ lập kế hoạch doanh nghiệp phức tạp, các bước dưới đây sẽ hướng dẫn bạn thêm các nhiệm vụ tổng hợp, quản lý cấu trúc dự án và thiết lập thư mục tài liệu — tất cả đều kèm theo các đoạn mã mẫu có thể chạy ngay. Khi hoàn thành, bạn sẽ có một lịch trình được cấu trúc đầy đủ, sẵn sàng cho việc thao tác hoặc xuất ra.

## Câu trả lời nhanh
- **Aspose.Tasks quản lý gì?** Nó xử lý cấu trúc nhiệm vụ, nguồn lực, lịch làm việc và các định dạng tệp dự án (MS‑Project, Primavera, v.v.).  
- **Có cần giấy phép cho việc phát triển không?** Giấy phép tạm thời miễn phí đủ cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 và các phiên bản mới hơn đều được hỗ trợ đầy đủ.  
- **Có thể thêm trường tùy chỉnh vào nhiệm vụ không?** Có, bạn có thể mở rộng nhiệm vụ bằng các trường do người dùng định nghĩa qua API.  
- **Có hỗ trợ biểu đồ Gantt tích hợp không?** Aspose.Tasks có thể xuất ra PDF/HTML bao gồm hình ảnh Gantt.

## Lịch trình dự án trong Aspose.Tasks là gì?
Lịch trình dự án là tập hợp đầy đủ các nhiệm vụ, phụ thuộc và thời gian xác định cách công việc sẽ được thực hiện. Aspose.Tasks lưu trữ thông tin này trong một đối tượng `Project` mà bạn có thể đọc, sửa đổi và lưu dưới nhiều định dạng khác nhau. Nó bao gồm ngày bắt đầu và kết thúc, ràng buộc, và phân công nguồn lực, cho phép lập kế hoạch và báo cáo toàn diện.

## Tại sao nên dùng Aspose.Tasks cho quản lý dự án Java?
Aspose.Tasks hỗ trợ **hơn 30 định dạng nhập và xuất** và có thể xử lý dự án với **tối đa 10.000 nhiệm vụ** mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại hiệu năng cao cho các kịch bản quản lý dự án quy mô lớn bằng Java.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn đã chuẩn bị các yêu cầu sau:
- **Java Development Kit (JDK)** – JDK 8 hoặc mới hơn đã được cài đặt trên máy của bạn.  
- **Thư viện Aspose.Tasks cho Java** – Tải và cài đặt thư viện từ [tải Aspose.Tasks cho Java](https://releases.aspose.com/tasks/java/).  
- **Môi trường Phát triển Tích hợp (IDE)** – Sử dụng Eclipse, IntelliJ IDEA, hoặc bất kỳ IDE nào hỗ trợ Java mà bạn ưa thích.

## Nhập các gói
`Project`, `Task` và các lớp liên quan nằm trong không gian tên `com.aspose.tasks`. Nhập chúng ở đầu tệp Java của bạn:

Lớp `Project` đại diện cho một lịch trình dự án hoàn chỉnh và cung cấp các phương thức để thao tác nhiệm vụ và nguồn lực.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Lớp `Project` là điểm khởi đầu cho mọi thao tác trên tệp dự án.

## Cách tạo lịch trình dự án với Aspose.Tasks?

Tải một thể hiện `Project` mới, thiết lập thư mục tài liệu, và bắt đầu thêm các nhiệm vụ. Đoạn văn trả lời trực tiếp này giải thích luồng chính: bạn tạo một `Project`, cấu hình `RootFolder` (thư mục tài liệu), sau đó thêm một nhiệm vụ tổng hợp và các nhiệm vụ con. Tất cả các thay đổi được giữ trong bộ nhớ cho đến khi bạn gọi `save` để ghi lịch trình ra tệp.

### Bước 1: thiết lập thư mục tài liệu
Xác định nơi tệp dự án sẽ được ghi. Thiết lập thư mục từ sớm giúp mọi thao tác lưu sau này sử dụng cùng một đường dẫn nhất quán.

Thuộc tính `RootFolder` chỉ định thư mục cơ sở nơi các tệp dự án được đọc hoặc ghi.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Bước 2: tạo một dự án mới
Khởi tạo một đối tượng `Project` mới sẽ chứa lịch trình của bạn. Bạn cũng có thể truyền đường dẫn tệp đã tồn tại để tải một lịch trình hiện có và chỉnh sửa.

Hàm khởi tạo `Project` tạo một lịch trình trống, sẵn sàng cho việc thêm nhiệm vụ.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Bước 3: thêm một nhiệm vụ tổng hợp
Nhiệm vụ tổng hợp nhóm các nhiệm vụ con liên quan và xuất hiện dưới dạng nút có thể thu gọn trong biểu đồ Gantt. Sử dụng lớp `Task` và đặt `IsSummary` thành `true`.

Phương thức `addTask` tạo một nhiệm vụ mới dưới một parent xác định và trả về ID của nó.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Bước 4: thêm một nhiệm vụ con
Nhiệm vụ con kế thừa ngày bắt đầu/kết thúc từ nhiệm vụ tổng hợp cha trừ khi bạn ghi đè chúng. Thêm một nhiệm vụ con chỉ cần gọi lại `addTask` và chỉ định ID của parent.

Gọi `addTask` với ID của parent sẽ thêm một nhiệm vụ con dưới nhiệm vụ tổng hợp đó.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Tiếp tục thêm bao nhiêu nhiệm vụ và nhiệm vụ con tùy nhu cầu dự án của bạn. Mỗi bước góp phần xây dựng một cấu trúc dự án có tổ chức, có thể xuất ra MS‑Project, PDF hoặc các định dạng hỗ trợ khác.

## Các vấn đề thường gặp và giải pháp
- **Vấn đề:** “Không tìm thấy thư mục tài liệu.”  
  **Giải pháp:** Kiểm tra đường dẫn bạn gán cho `RootFolder` có tồn tại trên hệ thống và quy trình Java của bạn có quyền ghi không.
- **Vấn đề:** Nhiệm vụ con không hiển thị dưới nhiệm vụ tổng hợp.  
  **Giải pháp:** Đảm bảo bạn truyền đúng ID của nhiệm vụ cha khi gọi `addTask`. API yêu cầu ID của parent làm đối số thứ hai.
- **Vấn đề:** Dự án lớn gây ra OutOfMemoryError.  
  **Giải pháp:** Aspose.Tasks xử lý nhiệm vụ theo chế độ streaming; tăng kích thước heap JVM (`-Xmx2g`) hoặc chia lịch trình thành nhiều tệp.

## Câu hỏi thường gặp
**H: Aspose.Tasks có phù hợp với các dự án quy mô nhỏ không?**  
Đ: Hoàn toàn. Thư viện mở rộng từ danh sách nhiệm vụ đơn lẻ đến lịch trình doanh nghiệp với hàng ngàn nhiệm vụ.

**H: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks cho Java ở đâu?**  
Đ: Tham khảo tài liệu [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**H: Làm sao để lấy giấy phép tạm thời cho Aspose.Tasks?**  
Đ: Truy cập [trang yêu cầu giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để nhận giấy phép có thời hạn, phù hợp cho phát triển và thử nghiệm.

**H: Tôi có thể tùy chỉnh thuộc tính nhiệm vụ bằng Aspose.Tasks không?**  
Đ: Có, bạn có thể mở rộng nhiệm vụ với các trường tùy chỉnh, phân công nguồn lực và chỉnh sửa lịch làm việc thông qua lập trình.

**H: Có cộng đồng hỗ trợ cho người dùng Aspose.Tasks không?**  
Đ: Chắc chắn! Tham gia cộng đồng Aspose.Tasks tại [diễn đàn hỗ trợ](https://forum.aspose.com/c/tasks/15).

---

**Cập nhật lần cuối:** 2026-09-25  
**Kiểm tra với:** Aspose.Tasks 24.12 cho Java  
**Tác giả:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Các hướng dẫn liên quan

- [Đặt ngày bắt đầu dự án trong MS Project bằng Aspose.Tasks cho Java](/tasks/java/project-properties/write-project-info/)
- [Tạo liên kết phụ thuộc nhiệm vụ trong Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Cách thêm nguồn lực vào dự án và tạo phân công nguồn lực trong Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}