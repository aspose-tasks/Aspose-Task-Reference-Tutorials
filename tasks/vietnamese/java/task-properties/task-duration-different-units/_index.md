---
date: 2026-02-28
description: Tìm hiểu cách lấy thời lượng tính bằng phút, ngày, giờ, tuần và tháng
  bằng Aspose.Tasks cho Java. Hướng dẫn chi tiết kèm ví dụ mã.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách lấy thời lượng trong các đơn vị khác nhau với Aspose.Tasks
url: /vi/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lấy thời lượng ở các đơn vị khác nhau với Aspose.Tasks

## Giới thiệu
Hiểu **how to get duration** cho các công việc là một phần cốt lõi của bất kỳ quy trình quản lý dự án nào. Dù bạn cần phút để theo dõi chi tiết hay tháng để lập kế hoạch tổng thể, Aspose.Tasks for Java giúp việc chuyển đổi trở nên đơn giản. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách lấy thời lượng của một công việc tính bằng phút, ngày, giờ, tuần và tháng, đồng thời giải thích lý do mỗi đơn vị có thể hữu ích trong các dự án thực tế.

## Trả lời nhanh
- **“how to get duration” có nghĩa là gì?** Đó là quá trình trích xuất khoảng thời gian của một công việc và chuyển đổi nó sang đơn vị bạn cần.  
- **Phương thức API nào thực hiện việc chuyển đổi?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **Tôi có cần giấy phép để chạy mã không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; cần giấy phép thương mại cho môi trường sản xuất.  
- **Tôi có thể chuyển đổi sang các đơn vị tùy chỉnh không?** Bạn có thể xâu chuỗi các chuyển đổi hoặc sử dụng `TimeSpan` cho các phép tính tùy chỉnh.  
- **Mã có tương thích với Java 17 không?** Có, Aspose.Tasks hỗ trợ Java 8 và các phiên bản mới hơn.

## “how to get duration” là gì trong Aspose.Tasks?
Aspose.Tasks lưu độ dài của công việc dưới dạng đối tượng `Duration`. Bằng cách gọi phương thức `convert` và chỉ định một `TimeUnitType` (Minute, Hour, Day, Week, Month), bạn có thể lấy cùng một giá trị cơ bản nhưng được biểu diễn bằng đơn vị mong muốn. Tính linh hoạt này cho phép bạn tạo báo cáo, thực hiện các phép tính, hoặc truyền dữ liệu sang hệ thống khác mà không cần tính toán thủ công.

## Tại sao nên dùng Aspose.Tasks để chuyển đổi thời lượng?
- **Độ chính xác:** Tự động xử lý các ngoại lệ lịch, thời gian làm việc và lịch không chuẩn.  
- **Hiệu suất:** Chuyển đổi trong một dòng lệnh, không cần vòng lặp hay phân tích tùy chỉnh.  
- **Khả năng di động:** Hoạt động giống nhau trên Windows, Linux và macOS.  
- **Tích hợp:** Dễ dàng nhúng vào các ứng dụng Java hiện có đã sử dụng Aspose.Tasks.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- Java Development Kit (JDK) được cài đặt
- Thư viện Aspose.Tasks for Java. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/tasks/java/)
- Kiến thức cơ bản về lập trình Java

## Nhập khẩu các gói
Trong dự án Java của bạn, bao gồm thư viện Aspose.Tasks. Thêm câu lệnh import sau vào đầu file mã nguồn:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Bước 1: Thiết lập dự án
Tạo một dự án Java mới trong IDE yêu thích (IntelliJ, Eclipse, VS Code, …) và thêm file JAR của Aspose.Tasks vào classpath của dự án. Điều này sẽ làm cho các lớp trên có sẵn khi biên dịch.

## Bước 2: Đọc mẫu dự án
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

Thay thế `"Your Document Directory"` bằng thư mục thực tế chứa file dự án `.xml` hoặc `.mpp` của bạn.

## Bước 3: Lấy một công việc
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

Lệnh `getById(1)` sẽ lấy công việc có ID = 1. Điều chỉnh ID nếu muốn truy xuất công việc khác trong file.

## Bước 4: Thời lượng tính bằng phút – How to get duration in minutes?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

Biến `mins` hiện chứa độ dài công việc được biểu diễn bằng phút.

## Bước 5: Thời lượng tính bằng ngày – How to get duration in days?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

Sử dụng giá trị này khi bạn cần độ chi tiết ở mức ngày cho báo cáo hoặc phân bổ nguồn lực.

## Bước 6: Thời lượng tính bằng giờ – How to get duration in hours?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

Giờ rất hữu ích cho bảng chấm công hoặc khi bạn muốn chia một ngày thành các ca làm việc.

## Bước 7: Thời lượng tính bằng tuần – How to get duration in weeks?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

Tuần thường được dùng trong biểu đồ Gantt cấp cao hoặc lập kế hoạch mốc quan trọng.

## Bước 8: Thời lượng tính bằng tháng – How to get duration in months?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

Thời lượng ở mức tháng giúp bạn đồng bộ các giai đoạn dự án với kỳ tài chính.

## Các vấn đề thường gặp và giải pháp
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `NullPointerException` on `task` | Wrong task ID or missing children | Verify the task ID exists using `project.getRootTask().getChildren()` |
| Unexpected values (e.g., 0) | Project uses a custom calendar with non‑working days | Ensure the project’s calendar is correctly defined or use `project.getCalendar()` to inspect it |
| Conversion returns fractional weeks | Weeks are calculated based on the project’s default week length (usually 5 days) | Multiply by 5 if you need calendar weeks, or adjust the calendar settings |

## Câu hỏi thường gặp
### H: Tôi có thể dùng Aspose.Tasks for Java với bất kỳ IDE Java nào không?
Đ: Có, Aspose.Tasks for Java tương thích với mọi môi trường phát triển Java (IDE).

### H: Làm thế nào để lấy ID của một công việc trong file Microsoft Project?
Đ: Bạn có thể kiểm tra file dự án thủ công hoặc gọi `project.getRootTask().getChildren()` và duyệt qua collection để đọc `ID` của từng công việc.

### H: Aspose.Tasks có phù hợp cho các dự án quy mô lớn không?
Đ: Chắc chắn. Aspose.Tasks được thiết kế để xử lý hiệu quả các dự án có hàng ngàn công việc và nguồn lực.

### H: Tôi có thể tìm tài liệu chi tiết ở đâu?
Đ: Truy cập [documentation](https://reference.aspose.com/tasks/java/) để xem tài liệu API toàn diện, mẫu mã và hướng dẫn thực hành tốt nhất.

### H: Tôi có thể dùng thử Aspose.Tasks for Java trước khi mua không?
Đ: Có, bạn có thể khám phá [free trial](https://releases.aspose.com/) để đánh giá các tính năng.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}