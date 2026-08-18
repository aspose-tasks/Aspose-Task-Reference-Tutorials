---
date: 2026-02-20
description: Khám phá cách thêm nhiệm vụ vào dự án và quản lý thời lượng với Aspose.Tasks
  cho Java. Tìm hiểu cách đặt thời lượng và cách chuyển đổi thời lượng một cách dễ
  dàng.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Thêm công việc vào dự án và quản lý thời lượng với Aspose.Tasks
url: /vi/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Nhiệm Vụ vào Dự Án và Quản Lý Thời Lượng với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách thêm nhiệm vụ vào dự án** và kiểm soát thời lượng của nó bằng Aspose.Tasks cho Java. Dù bạn đang xây dựng một công cụ lập kế hoạch dự án mới hay mở rộng một giải pháp hiện có, việc nắm vững xử lý thời lượng nhiệm vụ là điều thiết yếu để lập lịch và báo cáo chính xác.

## Câu trả lời nhanh
- **“add task to project” có nghĩa là gì?** Nó tạo một đối tượng nhiệm vụ mới dưới gốc của dự án hoặc dưới một nhiệm vụ tổng hợp cụ thể.  
- **Lớp nào đại diện cho một thời lượng?** `com.aspose.tasks.Duration`.  
- **Cách đặt thời lượng?** Sử dụng `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Có thể chuyển đổi thời lượng sang đơn vị khác không?** Có, gọi `duration.convert(TimeUnitType.Hour)` hoặc bất kỳ `TimeUnitType` nào khác.  
- **Có cần giấy phép cho môi trường sản xuất không?** Cần một giấy phép Aspose.Tasks hợp lệ cho việc sử dụng thương mại.

## Thêm nhiệm vụ vào dự án là gì?
Thêm một nhiệm vụ vào dự án có nghĩa là tạo một đối tượng `Task` và gắn nó vào cấu trúc cây nhiệm vụ của dự án. Thao tác này là bước đầu tiên trước khi bạn có thể định nghĩa công việc, nguồn lực hoặc thời lượng cho nhiệm vụ đó.

## Tại sao cần quản lý thời lượng nhiệm vụ?
Thời lượng chính xác mang lại các thời gian biểu thực tế, phân bổ nguồn lực hợp lý và phân tích đường truyền quan trọng. Với Aspose.Tasks, bạn có thể đặt, đọc, chuyển đổi và điều chỉnh thời lượng một cách lập trình, cho phép bạn kiểm soát toàn bộ lịch trình dự án.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:

- Java Development Kit (JDK): Đảm bảo rằng Java đã được cài đặt trên máy của bạn. Bạn có thể tải về [tại đây](https://www.oracle.com/java/technologies/javase-downloads.html).
- Thư viện Aspose.Tasks: Tải xuống và đưa thư viện Aspose.Tasks vào dự án của bạn. Bạn có thể tìm thư viện [tại đây](https://releases.aspose.com/tasks/java/).

## Nhập khẩu các gói
Trong dự án Java của bạn, nhập các gói cần thiết để làm việc với Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Bước 1: Thiết lập dự án của bạn
```java
// Create a new project
Project project = new Project();
```

## Bước 2: Thêm một Nhiệm Vụ Mới (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Cách đặt thời lượng
Bây giờ nhiệm vụ đã tồn tại, bạn có thể xác định độ dài của nó. Mặc định, thời lượng được biểu thị bằng ngày.

## Bước 3: Lấy và Chuyển Đổi Thời Lượng Nhiệm Vụ
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Cách chuyển đổi thời lượng
Phương thức `convert` cho phép bạn dịch một `Duration` từ một `TimeUnitType` sang một `TimeUnitType` khác (ví dụ: ngày → giờ, tuần → ngày).

## Bước 4: Cập nhật Thời Lượng Nhiệm Vụ thành 1 Tuần
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Bước 5: Giảm Thời Lượng Nhiệm Vụ
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Bằng cách thực hiện các bước này, bạn đã **thêm một nhiệm vụ vào dự án** và quản lý thời lượng của nó bằng Aspose.Tasks cho Java.

## Những Sai Lầm Thường Gặp & Mẹo
- **Sai lầm:** Quên chuyển đổi thời lượng trước khi thực hiện các phép tính có thể dẫn đến kết quả sai. Luôn kiểm tra đơn vị bằng `duration.getTimeUnit()`.
- **Mẹo:** Sử dụng `project.getDuration(value, TimeUnitType)` để tạo thời lượng ở đơn vị mong muốn thay vì chuyển đổi sau này.
- **Sai lầm:** Đặt thời lượng âm sẽ gây ra ngoại lệ. Hãy xác thực giá trị đầu vào.

## Kết luận
Trong hướng dẫn này, chúng ta đã đề cập cách **thêm nhiệm vụ vào dự án**, đọc thời lượng mặc định, **đặt thời lượng**, và **chuyển đổi thời lượng** sang các đơn vị thời gian khác nhau. Bây giờ bạn có thể tích hợp các kỹ thuật này vào các ứng dụng lập lịch lớn hơn để lên kế hoạch dự án một cách chính xác.

## Câu Hỏi Thường Gặp
### Aspose.Tasks có tương thích với tất cả các phiên bản Java không?
Aspose.Tasks tương thích với Java 6 và các phiên bản sau này.

### Tôi có thể sử dụng Aspose.Tasks cho các dự án thương mại không?
Có, bạn có thể sử dụng Aspose.Tasks cho cả dự án cá nhân và thương mại. Tham khảo chi tiết giấy phép [tại đây](https://purchase.aspose.com/buy).

### Tôi có thể tìm hỗ trợ và tài nguyên bổ sung ở đâu?
Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận hỗ trợ cộng đồng và thảo luận.

### Làm sao để lấy giấy phép tạm thời cho mục đích thử nghiệm?
Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/) để thử nghiệm và đánh giá.

### Có bản dùng thử miễn phí cho Aspose.Tasks không?
Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/) để khám phá Aspose.Tasks trước khi mua.

## Câu Hỏi Thường Gặp

**Q: Làm thế nào để thay đổi thời lượng của một nhiệm vụ sau khi đã đặt?**  
A: Lấy thời lượng hiện tại bằng `task.get(Tsk.DURATION)`, chỉnh sửa nó (ví dụ: `add`, `subtract`, hoặc `convert`), và sau đó đặt lại bằng `task.set(Tsk.DURATION, newDuration)`.

**Q: Tôi có thể đặt thời lượng tính bằng phút không?**  
A: Có, sử dụng `TimeUnitType.Minute` khi gọi `project.getDuration(value, TimeUnitType.Minute)`.

**Q: Thay đổi thời lượng có tự động cập nhật ngày bắt đầu và ngày kết thúc của nhiệm vụ không?**  
A: Chỉ khi chế độ lập lịch của dự án được đặt là tự động. Nếu không, bạn có thể cần tính lại lịch bằng `project.calculateCriticalPath()`.

**Q: Có thể lấy thời lượng dưới dạng số nguyên thô không?**  
A: Gọi `duration.getTimeSpan()` để nhận giá trị số trong đơn vị thời gian hiện tại.

**Q: Điều gì sẽ xảy ra nếu tôi trừ đi thời lượng lớn hơn thời lượng hiện tại?**  
A: API sẽ ném ra `ArgumentOutOfRangeException`. Luôn xác thực để thời lượng kết quả vẫn dương.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}