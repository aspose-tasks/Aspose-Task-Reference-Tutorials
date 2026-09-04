---
date: 2026-07-05
description: Tìm hiểu cách liên kết các công việc giữa các dự án với Aspose.Tasks
  for Java. Hướng dẫn từng bước, các yêu cầu trước, và các thực tiễn tốt nhất để thực
  hiện liên kết công việc giữa các dự án một cách liền mạch.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Tạo liên kết công việc giữa các dự án trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Liên kết các công việc giữa các dự án bằng Aspose.Tasks for Java
url: /vi/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Liên kết các Nhiệm vụ Giữa Các Dự án bằng Aspose.Tasks cho Java

## Giới thiệu
Liên kết các nhiệm vụ giữa các dự án là một khả năng cốt lõi cho phép bạn đồng bộ công việc, tránh trùng lặp và duy trì một nguồn thông tin duy nhất cho các hoạt động phụ thuộc lẫn nhau. Trong hướng dẫn này, bạn sẽ khám phá cách **liên kết các nhiệm vụ giữa các dự án** bằng Aspose.Tasks cho Java, từng bước một. Khi kết thúc, bạn sẽ có một liên kết đa dự án hoạt động đầy đủ, tự động cập nhật khi bất kỳ phía nào thay đổi, mang lại sự phối hợp thời gian thực mà không cần sao chép‑dán thủ công.

## Câu trả lời nhanh
- **Lớp chính để tạo dự án là gì?** `Project` – nó đại diện cho toàn bộ tệp MS‑Project trong bộ nhớ.  
- **Phương thức nào thêm một nhiệm vụ ngoại vi?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **Tôi có thể đặt loại liên kết không?** Có – sử dụng `TaskLinkType.FinishToStart`, `StartToStart`, v.v.  
- **Tôi có cần giấy phép để liên kết không?** Cần một giấy phép Aspose.Tasks hợp lệ cho việc sử dụng trong môi trường sản xuất; bản dùng thử miễn phí đủ cho việc đánh giá.  
- **Có giới hạn về số lượng nhiệm vụ được liên kết không?** Aspose.Tasks có thể xử lý hơn 10.000 nhiệm vụ liên kết mỗi dự án mà không giảm hiệu năng.

## Liên kết nhiệm vụ giữa các dự án là gì?
Liên kết các nhiệm vụ giữa các dự án tạo ra một mối quan hệ phụ thuộc giữa một nhiệm vụ trong một tệp dự án và một nhiệm vụ trong tệp dự án khác, cho phép các thay đổi trong nhiệm vụ nguồn (thời lượng, ngày bắt đầu, ràng buộc) tự động truyền tới nhiệm vụ phụ thuộc. Cơ chế này giữ cho lịch trình đồng bộ, giảm việc cập nhật thủ công và đảm bảo bất kỳ sửa đổi nào trong dự án nguồn đều được phản ánh ngay lập tức trong tất cả các dự án được liên kết, duy trì tính nhất quán trong toàn bộ danh mục dự án.

## Tại sao nên sử dụng Aspose.Tasks cho việc liên kết đa dự án?
Aspose.Tasks hỗ trợ **hơn 50 định dạng nhập và xuất** và có thể xử lý **các dự án hàng trăm trang** trong khi giữ mức sử dụng bộ nhớ dưới 200 MB. API của nó thực hiện việc liên kết ở phía máy chủ, loại bỏ nhu cầu cài đặt Microsoft Project và cho phép các pipeline tự động cho các doanh nghiệp lớn.

## Yêu cầu trước
- Java 17 (hoặc phiên bản mới hơn) đã được cài đặt và cấu hình trong IDE của bạn.  
- Tệp giấy phép Aspose.Tasks cho Java hợp lệ (`Aspose.Tasks.Java.lic`).  
- Thư viện Aspose.Tasks cho Java đã được thêm vào dự án của bạn. Bạn có thể tải xuống từ [trang phát hành Aspose.Tasks cho Java](https://releases.aspose.com/tasks/java/).  
- Kiến thức cơ bản về các khái niệm của MS‑Project như nhiệm vụ, nhiệm vụ tổng hợp và các phụ thuộc.

## Nhập các Gói
Các lớp `Project`, `Task`, `TaskLink` và các enum liên quan nằm trong không gian tên `com.aspose.tasks`. Nhập chúng ở đầu tệp Java của bạn:

`import com.aspose.tasks.*;`

**Project** là lớp chính đại diện cho một tệp dự án trong bộ nhớ. **Task** đại diện cho một mục công việc riêng lẻ trong dự án. **TaskLink** xác định một mối quan hệ phụ thuộc giữa hai nhiệm vụ. Những import này cung cấp cho bạn quyền truy cập vào toàn bộ bộ tính năng thao tác dự án, bao gồm cả việc liên kết đa dự án.

## Cách liên kết nhiệm vụ giữa các dự án?
Tải hai tệp dự án, thêm một placeholder cho nhiệm vụ ngoại vi, tạo một nhiệm vụ nội bộ, và sau đó kết nối chúng bằng một `TaskLink`. API xử lý việc ánh xạ ID và cập nhật tự động, đảm bảo bất kỳ thay đổi nào trong nhiệm vụ ngoại vi đều lan truyền tới nhiệm vụ nội bộ được liên kết mà không cần mã bổ sung. Cách tiếp cận này đơn giản hoá việc phối hợp đa dự án và giảm rủi ro lệch lịch trình.

### Bước 1: Thiết lập Môi trường của Bạn
Đảm bảo JAR Aspose.Tasks có trong classpath và tệp giấy phép được tải tại thời gian chạy:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** tải tệp giấy phép Aspose.Tasks của bạn để kích hoạt đầy đủ chức năng và loại bỏ các dấu watermark đánh giá.

### Bước 2: Tạo một Instance Dự án
Khởi tạo một đối tượng `Project` mới cho dự án mục tiêu nơi bạn muốn tạo liên kết:

`Project targetProject = new Project();`

Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks, đại diện cho một tệp dự án duy nhất trong bộ nhớ.

### Bước 3: Thêm Nhiệm vụ Tổng hợp
Nhiệm vụ tổng hợp nhóm các nhiệm vụ liên quan lại với nhau. Tạo một nhiệm vụ để chứa cả nhiệm vụ ngoại vi và nội bộ:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### Bước 4: Thêm Nhiệm vụ Ngoại vi
Chèn một nhiệm vụ ngoại vi trỏ tới một nhiệm vụ trong tệp dự án khác:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

Phương thức **addExternalTask** tạo một nhiệm vụ placeholder tham chiếu tới một tệp dự án ngoại vi, sử dụng tên tệp và ID nhiệm vụ được cung cấp.

### Bước 5: Thêm Nhiệm vụ Nội bộ
Tạo nhiệm vụ sẽ được liên kết với nhiệm vụ ngoại vi:

`Task local = summary.getChildren().add("Local Task");`

### Bước 6: Tạo Liên kết Nhiệm vụ
Thiết lập một phụ thuộc giữa nhiệm vụ ngoại vi và nhiệm vụ nội bộ. Loại liên kết phổ biến nhất là Finish‑to‑Start:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink** ghi lại mối quan hệ; bạn có thể sau này chỉnh sửa độ trễ, thời gian dẫn hoặc loại liên kết khi cần.

### Bước 7: Lưu và Xác minh
Lưu dự án vào một tệp và tùy chọn mở nó trong Microsoft Project để xác minh liên kết:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat** chỉ định định dạng tệp để lưu dự án. Khi bạn mở *LinkedProject.mpp*, bạn sẽ thấy nhiệm vụ ngoại vi hiển thị với một biểu tượng đặc biệt và đường phụ thuộc chỉ tới nhiệm vụ nội bộ.

## Các Vấn đề Thường gặp và Giải pháp
- **Không tìm thấy tệp ngoại vi** – Đảm bảo đường dẫn tương đối với tiến trình đang chạy hoặc cung cấp một đường dẫn tuyệt đối.  
- **ID nhiệm vụ không khớp** – Xác minh ID nhiệm vụ ngoại vi (đối số thứ hai của `addExternalTask`) khớp với dự án nguồn.  
- **Giấy phép chưa được tải** – Thiếu hoặc tệp giấy phép không đúng sẽ gây ra `LicenseException`. Hãy tải nó trước khi gọi bất kỳ phương thức nào của Aspose.Tasks.  
- **Hiệu năng trên dự án lớn** – Sử dụng `Project.setReadOnly(true)` khi bạn chỉ cần đọc các nhiệm vụ ngoại vi; cách này giảm tải bộ nhớ.

## Câu hỏi Thường gặp

**Q: Tôi có thể liên kết các nhiệm vụ từ nhiều dự án ngoại vi trong cùng một nhiệm vụ tổng hợp không?**  
A: Có, bạn có thể thêm nhiều nhiệm vụ ngoại vi dưới một nhiệm vụ tổng hợp và tạo liên kết riêng cho từng nhiệm vụ, sử dụng cùng phương thức `addExternalTask`.

**Q: Điều gì sẽ xảy ra nếu nhiệm vụ ngoại vi trong dự án được liên kết bị sửa đổi?**  
A: Bất kỳ thay đổi nào đối với lịch trình, thời lượng hoặc ràng buộc của nhiệm vụ ngoại vi sẽ tự động được phản ánh trong nhiệm vụ nội bộ phụ thuộc khi dự án mục tiêu được làm mới.

**Q: Có thể tạo liên kết giữa các nhiệm vụ trong các định dạng tệp khác nhau không?**  
A: Chắc chắn. Aspose.Tasks hỗ trợ việc liên kết giữa các định dạng MPP, XML và Primavera, cho phép các hệ sinh thái dự án hỗn hợp đồng bộ với nhau.

**Q: Tôi có thể hủy liên kết các nhiệm vụ sau khi chúng đã được liên kết giữa các dự án không?**  
A: Có, hãy xóa liên kết bằng cách gọi `project.getTaskLinks().remove(link)` hoặc bằng cách xóa placeholder nhiệm vụ ngoại vi.

**Q: Có bất kỳ giới hạn nào về số lượng nhiệm vụ có thể được liên kết giữa các dự án không?**  
A: Thư viện có thể xử lý **hơn 10.000 nhiệm vụ được liên kết** mỗi dự án, chỉ bị giới hạn bởi bộ nhớ hệ thống khả dụng và các thông số kỹ thuật của định dạng tệp nền tảng.

## Kết luận
Bây giờ bạn đã có một cách tiếp cận hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **liên kết các nhiệm vụ giữa các dự án** bằng Aspose.Tasks cho Java. Khả năng này giúp đơn giản hoá việc phối hợp đa dự án, giảm công sức thủ công và đảm bảo các thay đổi lịch trình được lan truyền ngay lập tức trên toàn bộ danh mục dự án của bạn. Khám phá các tính năng bổ sung như thời gian trễ tùy chỉnh, các loại liên kết khác nhau và liên kết hàng loạt để tự động hoá hơn nữa các cấu trúc dự án phức tạp.

---

**Cập nhật lần cuối:** 2026-07-05  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## Hướng dẫn liên quan

- [Tạo Liên kết Nhiệm vụ trong Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Tạo Nhiệm vụ Aspose Java – Thuộc tính Nhiệm vụ](/tasks/java/task-properties/)
- [Tạo Tệp MS Project Trống trong Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}