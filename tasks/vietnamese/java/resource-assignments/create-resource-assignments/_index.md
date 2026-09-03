---
date: 2026-05-20
description: Tìm hiểu cách thêm tài nguyên vào dự án và tạo phân công tài nguyên bằng
  Aspose.Tasks cho Java, một thư viện quản lý dự án Java mạnh mẽ.
keywords:
- add resource to project
- how to add task
- assign resource to task
- java project management library
linktitle: Tạo Phân Công Tài Nguyên trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  headline: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  name: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  steps:
  - name: Create a Project Object
    text: 'The `Project` class is the top‑level container that represents a single
      project file in memory. Instantiate a `Project` object, which represents the
      project file you''re working with:'
  - name: Add a Task to the Project
    text: 'The `Task` class models an individual work item within the schedule. Add
      a task to the project using the `addChild` method of the root task:'
  - name: Add a Resource to the Project
    text: 'The `Resource` class defines a person, equipment, or material that can
      be assigned to tasks. Add a resource to the project using the `add` method of
      the `Resources` collection:'
  - name: Create a Resource Assignment
    text: 'The `ResourceAssignment` class links a `Task` and a `Resource` and stores
      allocation details such as work hours and cost. Create a resource assignment
      for the task and resource using the `add` method of the `ResourceAssignments`
      collection:'
  type: HowTo
- questions:
  - answer: Yes, you can update assignment properties such as `Work`, `Cost`, and
      `Start` using the setters provided by the `ResourceAssignment` class.
    question: Can I modify resource assignments after creation?
  - answer: Absolutely, Aspose.Tasks for Java supports MPP, XML, CSV, and many other
      formats, allowing seamless import and export.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Yes, a valid commercial license is required. A free evaluation license
      is available for testing purposes.
    question: Does Aspose.Tasks for Java require a license for commercial use?
  - answer: Yes, the library is fully thread‑safe and can be integrated into servlet‑based
      or Spring‑Boot web services.
    question: Can I use Aspose.Tasks for Java in my web applications?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for technical assistance and community discussions.
    question: Where can I find additional support for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách Thêm Tài Nguyên Vào Dự Án và Tạo Phân Công Tài Nguyên trong Aspose.Tasks
url: /vi/java/resource-assignments/create-resource-assignments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm tài nguyên vào dự án – Tạo phân công tài nguyên trong Aspose.Tasks

## Giới thiệu
Trong quản lý dự án hiện đại, **add resource to project** là nền tảng của việc lập lịch và kiểm soát chi phí hiệu quả. Aspose.Tasks for Java cung cấp cho bạn một cách lập trình, hiệu suất cao để quản lý tài nguyên, nhiệm vụ và phân công mà không rời khỏi IDE của bạn. Trong hướng dẫn này, bạn sẽ thấy chính xác cách thêm tài nguyên vào dự án, gắn nó vào một nhiệm vụ, và tinh chỉnh chi tiết phân công — tất cả bằng mã Java sạch sẽ, sẵn sàng cho môi trường sản xuất.

## Câu trả lời nhanh
- **Bước đầu tiên là gì?** Tạo một thể hiện `Project` đại diện cho tệp .mpp hoặc .xml của bạn.  
- **Làm sao để thêm một nhiệm vụ?** Sử dụng phương thức `addChild` của nhiệm vụ gốc và đặt tên cho nhiệm vụ.  
- **Làm sao để thêm một tài nguyên?** Gọi `project.getResources().add` với một đối tượng `Resource`.  
- **Làm sao để liên kết một tài nguyên với một nhiệm vụ?** Sử dụng `project.getResourceAssignments().add(task, resource)`.  
- **Tôi có cần giấy phép không?** Có – cần một giấy phép Aspose.Tasks for Java hợp lệ để sử dụng trong môi trường sản xuất.

## “add resource to project” là gì?
**Add resource to project** có nghĩa là tạo một đối tượng `Resource` trong tệp dự án và liên kết nó với một hoặc nhiều nhiệm vụ để công việc, chi phí và dữ liệu lịch tự động được tính toán. Hoạt động này là xương sống của bất kỳ ứng dụng nào dựa trên lịch trình.

## Tại sao chọn Aspose.Tasks cho Java?
Aspose.Tasks cho Java hỗ trợ **hơn 30 định dạng đầu vào và đầu ra** (bao gồm MPP, XML và CSV) và có thể xử lý các dự án với **hơn 10.000 nhiệm vụ** trong khi giữ mức sử dụng bộ nhớ dưới 200 MB. Thư viện chạy trên Java 8‑17, không yêu cầu cài đặt Microsoft Project, và cung cấp các API thread‑safe cho tự động hoá phía máy chủ.

## Yêu cầu
Trước khi chúng ta bắt đầu tạo các phân công tài nguyên, hãy chắc chắn rằng bạn có những thứ sau:

### Môi trường phát triển Java
Đảm bảo bạn đã cài đặt Java Development Kit (JDK) trên hệ thống của mình. Bạn có thể tải và cài đặt JDK từ [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Thư viện Aspose.Tasks cho Java
Tải thư viện Aspose.Tasks cho Java từ [download page](https://releases.aspose.com/tasks/java/). Thực hiện theo hướng dẫn cài đặt để thiết lập thư viện trong dự án Java của bạn.

## Cách thêm tài nguyên vào dự án?
Tải dự án của bạn, tạo một nhiệm vụ, thêm một tài nguyên, và cuối cùng liên kết chúng lại với nhau – tất cả trong bốn bước ngắn gọn. Các đoạn mã dưới đây (placeholder) hiển thị các lời gọi API chính xác; bạn chỉ cần thay thế văn bản placeholder bằng các đường dẫn tệp và tên của mình.

### Bước 1: Tạo đối tượng Project
Lớp `Project` là container cấp cao nhất đại diện cho một tệp dự án duy nhất trong bộ nhớ.  
Khởi tạo một đối tượng `Project`, đại diện cho tệp dự án mà bạn đang làm việc với:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

### Bước 2: Thêm một nhiệm vụ vào dự án
Lớp `Task` mô hình hoá một công việc cá nhân trong lịch trình.  
Thêm một nhiệm vụ vào dự án bằng cách sử dụng phương thức `addChild` của nhiệm vụ gốc:
```java
Project project = new Project();
```

### Bước 3: Thêm một tài nguyên vào dự án
Lớp `Resource` định nghĩa một người, thiết bị, hoặc vật liệu có thể được gán cho các nhiệm vụ.  
Thêm một tài nguyên vào dự án bằng cách sử dụng phương thức `add` của bộ sưu tập `Resources`:
```java
Task task = project.getRootTask().getChildren().add("Task");
```

### Bước 4: Tạo một phân công tài nguyên
Lớp `ResourceAssignment` liên kết một `Task` và một `Resource` và lưu trữ chi tiết phân bổ như giờ làm việc và chi phí.  
Tạo một phân công tài nguyên cho nhiệm vụ và tài nguyên bằng cách sử dụng phương thức `add` của bộ sưu tập `ResourceAssignments`:
```java
Resource rsc = project.getResources().add("Rsc");
```

## Các vấn đề thường gặp và giải pháp
- **NullPointerException khi `addChild`** – Đảm bảo bạn gọi `project.getRootTask()` trước khi thêm các phần tử con.  
- **Không tìm thấy giấy phép** – Đặt tệp `Aspose.Tasks.lic` của bạn vào classpath hoặc thiết lập giấy phép bằng cách lập trình với `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Dự án lớn chậm** – Sử dụng `project.setReadOnly(true)` khi bạn chỉ cần đọc dữ liệu; điều này giảm tải bộ nhớ.

## Câu hỏi thường gặp

**Q: Tôi có thể sửa đổi các phân công tài nguyên sau khi tạo không?**  
A: Có, bạn có thể cập nhật các thuộc tính phân công như `Work`, `Cost`, và `Start` bằng cách sử dụng các setter được cung cấp bởi lớp `ResourceAssignment`.

**Q: Aspose.Tasks cho Java có tương thích với các định dạng tệp dự án khác nhau không?**  
A: Chắc chắn, Aspose.Tasks cho Java hỗ trợ MPP, XML, CSV và nhiều định dạng khác, cho phép nhập và xuất một cách liền mạch.

**Q: Aspose.Tasks cho Java có yêu cầu giấy phép cho việc sử dụng thương mại không?**  
A: Có, cần một giấy phép thương mại hợp lệ. Một giấy phép đánh giá miễn phí có sẵn cho mục đích thử nghiệm.

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java trong các ứng dụng web của mình không?**  
A: Có, thư viện hoàn toàn thread‑safe và có thể được tích hợp vào các dịch vụ web dựa trên servlet hoặc Spring‑Boot.

**Q: Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Tasks cho Java ở đâu?**  
A: Bạn có thể truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để được hỗ trợ kỹ thuật và thảo luận cộng đồng.

---

**Cập nhật lần cuối:** 2026-05-20  
**Kiểm thử với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose  

```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách tạo tài nguyên – Quản lý tài nguyên với Aspose.Tasks cho Java](/tasks/java/resource-management/)
- [Cách thêm ghi chú vào phân công tài nguyên trong Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Cách thêm tài nguyên vào dự án và xử lý thuộc tính độ trễ cân bằng trong Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}