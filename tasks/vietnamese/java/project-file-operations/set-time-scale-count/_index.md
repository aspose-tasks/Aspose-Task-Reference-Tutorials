---
date: 2026-03-29
description: Tìm hiểu cách tạo tệp PDF dự án đồng thời tùy chỉnh số lượng thang thời
  gian của biểu đồ Gantt bằng Aspose.Tasks cho Java. Hướng dẫn này sẽ chỉ cho bạn
  từng bước cách xuất Gantt sang PDF với kiểm soát đầy đủ.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tạo PDF Dự án – Tùy chỉnh thang thời gian biểu đồ Gantt
url: /vi/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo PDF Dự Án – Tùy Chỉnh Thang Thời Gian Biểu Đồ Gantt

## Giới thiệu
Nếu bạn cần **tạo PDF dự án** có biểu đồ Gantt được điều chỉnh hoàn hảo, việc kiểm soát số lượng thang thời gian là chìa khóa. Với Aspose.Tasks for Java, bạn có thể lập trình thiết lập các tầng thang thời gian dưới và giữa, ẩn các dấu tick, và sau đó **lưu dự án dưới dạng PDF** để dễ dàng phân phối. Trong hướng dẫn này, chúng ta sẽ đi qua mọi thứ bạn cần—từ việc thiết lập môi trường phát triển đến tạo ra một PDF chuyên nghiệp hiển thị chế độ xem Gantt đã tùy chỉnh của bạn.

## Câu trả lời nhanh
- **“Tùy chỉnh biểu đồ Gantt” có nghĩa là gì?** Điều chỉnh các tầng thang thời gian, màu sắc và bố cục để phù hợp với nhu cầu báo cáo của bạn.  
- **Phương thức API nào thiết lập số lượng tầng dưới cùng?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Tôi có thể tạo PDF trực tiếp từ dự án không?** Có—sử dụng `project.save(..., SaveFileFormat.Pdf)`.  
- **Có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần giấy phép thương mại; bản dùng thử miễn phí có sẵn.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc cao hơn hoạt động với thư viện Aspose.Tasks mới nhất.

## “Tùy chỉnh biểu đồ Gantt” là gì trong Aspose.Tasks?
Tùy chỉnh một biểu đồ Gantt có nghĩa là thay đổi các thành phần trực quan của nó một cách lập trình—như khoảng thời gian thang thời gian, dấu tick và thanh nhiệm vụ—để biểu đồ phù hợp với cách bạn muốn **quản lý việc hiển thị dự án**. Bằng cách thay đổi số lượng thang thời gian, bạn kiểm soát số ngày, tuần hoặc tháng mà mỗi đoạn đại diện, làm cho biểu đồ rõ ràng hơn cho các đối tượng khác nhau.

## Tại sao tạo PDF dự án với biểu đồ Gantt tùy chỉnh?
- **Kết quả sẵn sàng cho các bên liên quan:** PDF có thể xem trên mọi nền tảng, đảm bảo mọi người nhìn thấy cùng một bố cục lịch trình.  
- **Thân thiện với việc in:** Kiểm soát chính xác các tầng thang thời gian ngăn ngừa việc in ra quá chật chội hoặc mơ hồ.  
- **Tự động hoá:** Tích hợp việc tạo PDF vào các pipeline CI hoặc dịch vụ báo cáo để không cần thao tác thủ công.

## Các yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Môi trường phát triển Java** – JDK 8 hoặc mới hơn đã được cài đặt.  
2. **Thư viện Aspose.Tasks for Java** – Tải về từ [here](https://releases.aspose.com/tasks/java/).  
3. **Kiến thức cơ bản về Java** – Quen thuộc với cú pháp Java và các khái niệm hướng đối tượng.

## Nhập các gói
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

### Bước 1: Đặt thư mục dữ liệu
Xác định nơi các tệp dự án sẽ được đọc và ghi:

```java
String dataDir = "Your Data Directory";
```

Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối trên máy của bạn.

### Bước 2: Tạo một thể hiện Project mới
Khởi tạo một đối tượng `Project` mới sẽ chứa tất cả các nhiệm vụ và cài đặt chế độ xem:

```java
Project project = new Project();
```

### Bước 3: Cấu hình chế độ xem biểu đồ Gantt
Tạo một đối tượng `GanttChartView`—đây là nơi bạn sẽ **tạo mã Java để tạo chế độ xem Gantt** và kiểm soát giao diện biểu đồ:

```java
GanttChartView view = new GanttChartView();
```

### Bước 4: Đặt số lượng thang thời gian cho tầng dưới cùng
Điều chỉnh tầng dưới cùng để hiển thị hai khoảng và ẩn các dấu tick:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Bước 5: Đặt số lượng thang thời gian cho tầng giữa
Áp dụng cùng cấu hình cho tầng giữa:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Bước 6: Thêm chế độ xem tùy chỉnh vào Project
Gắn chế độ xem vừa cấu hình vào thể hiện `Project`:

```java
project.getViews().add(view);
```

### Bước 7: Thêm các tác vụ mẫu (Dữ liệu kiểm tra)
Tạo một vài nhiệm vụ với thời lượng cụ thể để minh họa biểu đồ Gantt đã tùy chỉnh:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Bước 8: Lưu Project dưới dạng PDF
Cuối cùng, xuất dự án—bao gồm **biểu đồ Gantt đã tùy chỉnh**—ra tệp PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

PDF kết quả sẽ cho thấy các tầng thang thời gian dưới và giữa đã được **tùy chỉnh**, cung cấp cho các bên liên quan một cái nhìn rõ ràng, có thể in được của lịch trình.

## Các vấn đề thường gặp & Khắc phục
- **PDF trống** – Đảm bảo đường dẫn `dataDir` kết thúc bằng dấu phân cách thư mục (`/` hoặc `\`) và thư mục tồn tại.  
- **Vẫn còn dấu tick** – Kiểm tra rằng `setShowTicks(false)` đã được gọi trên cả hai tầng.  
- **Thời lượng không được áp dụng** – Xác nhận bạn đang sử dụng `TimeUnitType.Hour` (hoặc đơn vị phù hợp) khi tạo thời lượng.

## Câu hỏi thường gặp

**Q: Aspose.Tasks for Java có thể xử lý các tệp dự án quy mô lớn không?**  
A: Có, thư viện được tối ưu cho việc xử lý hiệu suất cao các dữ liệu dự án quy mô lớn.

**Q: Aspose.Tasks for Java có tương thích với các IDE Java khác nhau không?**  
A: Chắc chắn – nó hoạt động liền mạch với Eclipse, IntelliJ IDEA, NetBeans và các IDE phổ biến khác.

**Q: Tôi có thể tùy chỉnh giao diện biểu đồ Gantt ngoài cài đặt thang thời gian không?**  
A: Có, Aspose.Tasks cung cấp nhiều tùy chọn định dạng như màu thanh, phông chữ và đường lưới.

**Q: Có phiên bản dùng thử cho Aspose.Tasks for Java không?**  
A: Có, bạn có thể tải phiên bản dùng thử miễn phí từ [here](https://releases.aspose.com/).

**Q: Tôi có thể nhận hỗ trợ cho Aspose.Tasks for Java ở đâu?**  
A: Bạn có thể tìm hỗ trợ và trợ giúp trên diễn đàn Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: Làm thế nào để lập trình thay đổi màu nền của biểu đồ Gantt?**  
A: Sử dụng phương thức `view.getGanttChartProperties().setBackgroundColor(Color)` sau khi nhập `java.awt.Color`.

## Kết luận
Bằng cách thực hiện các bước trên, bạn đã học cách **tạo PDF dự án** với thang thời gian biểu đồ Gantt được tùy chỉnh hoàn toàn, cải thiện **việc hiển thị dự án**, và **lưu dự án dưới dạng PDF** bằng Aspose.Tasks for Java. Cách tiếp cận này cho phép bạn kiểm soát toàn bộ đầu ra trực quan, giúp dễ dàng chia sẻ các lịch trình chuyên nghiệp, rõ ràng với đội ngũ hoặc khách hàng của mình.

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}