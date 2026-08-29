---
date: 2026-08-29
description: Tìm hiểu cách thiết lập loại liên kết và quản lý phụ thuộc nhiệm vụ với
  Aspose.Tasks for Java trong hướng dẫn từng bước.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Cách thiết lập loại liên kết trong Aspose.Tasks for Java
og_description: Tìm hiểu cách thiết lập loại liên kết và quản lý phụ thuộc nhiệm vụ
  với Aspose.Tasks for Java. Hướng dẫn từng bước dành cho nhà phát triển.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Cách thiết lập loại liên kết trong Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Cách thiết lập loại liên kết trong Aspose.Tasks for Java
url: /vi/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đặt loại liên kết trong Aspose.Tasks cho Java

## Giới thiệu
Nếu bạn đang tự hỏi **cách đặt liên kết** giữa các nhiệm vụ khi bạn *quản lý phụ thuộc nhiệm vụ* trong một dự án, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách tạo một dự án mới, thêm các nhiệm vụ và xác định loại liên kết (Start‑to‑Start, Finish‑to‑Start, v.v.) bằng cách sử dụng Aspose.Tasks cho Java. Khi hoàn thành, bạn sẽ tự tin tùy chỉnh mối quan hệ giữa các nhiệm vụ để phù hợp với nhu cầu lập lịch thực tế và bạn sẽ thấy API xử lý các kế hoạch quy mô lớn lên tới 10.000 nhiệm vụ.

## Câu trả lời nhanh
- **Lớp nào đại diện cho một phụ thuộc?** `TaskLink` là đối tượng cốt lõi mô hình hoá một liên kết giữa hai nhiệm vụ.  
- **Enum nào xác định loại quan hệ?** `TaskLinkType` (ví dụ, `StartToStart`, `FinishToStart`).  
- **Tôi có thể đọc các loại liên kết hiện có không?** Có – lặp qua `Project.getTaskLinks()` và gọi `getLinkType()`.  
- **Tôi có cần giấy phép cho đoạn mã này không?** Giấy phép tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Điều này có tương thích với Java 8+ không?** Hoàn toàn – Aspose.Tasks hỗ trợ Java 8 đến Java 21, bao gồm 13 phiên bản chính.

## Liên kết nhiệm vụ là gì?
Một **liên kết nhiệm vụ** mô hình hoá một phụ thuộc giữa hai nhiệm vụ trong lịch trình dự án.  
Bạn có thể tạo, sửa đổi hoặc xóa một `TaskLink` để phản ánh mối quan hệ tiền nhiệm‑sau nhiệm, cho phép bộ lập lịch tính toán ngày bắt đầu và kết thúc một cách tự động.

## Tại sao nên sử dụng các loại liên kết Aspose.Tasks?
Aspose.Tasks hỗ trợ **hơn 30 định dạng nhập và xuất** và có thể xử lý các dự án chứa **lên tới 10.000 nhiệm vụ** mà không cần tải toàn bộ tệp vào bộ nhớ. Khả năng định lượng này đảm bảo hiệu suất nhanh ngay cả với các kế hoạch quy mô doanh nghiệp, và thư viện giữ nguyên tất cả các tính năng của Microsoft Project như trường tùy chỉnh và phân công tài nguyên.

## Yêu cầu trước
- **Môi trường phát triển Java** – JDK 8 hoặc mới hơn đã được cài đặt và cấu hình.  
- **Thư viện Aspose.Tasks** – Tải JAR mới nhất từ [download link](https://releases.aspose.com/tasks/java/).  
- **Thư mục tài liệu** – Tạo một thư mục trên máy của bạn để lưu các tệp dự án mẫu.

## Nhập các gói
Chúng tôi bắt đầu bằng việc nhập các lớp Aspose.Tasks cần thiết. Điều này chuẩn bị IDE để nhận diện các lời gọi API mà chúng tôi sẽ sử dụng sau.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Cách đặt loại liên kết trong Aspose.Tasks cho Java?
Tải một thể hiện `Project` mới, thêm hai nhiệm vụ, và sau đó tạo một `TaskLink` với `TaskLinkType` mong muốn. Mẫu hai bước này cho phép bạn định nghĩa bất kỳ một trong bốn loại phụ thuộc tiêu chuẩn trong một lời gọi duy nhất. `Project` đại diện cho toàn bộ tệp dự án và lịch trình của nó. `Task` là một mục công việc riêng lẻ trong dự án. `TaskLink` kết nối một nhiệm vụ tiền nhiệm với một nhiệm vụ hậu nhiệm. `TaskLinkType` là một enum xác định quan hệ (Start‑to‑Start, Finish‑to‑Start, v.v.).

### Bước 1: đặt loại liên kết
`TaskLink` đại diện cho một phụ thuộc giữa hai nhiệm vụ, trong khi `TaskLinkType` liệt kê các loại quan hệ có thể như `StartToStart`. Trong bước này, chúng tôi tạo một dự án mới, thêm hai nhiệm vụ và liên kết chúng bằng quan hệ **Start‑to‑Start**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Mẹo:** Bạn có thể thay thế `StartToStart` bằng `FinishToStart`, `StartToFinish`, hoặc `FinishToFinish` tùy thuộc vào phụ thuộc bạn cần **quản lý phụ thuộc nhiệm vụ**.

### Bước 2: lấy loại liên kết
`Project.getTaskLinks()` trả về một tập hợp các đối tượng `TaskLink` trong lịch trình. Bằng cách lặp qua tập hợp này, bạn có thể đọc `TaskLinkType` của mỗi liên kết và xác nhận rằng quan hệ đúng đã được lưu.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

Bảng điều khiển sẽ xuất các giá trị như `StartToStart`, `FinishToStart`, v.v., xác nhận loại liên kết bạn đã đặt trước đó.

## Các vấn đề thường gặp & giải pháp
- **NullPointerException khi thêm liên kết** – Đảm bảo cả nhiệm vụ tiền nhiệm và hậu nhiệm đều đã được thêm vào dự án trước khi tạo `TaskLink`.  
- **Loại liên kết không đúng sau khi lưu** – Luôn gọi `project.save("output.mpp")` (hoặc định dạng hỗ trợ khác) sau khi đặt loại liên kết để lưu các thay đổi.  
- **Không tìm thấy giấy phép** – Đặt tệp giấy phép Aspose.Tasks của bạn vào classpath của dự án và tải nó bằng `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Câu hỏi thường gặp

**Q: Aspose.Tasks có tương thích với các môi trường Java khác nhau không?**  
A: Có, Aspose.Tasks tích hợp với Java SE tiêu chuẩn, Java EE và bộ công cụ phát triển Android mà không cần phụ thuộc bổ sung.

**Q: Tôi có thể tùy chỉnh các loại liên kết dựa trên yêu cầu dự án của mình không?**  
A: Chắc chắn. Enum `TaskLinkType` cung cấp bốn loại tiêu chuẩn, và bạn có thể kết hợp chúng với giá trị trễ để mô hình hoá lịch trình phức tạp.

**Q: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks cho Java ở đâu?**  
A: Tham khảo [tài liệu Aspose.Tasks cho Java](https://reference.aspose.com/tasks/java/) để có hướng dẫn chi tiết, tham chiếu API và các mẫu mã.

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Tasks?**  
A: Truy cập [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để nhận giấy phép tạm thời cho mục đích thử nghiệm.

**Q: Tôi có thể nhận hỗ trợ cho các câu hỏi liên quan đến Aspose.Tasks ở đâu?**  
A: Tham gia cộng đồng Aspose.Tasks trên [diễn đàn hỗ trợ](https://forum.aspose.com/c/tasks/15) để được trợ giúp và thảo luận.

**Q: Tôi có thể thay đổi loại liên kết sau khi dự án đã được lưu không?**  
A: Có. Tải dự án, lấy `TaskLink`, gọi `setLinkType()` với giá trị enum mới, và lưu lại dự án.

**Q: Aspose.Tasks có hỗ trợ đọc các tệp Microsoft Project (MPP) không?**  
A: Có. Sử dụng `new Project("file.mpp")` để tải các tệp MPP và làm việc với các liên kết nhiệm vụ của chúng giống như ví dụ XML ở trên.

---

**Cập nhật lần cuối:** 2026-08-29  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo liên kết nhiệm vụ chéo dự án trong Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [Đặt ngày bắt đầu dự án và quản lý nhiệm vụ cha và con trong Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Tải tệp MPP Java - Quản lý thuộc tính dự án với Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}