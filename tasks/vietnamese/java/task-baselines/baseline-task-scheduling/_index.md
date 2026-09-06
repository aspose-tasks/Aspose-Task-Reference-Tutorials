---
date: 2026-08-29
description: Tìm hiểu cách đọc dữ liệu baseline và schedule tasks bằng Aspose.Tasks
  cho Java, để bạn có thể so sánh tiến độ dự kiến và thực tế một cách hiệu quả.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Lập lịch công việc Baseline trong Aspose.Tasks
og_description: Tìm hiểu cách đọc dữ liệu baseline và schedule tasks bằng Aspose.Tasks
  cho Java, cho phép so sánh chính xác tiến độ dự kiến và thực tế.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Cách đọc baseline và schedule tasks với Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Cách đọc baseline và schedule tasks với Aspose.Tasks
url: /vi/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc baseline và lên lịch các nhiệm vụ với Aspose.Tasks

Trong hướng dẫn này, bạn sẽ khám phá **cách đọc thông tin baseline** và lên lịch các nhiệm vụ một cách lập trình bằng Aspose.Tasks cho Java. Khi kết thúc tutorial, bạn sẽ có thể nắm bắt kế hoạch dự án gốc, so sánh với tiến độ thực tế và tạo báo cáo chênh lệch — tất cả mà không cần cài đặt Microsoft Project.

## Giới thiệu về baseline quản lý dự án

Quản lý **baseline quản lý dự án** là nền tảng của việc quản lý dự án hiệu quả. Nó cho phép bạn ghi lại kế hoạch ban đầu và sau đó so sánh **tiến độ dự kiến vs thực tế** để phát hiện sớm các sai lệch. Trong tutorial này, chúng ta sẽ đi qua cách lên lịch baseline nhiệm vụ bằng Aspose.Tasks cho Java, cung cấp cho bạn công cụ **quản lý baseline dự án** một cách tự tin và giữ dự án luôn trên đúng hướng.

## Câu trả lời nhanh
- **Baseline quản lý dự án đại diện cho gì?**  
  Nó ghi lại lịch trình, chi phí và phạm vi đã được phê duyệt khi dự án bắt đầu, cung cấp một tham chiếu để phân tích chênh lệch.  
- **Thư viện nào xử lý việc lên lịch baseline trong Java?**  
  Aspose.Tasks cho Java cung cấp API thuần Java hỗ trợ hơn 45 định dạng nhập và xuất và các dự án lên tới 100 000 nhiệm vụ.  
- **Tôi có cần giấy phép để chạy mã không?**  
  Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép thương mại là bắt buộc cho môi trường sản xuất.  
- **Các yêu cầu trước chính là gì?**  
  Java Development Kit (JDK) 11+ và thư viện Aspose.Tasks cho Java.  
- **Tôi có thể xem ngày baseline sau khi đã thiết lập không?**  
  Có — sử dụng đối tượng `TaskBaseline` để đọc giá trị start, finish và duration.

## Baseline quản lý dự án là gì?
Baseline quản lý dự án ghi lại lịch trình, ngân sách và phạm vi đã được phê duyệt khi bắt đầu thực hiện. Nó đóng vai trò là điểm tham chiếu để đo lường hiệu suất và xác định các sai lệch trong suốt vòng đời dự án. Baseline bao gồm ngày bắt đầu và kết thúc dự kiến, tổng chi phí và chi tiết phạm vi, cung cấp một bức tranh toàn diện để so sánh trong tương lai.

## Tại sao nên sử dụng Aspose.Tasks để lên lịch baseline?
Aspose.Tasks cung cấp API thuần Java hoạt động mà không cần cài đặt Microsoft Project. Nó hỗ trợ **hơn 45 định dạng nhập và xuất**, có thể xử lý các dự án với **tối đa 100 000 nhiệm vụ** trong chế độ tiết kiệm bộ nhớ, và cung cấp các phương thức tích hợp sẵn để đọc và ghi dữ liệu baseline — giúp việc báo cáo tự động và tích hợp trở nên đơn giản.

## Yêu cầu trước
- **Java Development Kit (JDK)** – cài đặt JDK 11 hoặc mới hơn. Bạn có thể tải xuống từ [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Thư viện Aspose.Tasks cho Java** – tải bản phát hành mới nhất từ [download page](https://releases.aspose.com/tasks/java/) và thêm file JAR vào classpath của dự án.

## Nhập các gói
Các lớp `Project`, `Task` và `TaskBaseline` nằm trong không gian tên `com.aspose.tasks`. Nhập chúng ở đầu file nguồn của bạn:

Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks, đại diện cho một tệp dự án duy nhất trong bộ nhớ. Nó cung cấp quyền truy cập vào các nhiệm vụ, tài nguyên và bộ sưu tập baseline.

## Cách đọc baseline?
Tải dự án, sau đó truy vấn bộ sưu tập `TaskBaseline` cho mỗi nhiệm vụ. Đối tượng `TaskBaseline` trả về ngày bắt đầu, kết thúc và thời lượng baseline đã được ghi lại khi bạn gọi `setBaseline`. Cách tiếp cận trực tiếp này cho phép bạn đọc giá trị baseline mà không cần phân tích XML hay file nhị phân.

## Bước 1: tạo một thể hiện dự án mới
Lớp `Project` đại diện cho toàn bộ tệp dự án trong bộ nhớ.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Bước 2: định nghĩa một nhiệm vụ và thiết lập baseline
`Task` đại diện cho một công việc cá nhân, và `setBaseline` ghi lại lịch trình hiện tại của nó dưới dạng baseline.
```java
Project project = new Project();
```

## Bước 3: truy cập thông tin baseline
`TaskBaseline` chứa các giá trị start, finish và duration đã lưu cho một baseline.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Bước 4: hiển thị thời lượng baseline
`Duration` đại diện cho độ dài thời gian của một nhiệm vụ hoặc baseline.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Bước 5: hiển thị ngày bắt đầu baseline
`Start` là ngày bắt đầu đã lên lịch của baseline.
```java
System.out.println(baseline.getDuration().toString());
```

## Bước 6: hiển thị ngày kết thúc baseline
`Finish` là ngày hoàn thành đã lên lịch của baseline.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Các vấn đề thường gặp và giải pháp
- **Baseline chưa được thiết lập:** Đảm bảo bạn gọi `project.setBaseline(BaselineType.Baseline)` **sau** khi đã thêm các nhiệm vụ; nếu không, bộ sưu tập baseline sẽ rỗng.  
- **Giá trị null:** Nếu `task.getBaselines()` trả về danh sách rỗng, hãy xác nhận rằng nhiệm vụ đã được thêm vào cấu trúc dự án trước khi thiết lập baseline.  
- **Định dạng ngày:** Các phương thức `getStart()` và `getFinish()` trả về đối tượng `java.util.Date`. Sử dụng `SimpleDateFormat` nếu bạn cần định dạng hiển thị tùy chỉnh.

## Câu hỏi thường gặp

**Q: Làm thế nào để tạo một thể hiện dự án mới trong Aspose.Tasks?**  
A: Khởi tạo lớp `Project` (`Project project = new Project();`). Điều này tạo một tệp dự án mới sẵn sàng cho các nhiệm vụ và baseline.

**Q: Sự khác biệt giữa `BaselineType.Baseline` và các loại baseline khác là gì?**  
A: `BaselineType.Baseline` đề cập đến baseline chính (Baseline 1). Aspose.Tasks cũng hỗ trợ Baseline 2‑10 cho các snapshot bổ sung.

**Q: Tôi có thể xuất dữ liệu baseline ra Excel hoặc CSV không?**  
A: Có, bạn có thể duyệt qua các đối tượng `TaskBaseline` và ghi các giá trị vào file CSV bằng I/O chuẩn của Java.

**Q: Việc thiết lập baseline có ảnh hưởng đến ngày của nhiệm vụ hiện có không?**  
A: Thiết lập baseline chỉ ghi lại các ngày hiện tại mà không thay đổi lịch trình hoạt động của nhiệm vụ. Bạn vẫn có thể điều chỉnh ngày bắt đầu/kết thúc sau khi baseline đã được thiết lập.

**Q: Có thể so sánh nhiều baseline một cách lập trình được không?**  
A: Chắc chắn. Lấy mỗi baseline qua `task.getBaselines().get(index)` và so sánh các thuộc tính `Start`, `Finish` và `Duration` của chúng.

---

**Cập nhật lần cuối:** 2026-08-29  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.12  
**Tác giả:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Hướng dẫn liên quan

- [Tạo danh sách nhiệm vụ Java – Baseline MS Project bằng Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Cách thiết lập thời lượng baseline trong Aspose.Tasks cho Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Tạo dự án MPP Java – Thay đổi tiến độ nhiệm vụ với Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}