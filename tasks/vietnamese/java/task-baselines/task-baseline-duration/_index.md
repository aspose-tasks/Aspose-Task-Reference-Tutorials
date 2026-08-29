---
date: 2026-08-29
description: Tìm hiểu cách thiết lập baseline duration và theo dõi project progress
  bằng Aspose.Tasks for Java. Hướng dẫn chi tiết này giúp bạn quản lý task baselines
  một cách hiệu quả.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Cách thiết lập Baseline Duration trong Aspose.Tasks for Java
og_description: Tìm hiểu cách thiết lập baseline duration và theo dõi project progress
  bằng Aspose.Tasks for Java. Tham khảo hướng dẫn chi tiết này để quản lý task baselines
  một cách hiệu quả.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Cách thiết lập baseline duration để theo dõi project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Cách thiết lập baseline duration để theo dõi project progress
url: /vi/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đặt thời lượng baseline để theo dõi tiến độ dự án

## Giới thiệu
Tracking project progress starts with a solid baseline. In this tutorial you’ll discover **how to set baseline duration** for tasks in Microsoft Project files using the Aspose.Tasks library for Java, and understand why establishing a baseline early helps you monitor schedule drift, cost variance, and resource overallocation throughout the life of the project.

## Câu trả lời nhanh
- **“set baseline” có nghĩa là gì?** Nó ghi lại thời gian bắt đầu, kết thúc và thời lượng gốc của một nhiệm vụ để bạn có thể so sánh các thay đổi trong tương lai.  
- **Lớp Aspose.Tasks nào tạo dự án?** Lớp `Project` – bạn cũng sẽ học cách **tạo một thể hiện dự án** một cách đúng đắn.  
- **Bạn có cần giấy phép để chạy mã không?** Giấy phép đánh giá miễn phí hoạt động cho việc thử nghiệm; giấy phép thương mại là bắt buộc cho môi trường sản xuất.  
- **Tôi có thể truy xuất các baseline tạm thời không?** Có, Aspose.Tasks cho phép bạn truy vấn các baseline tạm thời và chi phí cố định của chúng.  
- **Phiên bản Java nào được yêu cầu?** Java 8 hoặc mới hơn được khuyến nghị.  
- **Điều này giúp tôi theo dõi tiến độ dự án như thế nào?** Khi baseline đã được đặt, bạn có thể ngay lập tức so sánh ngày thực tế với kế hoạch gốc bằng các tính năng báo cáo tích hợp.

## Baseline nhiệm vụ là gì và tại sao cần đặt nó?
A task baseline captures the planned schedule (start date, finish date, and duration) at a specific point in time. By setting a baseline you create a reference point that makes it easy to spot schedule drift, cost overruns, and resource overallocation as the project evolves.

## Tại sao nên sử dụng Aspose.Tasks để quản lý baseline?
Aspose.Tasks provides **full .mpp compatibility** – you can read and write native Microsoft Project files without needing Microsoft Office installed. The API gives you programmatic access to **50+ input and output formats**, supports **interim baselines 1‑10**, and can handle **multi‑hundred‑page projects** without loading the entire file into memory, which is essential for high‑performance batch processing.

## Yêu cầu trước
1. **Java Development Environment** – JDK 8+ installed and configured.  
2. **Aspose.Tasks for Java** – download the library from the [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).  
3. **IDE or build tool** – Maven, Gradle, or any IDE you prefer.

## Nhập các gói
The following imports bring in the core Aspose.Tasks classes needed to work with projects, tasks, baselines, and time‑phased data.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Bước 1: tạo một thể hiện dự án
The `Project` class represents a Microsoft Project file in memory and is the entry point for all operations.

```java
Project project = new Project();
```

## Bước 2: tạo baseline cho nhiệm vụ
A `TaskBaseline` stores the planned start, finish, and duration for a specific task.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Bước 3: hiển thị thông tin baseline của nhiệm vụ
The `getBaselines()` method returns the collection of baselines associated with a task.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Bước 4: kiểm tra baseline tạm thời và chi phí cố định
`BaselineType` enumerates the primary and interim baselines (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Bước 5: in dữ liệu thời gian phân đoạn
`TimephasedData` represents a piece of schedule information for a specific time interval.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

By following these steps, you can **set baseline duration** for any task and retrieve detailed baseline information using Aspose.Tasks for Java, giving you a reliable way to **track project progress** throughout the project lifecycle.

## Các vấn đề thường gặp và giải pháp
- **Baseline không hiển thị trong MS Project:** Đảm bảo bạn đã gọi `project.setBaseline(BaselineType.Baseline)` **sau** khi thêm nhiệm vụ.  
- **NullPointerException khi gọi `getBaselines()`:** Xác nhận rằng nhiệm vụ đã được thêm vào dự án trước khi đặt baseline.  
- **Không khớp đơn vị thời gian:** Sử dụng `TimeUnitType` để định dạng thời lượng đúng, đặc biệt khi làm việc với lịch tùy chỉnh.

## Câu hỏi thường gặp
### Baseline nhiệm vụ trong MS Project là gì?
A task baseline in MS Project is a snapshot of the initial planned schedule for a task, including its start date, finish date, and duration.

### Tại sao quản lý baseline nhiệm vụ lại quan trọng?
Managing task baselines helps in comparing the planned schedule with the actual progress of the project, facilitating better tracking and decision‑making.

### Tôi có thể sửa đổi baseline nhiệm vụ sau khi đã đặt không?
Yes, you can modify task baselines in MS Project to reflect changes in the project plan. However, it’s essential to document any deviations from the original baseline.

### Aspose.Tasks có hỗ trợ các chức năng quản lý dự án khác không?
Yes, Aspose.Tasks offers a wide range of features for project management, including task scheduling, resource allocation, and Gantt chart generation.

### Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?
You can find support for Aspose.Tasks on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), where you can ask questions and interact with other users.

## Các câu hỏi thường gặp bổ sung
**Q: Tôi có cần gọi `setBaseline` cho mỗi nhiệm vụ riêng lẻ không?**  
A: Không. Gọi `project.setBaseline(BaselineType.Baseline)` ghi lại baseline cho tất cả các nhiệm vụ trong dự án cùng một lúc.

**Q: Làm thế nào để đặt baseline tạm thời cho một nhiệm vụ cụ thể?**  
A: Sử dụng `project.setBaseline(BaselineType.Baseline1)` (hoặc Baseline2‑Baseline10) sau khi cập nhật lịch trình của nhiệm vụ.

**Q: Có thể xuất dữ liệu baseline ra CSV không?**  
A: Có. Duyệt qua `task.getBaselines()` và ghi các trường mong muốn vào tệp CSV bằng I/O chuẩn của Java.

**Q: Tôi có thể đọc tệp .mpp hiện có đã chứa baseline không?**  
A: Chắc chắn. Tải tệp bằng `new Project("myproject.mpp")` và sau đó truy cập baseline của mỗi nhiệm vụ như đã trình bày ở trên.

**Q: Aspose.Tasks có xử lý các tệp đa dự án không?**  
A: Aspose.Tasks làm việc với các tệp .mpp đơn dự án. Đối với các kịch bản đa dự án, hãy kết hợp các dự án bằng lập trình.

---

**Cập nhật lần cuối:** 2026-08-29  
**Được kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo danh sách nhiệm vụ Java – Baseline MS Project bằng Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Tạo dự án MPP Java – Thay đổi tiến độ nhiệm vụ với Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Baseline quản lý dự án – Lập lịch nhiệm vụ với Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}