---
date: 2025-12-02
description: Tìm hiểu cách thiết lập lịch, định nghĩa các ngày trong tuần trong MS
  Project và thiết lập ngày làm việc tùy chỉnh bằng Aspose.Tasks cho Java. Lưu dự
  án dưới dạng XML chỉ với vài dòng mã.
language: vi
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách thiết lập lịch và xác định các ngày trong tuần trong MS Project bằng Aspose.Tasks
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Lịch và Xác Định Ngày Trong Tuần trong MS Project với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách đặt lịch** một cách lập trình và xác định các ngày trong tuần trong tệp Microsoft Project bằng cách sử dụng thư viện Aspose.Tasks cho Java. Cho dù bạn cần tạo một tuần làm việc tiêu chuẩn, thêm ngày làm việc cuối tuần, hoặc cấu hình lịch ngắn cho thứ Sáu, hướng dẫn này sẽ dẫn bạn qua từng bước — từ việc tạo dự án đến lưu tệp dưới dạng XML.

## Câu trả lời nhanh
- **Thư viện nào cần thiết?** Aspose.Tasks for Java  
- **Tôi có thể thêm ngày làm việc cuối tuần không?** Có – chỉ cần thêm Thứ Bảy và Chủ Nhật làm ngày làm việc.  
- **Làm thế nào để lưu dự án?** Sử dụng `prj.save(..., SaveFileFormat.Xml)`.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; cần giấy phép cho môi trường sản xuất.  
- **Phiên bản Java yêu cầu là gì?** Java 8 hoặc cao hơn.

## “Cách đặt lịch” là gì trong ngữ cảnh của MS Project?
Đặt lịch trong MS Project có nghĩa là xác định những ngày nào là ngày làm việc, giờ làm việc hàng ngày, và bất kỳ ngoại lệ nào như ngày lễ. Lịch này điều khiển việc lên lịch nhiệm vụ, phân bổ nguồn lực và toàn bộ thời gian dự án.

## Tại sao nên sử dụng Aspose.Tasks để thao tác lịch?
- **Kiểm soát đầy đủ** – tạo, sửa đổi hoặc xóa lịch một cách lập trình mà không cần mở giao diện người dùng.  
- **Đa nền tảng** – hoạt động trên bất kỳ hệ điều hành nào hỗ trợ Java.  
- **Hỗ trợ tất cả các định dạng tệp** – MPP, MPT và XML, vì vậy bạn có thể *lưu dự án dưới dạng XML* để dễ dàng tích hợp với các hệ thống khác.  
- **Không phụ thuộc vào COM** – không giống như thư viện Microsoft Project Interop.

## Yêu cầu trước
1. **Java Development Kit (JDK) 8+** – tải xuống từ [trang web Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – lấy JAR mới nhất từ [trang tải xuống Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Một IDE hoặc công cụ xây dựng (Maven/Gradle) để thêm JAR Aspose.Tasks vào classpath của dự án.

## Nhập các gói
Đầu tiên, nhập các lớp bạn sẽ cần. Những import này cho phép bạn truy cập vào các đối tượng project, calendar và working‑time objects.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Hướng dẫn từng bước

### Bước 1: Tạo một Instance Dự án
Tạo một đối tượng `Project` mới. Đối tượng này đại diện cho tệp MS Project mà bạn sẽ chỉnh sửa.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Bước 2: Định nghĩa một Lịch mới
Thêm một lịch mới vào dự án. Đặt tên rõ ràng giúp khi bạn có nhiều lịch.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Bước 3: Thêm các Ngày Làm việc Tiêu chuẩn (Thứ Hai‑Thứ Năm)
Sử dụng hàm trợ giúp tích hợp `WeekDay.createDefaultWorkingDay` để đặt lịch làm việc mặc định từ 9 am‑5 pm cho tuần làm việc cốt lõi.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Bước 4: Thêm Ngày Làm việc Cuối tuần
Nếu dự án của bạn chạy vào cuối tuần, chỉ cần thêm Thứ Bảy và Chủ Nhật làm ngày làm việc thường. Điều này minh họa **thêm ngày làm việc cuối tuần**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Bước 5: Đặt Ngày Làm việc Ngắn Tùy chỉnh (Thứ Sáu)
Ở đây chúng ta **đặt ngày làm việc tùy chỉnh** cho thứ Sáu: ca sáng (9 am‑12 pm) và ca chiều (1 pm‑4 pm).

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Bước 6: Lưu Dự án dưới dạng XML
Cuối cùng, lưu các thay đổi. Tùy chọn `SaveFileFormat.Xml` cho phép bạn **lưu dự án dưới dạng XML**, hữu ích cho việc tích hợp với các công cụ khác.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Các vấn đề thường gặp & Giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Thời gian làm việc không được áp dụng** | Đảm bảo `setDayWorking(true)` được gọi trên `WeekDay` tùy chỉnh. |
| **Không tìm thấy tệp khi lưu** | Xác minh rằng `dataDir` trỏ tới một thư mục tồn tại và ứng dụng của bạn có quyền ghi. |
| **Lịch không được phản ánh trong các nhiệm vụ** | Gán lịch mới tạo cho tài nguyên hoặc nhiệm vụ bằng cách sử dụng `task.setCalendar(cal)`. |

## Câu hỏi thường gặp

**Q: Tôi có thể định nghĩa ngày không làm việc tùy chỉnh bằng Aspose.Tasks cho Java không?**  
A: Có. Đặt thuộc tính `DayWorking` thành `false` cho bất kỳ `WeekDay` nào bạn muốn coi là ngày không làm việc.

**Q: Làm thế nào tôi có thể thêm ngày lễ hoặc ngoại lệ toàn công ty?**  
A: Tạo các đối tượng `CalendarException`, chỉ định các ngày ngoại lệ, và thêm chúng vào `cal.getExceptions()`.

**Q: Thư viện có tương thích với các phiên bản MS Project cũ không?**  
A: Hoàn toàn. Aspose.Tasks hỗ trợ các định dạng MPP, MPT và XML trên nhiều phiên bản Project.

**Q: Tôi có thể chỉnh sửa một lịch hiện có trong dự án đã nhập không?**  
A: Tải dự án bằng `new Project("existing.mpp")`, lấy lịch mong muốn, thực hiện thay đổi và lưu lại.

**Q: Aspose.Tasks có xử lý các nhiệm vụ lặp lại không?**  
A: Có, bạn có thể tạo và chỉnh sửa các nhiệm vụ lặp lại bằng lớp `RecurringTask`.

## Kết luận
Bây giờ bạn đã biết **cách đặt lịch** trong MS Project, **xác định các ngày trong tuần**, thêm ngày làm việc cuối tuần và tạo lịch ngắn cho thứ Sáu — tất cả đều bằng Aspose.Tasks cho Java. Lưu kết quả dưới dạng XML và tích hợp logic lịch vào bất kỳ giải pháp quản lý dự án nào dựa trên Java.

---

**Cập nhật lần cuối:** 2025-12-02  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}