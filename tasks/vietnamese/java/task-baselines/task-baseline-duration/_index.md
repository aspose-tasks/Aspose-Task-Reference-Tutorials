---
date: 2026-01-23
description: Tìm hiểu cách đặt thời gian baseline và tạo thể hiện dự án bằng Aspose.Tasks
  cho Java. Hướng dẫn từng bước này giúp bạn quản lý baseline của nhiệm vụ một cách
  hiệu quả.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Cách thiết lập thời lượng baseline trong Aspose.Tasks cho Java
url: /vi/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Thời Lượng Baseline trong Aspose.Tasks cho Java

## Giới thiệu
Việc đặt baseline là một bước cơ bản để theo dõi tiến độ dự án so với kế hoạch gốc. Trong hướng dẫn này, bạn sẽ học **cách đặt baseline** thời lượng cho các công việc trong Microsoft Project bằng thư viện Aspose.Tasks cho Java, và hiểu tại sao việc thiết lập baseline sớm có thể tiết kiệm thời gian và giảm bớt rắc rối sau này.

## Câu trả lời nhanh
- **“set baseline” có nghĩa là gì?** Nó ghi lại ngày bắt đầu, ngày kết thúc và thời lượng gốc của một công việc để bạn có thể so sánh các thay đổi trong tương lai.  
- **Lớp Aspose.Tasks nào tạo dự án?** Lớp `Project` – bạn cũng sẽ học cách **tạo instance dự án** một cách chính xác.  
- **Tôi có cần giấy phép để chạy mã không?** Giấy phép dùng thử miễn phí hoạt động cho việc kiểm tra; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể truy xuất các baseline tạm thời không?** Có, Aspose.Tasks cho phép bạn truy vấn các baseline tạm thời và chi phí cố định của chúng.  
- **Yêu cầu phiên bản Java nào?** Java 8 hoặc mới hơn được khuyến nghị.

## Baseline công việc là gì và tại sao cần đặt nó?
Baseline của một công việc ghi lại lịch trình dự kiến (ngày bắt đầu, ngày kết thúc và thời lượng) tại một thời điểm nhất định. Bằng cách đặt baseline, bạn tạo ra một điểm tham chiếu giúp dễ dàng phát hiện sự lệch lịch, chi phí vượt ngân sách và việc phân bổ tài nguyên quá mức khi dự án tiến triển.

## Tại sao sử dụng Aspose.Tasks để quản lý baseline?
- **Tương thích .mpp đầy đủ** – đọc và ghi các tệp Microsoft Project gốc mà không cần cài Office.  
- **API phong phú** – truy cập dữ liệu baseline, các baseline tạm thời và thông tin thời gian‑phân đoạn một cách lập trình.  
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS với bất kỳ JDK tiêu chuẩn nào.

## Yêu cầu trước
1. **Môi trường phát triển Java** – JDK 8+ đã được cài đặt và cấu hình.  
2. **Aspose.Tasks cho Java** – tải thư viện từ [here](https://releases.aspose.com/tasks/java/).  
3. **IDE hoặc công cụ xây dựng** – Maven, Gradle, hoặc bất kỳ IDE nào bạn thích.

## Nhập các gói
First, import the necessary classes into your Java project:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Bước 1: Tạo một Instance Dự án
Creating a project instance is the foundation for any further manipulation. This step shows how to **create project instance** using Aspose.Tasks:

```java
Project project = new Project();
```

## Bước 2: Tạo Baseline cho Công việc
Add a new task to the project’s root and set its baseline. This records the original schedule for the task:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Bước 3: Hiển thị Thông tin Baseline của Công việc
Retrieve the baseline you just created and print its key properties. This helps you verify that the baseline was set correctly:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Bước 4: Kiểm tra Baseline Tạm thời và Chi phí Cố định
If you’re working with interim baselines, you can query whether the current baseline is interim and any associated fixed cost:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Bước 5: In Dữ liệu Thời gian‑phân đoạn
Time‑phased data shows how the baseline is distributed over time. Loop through the collection to inspect each entry:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Bằng cách thực hiện các bước này, bạn có thể **đặt baseline** thời lượng cho bất kỳ công việc nào và truy xuất thông tin chi tiết về baseline bằng Aspose.Tasks cho Java.

## Các vấn đề thường gặp và giải pháp
- **Baseline không hiển thị trong MS Project:** Đảm bảo bạn đã gọi `project.setBaseline(BaselineType.Baseline)` **sau** khi thêm công việc.  
- **NullPointerException khi gọi `getBaselines()`:** Xác nhận rằng công việc đã được thêm vào dự án trước khi đặt baseline.  
- **Không khớp đơn vị thời gian:** Sử dụng `TimeUnitType` để định dạng thời lượng đúng, đặc biệt khi làm việc với lịch tùy chỉnh.

## Câu hỏi thường gặp
### Baseline công việc trong MS Project là gì?
Baseline công việc trong MS Project là một ảnh chụp nhanh của lịch trình dự kiến ban đầu cho một công việc, bao gồm ngày bắt đầu, ngày kết thúc và thời lượng.

### Tại sao quản lý baseline công việc lại quan trọng?
Quản lý baseline công việc giúp so sánh lịch trình dự kiến với tiến độ thực tế của dự án, tạo điều kiện cho việc theo dõi và ra quyết định tốt hơn.

### Tôi có thể chỉnh sửa baseline công việc sau khi đã đặt không?
Có, bạn có thể chỉnh sửa baseline công việc trong MS Project để phản ánh các thay đổi trong kế hoạch dự án. Tuy nhiên, cần ghi lại mọi sai lệch so với baseline gốc.

### Aspose.Tasks có hỗ trợ các chức năng quản lý dự án khác không?
Có, Aspose.Tasks cung cấp một loạt các tính năng cho quản lý dự án, bao gồm lập lịch công việc, phân bổ nguồn lực và tạo biểu đồ Gantt.

### Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?
Bạn có thể tìm hỗ trợ cho Aspose.Tasks trên [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15), nơi bạn có thể đặt câu hỏi và tương tác với những người dùng khác.

## Các câu hỏi thường gặp bổ sung
**Q: Tôi có cần gọi `setBaseline` cho từng công việc riêng lẻ không?**  
A: Không. Gọi `project.setBaseline(BaselineType.Baseline)` sẽ ghi lại baseline cho tất cả các công việc trong dự án cùng một lúc.

**Q: Làm thế nào để đặt một baseline tạm thời cho một công việc cụ thể?**  
A: Sử dụng `project.setBaseline(BaselineType.Baseline1)` (hoặc Baseline2‑Baseline10) sau khi cập nhật lịch trình của công việc.

**Q: Có thể xuất dữ liệu baseline ra CSV không?**  
A: Có. Duyệt qua `task.getBaselines()` và ghi các trường mong muốn vào tệp CSV bằng I/O chuẩn của Java.

**Q: Tôi có thể đọc một tệp .mpp hiện có đã chứa baseline không?**  
A: Chắc chắn. Tải tệp bằng `new Project("myproject.mpp")` và sau đó truy cập baseline của từng công việc như đã minh họa ở trên.

**Q: Aspose.Tasks có hỗ trợ tệp đa dự án không?**  
A: Aspose.Tasks làm việc với các tệp .mpp đơn dự án. Đối với các kịch bản đa dự án, bạn cần kết hợp các dự án bằng chương trình.

---

**Cập nhật lần cuối:** 2026-01-23  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}