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

# Tùy chỉnh Biểu đồ Gantt – Thành nhớ Tính Thang thời gian trong MS Project bằng Aspose.Tasks

## Giới thiệu
Nếu bạn cần **điều chỉnh biểu đồ Gantt** trong Microsoft Project, việc kiểm soát số lượng thời gian là một kỹ thuật sau đó. Với Aspose.Tasks for Java, bạn có thể thiết lập chương trình các tầng thời gian bên dưới và trung, chỉnh sửa dấu kiểm hiển thị và sau đó **lưu dự án dưới dạng PDF** để chia sẻ với các bên liên quan. Hướng dẫn này sẽ cung cấp cho bạn toàn bộ quy trình—từ môi trường cài đặt để tạo một bản PDF phản ánh hoàn chỉnh tùy chọn giao diện Gantt.

## Trả lời nhanh
- **“Tùy chỉnh biểu đồ Gantt” nghĩa là gì?** Điều chỉnh các tầng trong thời gian, màu sắc và bố cục để phù hợp với nhu cầu báo cáo báo cáo của bạn.
- **Phương thức API nào đặt số lượng bậc dưới cùng?** `view.getBottomTimescaleTier().setCount(int)`.
- **Tôi có thể tạo tệp PDF trực tiếp từ dự án không?** Có—sử dụng `project.save(..., SaveFileFormat.Pdf)`.
- **Tôi có cần giấy phép để sử dụng sản xuất không?** Cần có giấy phép thương mại; bản thử miễn phí đã có sẵn.
- **Phiên bản Java nào được hỗ trợ?** Java8 hoặc cao hơn hoạt động với thư viện Aspose.Tasks mới nhất.

## “tùy chỉnh biểu đồ Gantt” trong Aspose.Tasks là gì?
Tùy chỉnh biểu đồ Gantt có nghĩa là thay đổi các phần trực tiếp của nó bằng một cách cài đặt—như khoảng thời gian, dấu tích và thanh nhiệm vụ—để biểu đồ phù hợp theo cách bạn muốn **quản lý công việc hiển thị dự án**. Bằng cách thay đổi số lượng trong thời gian, bạn kiểm soát số ngày, tuần hoặc tháng mà mỗi đoạn đại diện, làm cho biểu đồ rõ ràng hơn cho các đối tượng khác nhau.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Môi trường phát triển Java** – Môi trường phát triển Java — JDK 8hoặc mới hơn đã được cài đặt.
2. **Aspose.Tasks cho Thư viện Java** – Tải xuống từ [tại đây](https://releases.aspose.com/tasks/java/).
3. **Kiến thức Java cơ bản** – Kiến thức cơ bản về Java — Quen thuộc với cú pháp Java và các khái niệm hướng đối tượng.

## Nhập gói
Nhập các lớp cần thiết vào dự án Java của bạn:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập thư mục dữ liệu

Xác định nơi các tệp dự án của bạn sẽ được đọc và ghi:

```java
String dataDir = "Your Data Directory";
```

Thay thế `"Thư mục dữ liệu của bạn"` bằng đường dẫn tuyệt đối trên máy của bạn.

### Bước 2: Tạo một đối tượng dự án mới
Tạo một đối tượng `Project` mới để chứa tất cả các tác vụ và cài đặt hiển thị:

```java
Project project = new Project();
```

### Bước 3: Cấu hình chế độ xem biểu đồ Gantt
Tạo một đối tượng `GanttChartView`—đây là nơi bạn sẽ **tạo mã Java cho chế độ xem Gantt** để điều khiển giao diện biểu đồ:

```java
GanttChartView view = new GanttChartView();
```

### Bước 4: Đặt số lượng thang thời gian cho tầng dưới cùng
Điều chỉnh tầng dưới cùng để hiển thị hai khoảng thời gian và ẩn các vạch đánh dấu:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Bước 5: Đặt số lượng thang thời gian cho tầng giữa
Áp dụng cấu hình tương tự cho tầng giữa:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Bước 6: Thêm chế độ xem tùy chỉnh vào dự án
Đính kèm chế độ xem bạn vừa cấu hình vào đối tượng `Project`:

```java
project.getViews().add(view);
```

### Bước 7: Thêm các tác vụ mẫu (Dữ liệu thử nghiệm)
Tạo một vài tác vụ với thời lượng cụ thể để minh họa biểu đồ Gantt tùy chỉnh:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Bước 8: Lưu dự án dưới dạng PDF
Cuối cùng, xuất dự án—bao gồm cả **chế độ xem tùy chỉnh** của bạn Biểu đồ Gantt**—chuyển đổi sang tệp PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Bản PDF thu được trình bày cách các bậc ở thang thời gian dưới cùng và giữa đã được **tùy chỉnh**, giúp các bên liên quan có cái nhìn rõ ràng, có thể in được về lịch trình.
Kết quả PDF cho thấy các tầng trong thời gian bên dưới và trung đã được **chỉnh**, cung cấp cho các bên liên quan một góc nhìn rõ ràng, có thể trong lịch trình.

## Các vấn đề thường gặp & cách khắc phục sự cố
- **PDF trống** – Đảm bảo đường dẫn `dataDir` kết thúc bằng dấu phân tách tệp (`/` hoặc `\`) và thư mục đó tồn tại. 
Trống PDF — Đảm bảo đường dẫn `dataDir` kết thúc bằng dấu phân tách thư mục (`/` hoặc `\`) và thư mục tồn tại.
- **Ticks vẫn xuất hiện** – Xác minh rằng `setShowTicks(false)` được gọi trên cả hai cấp. 
Dấu tích vẫn xuất hiện — Kiểm tra rằng `setShowTicks(false)` được gọi trên cả hai tầng.
- **Thời lượng không được áp dụng** – Xác nhận bạn đang sử dụng `TimeUnitType.Hour` (hoặc đơn vị thích hợp) khi tạo thời lượng. 
Thời gian không được áp dụng — Xác nhận rằng bạn đang sử dụng `TimeUnitType.Hour` (hoặc đơn vị phù hợp) khi tạo thời lượng.

## Câu hỏi thường gặp

**Hỏi: Aspose.Tasks dành cho Java có thể xử lý các tệp dự án quy mô lớn không?**
Đáp: Có, thư viện được tối ưu hóa để xử lý hiệu suất cao dữ liệu dự án mở rộng.
Có, thư viện tối ưu đã được xử lý để thực hiện hiệu suất cao nhất của mô-đun dự án dữ liệu.

**Hỏi: Aspose.Tasks dành cho Java có tương thích với các IDE Java khác nhau không?**
Đáp: Hoàn toàn có thể – nó hoạt động trơn tru với Eclipse, IntelliJ IDEA, NetBeans và các IDE phổ biến khác.
Chắc chắn — nó hoạt động liền mạch với Eclipse, IntelliJ IDEA, NetBeans và các IDE phổ biến khác.

**Hỏi: Tôi có thể tùy chỉnh giao diện của biểu đồ Gantt ngoài các thiết lập thang thời gian không?**
Trả lời: Có, Aspose.Tasks cung cấp các tùy chọn tạo kiểu mở rộng như màu thanh, phông chữ và đường lưới.

**Hỏi: Có phiên bản dùng thử nào cho Aspose.Tasks dành cho Java không?**
Trả lời: Có, bạn có thể tải phiên bản dùng thử miễn phí tại [đây](https://releases.aspose.com/).

**Hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks dành cho Java ở đâu?**
Trả lời: Bạn có thể tìm thấy hỗ trợ và trợ giúp trên diễn đàn Aspose.Tasks [tại đây](https://forum.aspose.com/c/tasks/15).

**Hỏi: Làm cách nào để thay đổi màu nền của biểu đồ Gantt theo chương trình?**
Đáp: Sử dụng phương thức `view.getGanttChartProperties().setBackgroundColor(Color)` sau khi nhập `java.awt.Color`.

## Phần kết luận
Bằng cách làm theo các bước này, bạn đã học được cách **tùy chỉnh biểu đồ Gantt** các bậc thang thời gian, cải thiện **hình dung dự án** và **lưu dự án dưới dạng PDF** bằng cách sử dụng Aspose.Tasks cho Java. Cách tiếp cận này cung cấp cho bạn toàn quyền kiểm soát đầu ra trực quan, giúp chia sẻ lịch trình rõ ràng, chuyên nghiệp với nhóm hoặc khách hàng của bạn dễ dàng hơn.
Bằng cách thực hiện các bước trên, bạn đã học cách **điều chỉnh các tầng thang thời gian của biểu đồ Gantt**, cải thiện **việc hiển thị dự án** và **lưu dự án dưới dạng PDF** bằng Aspose.Tasks for Java. Cách tiếp cận này cho phép bạn kiểm soát Kiểm soát hoàn toàn đầu ra hình ảnh, giúp dễ dàng chia sẻ các lịch trình rõ ràng, chuyên nghiệp với đội ngũ hoặc khách hàng của mình.

---

**Cập nhật lần cuối:** 2025-12-21
**Đã kiểm thử với:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết bài)
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}