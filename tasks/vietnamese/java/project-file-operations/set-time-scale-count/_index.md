---
title: Nắm vững số lượng quy mô thời gian của dự án MS trong Aspose.Tasks
linktitle: Đặt số lượng quy mô thời gian trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách quản lý hiệu quả số lượng quy mô thời gian trong MS Project bằng Aspose.Tasks cho Java. Tối ưu hóa trực quan hóa và quản lý dự án một cách dễ dàng.
weight: 22
url: /vi/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nắm vững số lượng quy mô thời gian của dự án MS trong Aspose.Tasks

## Giới thiệu
Việc quản lý số lượng quy mô thời gian trong MS Project có thể ảnh hưởng đáng kể đến việc quản lý và trực quan hóa dự án. Với Aspose.Tasks cho Java, một API mạnh mẽ để xử lý các tác vụ quản lý dự án theo chương trình, bạn có thể thao tác một cách hiệu quả số lượng quy mô thời gian để điều chỉnh chế độ xem dự án theo nhu cầu cụ thể của mình.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có sẵn những điều sau:
1. Môi trường phát triển Java: Đảm bảo bạn đã cài đặt Bộ công cụ phát triển Java (JDK) trên hệ thống của mình.
2.  Aspose.Tasks for Java Library: Tải xuống và cài đặt thư viện Aspose.Tasks for Java. Bạn có thể lấy nó từ[đây](https://releases.aspose.com/tasks/java/).
3. Kiến thức cơ bản về lập trình Java: Làm quen với ngôn ngữ lập trình Java sẽ có lợi.

## Gói nhập khẩu
Nhập các gói cần thiết vào dự án Java của bạn:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Bước 1: Đặt thư mục dữ liệu
Xác định đường dẫn đến thư mục dữ liệu nơi các tệp dự án của bạn sẽ được lưu trữ:
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"` với đường dẫn đến thư mục dữ liệu của bạn.
## Bước 2: Tạo phiên bản dự án
 Khởi tạo một cái mới`Project` sự vật:
```java
Project project = new Project();
```
Điều này tạo ra một đối tượng dự án mới.
## Bước 3: Định cấu hình Chế độ xem biểu đồ Gantt
 Tạo một`GanttChartView` đối tượng để định cấu hình chế độ xem biểu đồ Gantt:
```java
GanttChartView view = new GanttChartView();
```
## Bước 4: Đặt số lượng thang thời gian cho cấp dưới cùng
Đặt mức độ hiển thị số lượng và đánh dấu cho bậc thời gian dưới cùng:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Điều này chỉ định số lượng khoảng thời gian và có hiển thị dấu tích cho tầng dưới cùng hay không.
## Bước 5: Đặt số lượng thang thời gian cho cấp trung
Tương tự, định cấu hình tầng thời gian ở giữa:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Bước 6: Thêm chế độ xem vào dự án
Thêm chế độ xem được định cấu hình vào dự án:
```java
project.getViews().add(view);
```
Điều này thêm chế độ xem tùy chỉnh cho dự án.
## Bước 7: Thêm dữ liệu thử nghiệm vào dự án
Thêm một số dữ liệu thử nghiệm vào dự án để trình diễn:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Điều này tạo ra hai nhiệm vụ với thời lượng được chỉ định.
## Bước 8: Lưu dự án dưới dạng PDF
Lưu dự án dưới dạng tệp PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Thao tác này sẽ lưu dự án với các cấu hình được áp dụng vào tệp PDF.

## Phần kết luận
Quản lý hiệu quả số lượng quy mô thời gian trong MS Project bằng Aspose.Tasks cho Java cho phép bạn tùy chỉnh các chế độ xem dự án để quản lý và trực quan hóa tốt hơn.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks cho Java có thể xử lý các tệp dự án quy mô lớn không?
Trả lời: Có, Aspose.Tasks cho Java có khả năng xử lý các tệp dự án quy mô lớn một cách hiệu quả.
### Câu hỏi: Aspose.Tasks dành cho Java có tương thích với các IDE Java khác nhau không?
Trả lời: Có, Aspose.Tasks dành cho Java hoạt động liền mạch với các Môi trường phát triển tích hợp Java (IDE) phổ biến như Eclipse và IntelliJ IDEA.
### Câu hỏi: Tôi có thể tùy chỉnh giao diện của biểu đồ Gantt bằng Aspose.Tasks cho Java không?
Đáp: Hoàn toàn có thể, Aspose.Tasks dành cho Java cung cấp các khả năng mở rộng để tùy chỉnh giao diện của biểu đồ Gantt theo yêu cầu của bạn.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
 Đ: Có, bạn có thể tải phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?
 Trả lời: Bạn có thể tìm thấy sự hỗ trợ và trợ giúp trên diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
