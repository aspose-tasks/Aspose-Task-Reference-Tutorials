---
date: 2025-12-21
description: Tìm hiểu cách tùy chỉnh chế độ xem biểu đồ Gantt, quản lý việc hiển thị
  dự án và lưu dự án dưới dạng PDF bằng Aspose.Tasks cho Java. Điều chỉnh số lượng
  thang thời gian một cách dễ dàng.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tùy chỉnh biểu đồ Gantt – Thành thạo việc đếm thang thời gian trong MS Project
  bằng Aspose.Tasks
url: /vi/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tùy chỉnh Biểu đồ Gantt – Thành thạo Đếm Thang thời gian trong MS Project bằng Aspose.Tasks

## Introduction
Nếu bạn cần **tùy chỉnh biểu đồ Gantt** trong Microsoft Project, việc kiểm soát số lượng thang thời gian là một kỹ thuật then chốt. Với Aspose.Tasks for Java bạn có thể thiết lập chương trình các tầng thời gian dưới và trung, tinh chỉnh hiển thị tick, và sau đó **lưu dự án dưới dạng PDF** để chia sẻ với các bên liên quan. Hướng dẫn này sẽ đưa bạn qua toàn bộ quy trình—từ cài đặt môi trường đến tạo ra một PDF hoàn chỉnh phản ánh giao diện Gantt đã tùy chỉnh.

## Quick Answers
- **What does “customize Gantt chart” mean?** Điều chỉnh các tầng thang thời gian, màu sắc và bố cục để phù hợp với nhu cầu báo cáo của bạn.  
- **Which API method sets the bottom tier count?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Can I generate a PDF directly from the project?** Yes—use `project.save(..., SaveFileFormat.Pdf)`.  
- **Do I need a license for production use?** Cần có giấy phép thương mại; bản dùng thử miễn phí có sẵn.  
- **Which Java version is supported?** Java 8 hoặc cao hơn hoạt động với thư viện Aspose.Tasks mới nhất.

## What is “customize Gantt chart” in Aspose.Tasks?
Việc tùy chỉnh biểu đồ Gantt có nghĩa là thay đổi các thành phần trực quan của nó một cách lập trình—như khoảng thời gian thang thời gian, dấu tick, và thanh nhiệm vụ—để biểu đồ phù hợp với cách bạn muốn **quản lý việc hiển thị dự án**. Bằng cách thay đổi số lượng thang thời gian, bạn kiểm soát số ngày, tuần hoặc tháng mà mỗi đoạn đại diện, làm cho biểu đồ rõ ràng hơn cho các đối tượng khác nhau.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Java Development Environment** – Môi trường phát triển Java — JDK 8 hoặc mới hơn đã được cài đặt.  
2. **Aspose.Tasks for Java Library** – Download it from [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** – Kiến thức cơ bản về Java — Quen thuộc với cú pháp Java và các khái niệm hướng đối tượng.

## Import Packages
Import the necessary classes into your Java project:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step‑by‑Step Guide

### Step 1: Set Data Directory
Define where your project files will be read from and written to:

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path on your machine.  
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối trên máy của bạn.

### Step 2: Create a New Project Instance
Instantiate a fresh `Project` object that will hold all tasks and view settings:

```java
Project project = new Project();
```

### Step 3: Configure the Gantt Chart View
Create a `GanttChartView` object—this is where you’ll **generate Gantt view Java** code to control the chart appearance:

```java
GanttChartView view = new GanttChartView();
```

### Step 4: Set Time Scale Count for the Bottom Tier
Adjust the bottom tier to show two intervals and hide the tick marks:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Step 5: Set Time Scale Count for the Middle Tier
Apply the same configuration to the middle tier:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Step 6: Add the Customized View to the Project
Attach the view you just configured to the `Project` instance:

```java
project.getViews().add(view);
```

### Step 7: Add Sample Tasks (Test Data)
Create a couple of tasks with specific durations to illustrate the customized Gantt chart:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Step 8: Save the Project as a PDF
Finally, export the project—including your **customized Gantt chart**—to a PDF file:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

The resulting PDF demonstrates how the bottom and middle time‑scale tiers have been **customized**, giving stakeholders a clear, printable view of the schedule.  
PDF kết quả cho thấy cách các tầng thang thời gian dưới và trung đã được **tùy chỉnh**, cung cấp cho các bên liên quan một góc nhìn rõ ràng, có thể in được của lịch trình.

## Common Issues & Troubleshooting
- **PDF is blank** – Ensure the `dataDir` path ends with a file separator (`/` or `\`) and that the directory exists.  
  PDF trống — Đảm bảo đường dẫn `dataDir` kết thúc bằng dấu phân tách thư mục (`/` hoặc `\`) và thư mục tồn tại.  
- **Ticks still appear** – Verify that `setShowTicks(false)` is called on both tiers.  
  Các dấu tick vẫn xuất hiện — Kiểm tra rằng `setShowTicks(false)` được gọi trên cả hai tầng.  
- **Duration not applied** – Confirm you are using `TimeUnitType.Hour` (or the appropriate unit) when creating durations.  
  Thời lượng không được áp dụng — Xác nhận bạn đang sử dụng `TimeUnitType.Hour` (hoặc đơn vị phù hợp) khi tạo thời lượng.

## Frequently Asked Questions

**Q: Can Aspose.Tasks for Java handle large‑scale project files?**  
A: Yes, the library is optimized for high‑performance processing of extensive project data.  
Có, thư viện được tối ưu cho việc xử lý hiệu suất cao các dữ liệu dự án quy mô lớn.

**Q: Is Aspose.Tasks for Java compatible with different Java IDEs?**  
A: Absolutely – it works seamlessly with Eclipse, IntelliJ IDEA, NetBeans, and other popular IDEs.  
Chắc chắn — nó hoạt động liền mạch với Eclipse, IntelliJ IDEA, NetBeans và các IDE phổ biến khác.

**Q: Can I customize the appearance of Gantt charts beyond time‑scale settings?**  
A: Yes, Aspose.Tasks provides extensive styling options such as bar colors, fonts, and grid lines.  
Có, Aspose.Tasks cung cấp các tùy chọn định dạng phong phú như màu thanh, phông chữ và đường lưới.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: Yes, you can get a free trial version from [here](https://releases.aspose.com/).  

**Q: Where can I get support for Aspose.Tasks for Java?**  
A: You can find support and assistance on the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).  

**Q: How do I programmatically change the Gantt chart’s background color?**  
A: Use the `view.getGanttChartProperties().setBackgroundColor(Color)` method after importing `java.awt.Color`.  

## Conclusion
By following these steps you’ve learned how to **customize Gantt chart** time‑scale tiers, improve **project visualization**, and **save project as PDF** using Aspose.Tasks for Java. This approach gives you full control over the visual output, making it easier to share clear, professional schedules with your team or clients.  
Bằng cách thực hiện các bước trên, bạn đã học cách **tùy chỉnh các tầng thang thời gian của biểu đồ Gantt**, cải thiện **việc hiển thị dự án**, và **lưu dự án dưới dạng PDF** bằng Aspose.Tasks for Java. Cách tiếp cận này cho phép bạn kiểm soát hoàn toàn đầu ra hình ảnh, giúp dễ dàng chia sẻ các lịch trình rõ ràng, chuyên nghiệp với đội ngũ hoặc khách hàng của mình.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}