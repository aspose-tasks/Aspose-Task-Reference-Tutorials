---
date: 2026-08-08
description: Tìm hiểu cách thiết lập lịch ms project, đặt giờ làm việc hàng ngày và
  thêm các ngày làm việc cuối tuần bằng Aspose.Tasks cho Java. Lưu dự án dưới dạng
  XML chỉ trong vài dòng mã.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Cách thiết lập lịch ms project và xác định các ngày trong tuần
og_description: Thiết lập lịch ms project, xác định các ngày trong tuần và thêm các
  ngày làm việc cuối tuần bằng Aspose.Tasks cho Java. Thực hiện theo hướng dẫn từng
  bước và lưu dưới dạng XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Thiết lập lịch ms project với Aspose.Tasks – Hướng dẫn Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Cách thiết lập lịch ms project và xác định các ngày trong tuần
url: /vi/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thiết lập lịch ms project và xác định các ngày trong tuần

Trong hướng dẫn này, bạn sẽ học **how to set calendar ms project** một cách lập trình, xác định các ngày trong tuần và cấu hình các ngày làm việc tùy chỉnh bằng thư viện Aspose.Tasks cho Java. Cho dù bạn đang xây dựng một công cụ lập lịch, tích hợp với hệ thống ERP, hoặc chỉ cần tạo một kế hoạch dự án mà không mở Microsoft Project, các bước dưới đây sẽ cho bạn thấy cách tạo lịch, thiết lập giờ làm việc hàng ngày và thêm các ngày làm việc cuối tuần chỉ trong vài dòng mã.

## Câu trả lời nhanh
- **Thư viện nào được yêu cầu?** Aspose.Tasks for Java.  
- **Tôi có thể thêm ngày làm việc cuối tuần không?** Có – chỉ cần đánh dấu Thứ Bảy và Chủ Nhật là ngày làm việc.  
- **Làm thế nào để lưu dự án?** Gọi `prj.save(..., SaveFileFormat.Xml)`.  
- **Cần có giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; cần giấy phép cho việc sử dụng trong môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc cao hơn.

## Set calendar ms project là gì?
Việc thiết lập lịch trong MS Project xác định những ngày nào được coi là ngày làm việc, số giờ làm việc mỗi ngày, và bất kỳ ngoại lệ đặc biệt nào như ngày lễ hoặc đóng cửa toàn công ty. Thông tin này điều khiển việc lên lịch công việc, phân bổ nguồn lực và thời gian tổng thể của dự án, đảm bảo các phép tính tôn trọng mô hình làm việc thực tế của tổ chức.

## Tại sao nên sử dụng Aspose.Tasks để thao tác lịch?
Aspose.Tasks cung cấp cho bạn khả năng kiểm soát lịch một cách lập trình mà không cần khởi chạy giao diện Microsoft Project. Nó chạy trên bất kỳ hệ điều hành nào hỗ trợ Java, hỗ trợ hơn 50 định dạng nhập và xuất, và có thể xử lý các dự án hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, làm cho nó trở nên lý tưởng cho tự động hoá phía máy chủ.

## Yêu cầu trước
- **Java Development Kit (JDK) 8+** – tải xuống từ [trang web Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – lấy JAR mới nhất từ [trang tải xuống Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
- Một IDE hoặc công cụ xây dựng (Maven/Gradle) để thêm JAR Aspose.Tasks vào classpath của bạn.

## Nhập gói
Nhập các lớp cung cấp quyền truy cập vào dự án, lịch và các đối tượng thời gian làm việc.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Hướng dẫn từng bước

### Bước 1: tạo một thể hiện dự án
Khởi tạo một đối tượng `Project`, đại diện cho tệp MS Project mà bạn sẽ thao tác.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Bước 2: định nghĩa một lịch mới
`Calendar` đại diện cho một tập hợp thời gian làm việc, ngoại lệ và ngày lễ cho một dự án.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Bước 3: thêm các ngày làm việc tiêu chuẩn (Thứ Hai‑Thứ Năm)
`WeekDay` xác định thời gian làm việc cho một ngày cụ thể trong tuần.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Bước 4: thêm ngày làm việc cuối tuần
Nếu dự án của bạn chạy vào cuối tuần, hãy thêm Thứ Bảy và Chủ Nhật làm các ngày làm việc thường xuyên. Điều này minh họa **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Bước 5: thiết lập ngày làm việc ngắn tùy chỉnh (Thứ Sáu)
Cấu hình Thứ Sáu với ca sáng (9 am‑12 pm) và ca chiều (1 pm‑4 pm) để minh họa **set daily working hours** và một ngày làm việc ngắn tùy chỉnh.

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

### Bước 6: lưu dự án dưới dạng XML
`SaveFileFormat` liệt kê các định dạng tệp được hỗ trợ khi lưu dự án, chẳng hạn như XML hoặc MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Các vấn đề thường gặp & giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Thời gian làm việc không được áp dụng** | Đảm bảo `setDayWorking(true)` được gọi trên mỗi `WeekDay` tùy chỉnh. |
| **Không tìm thấy tệp khi lưu** | Xác minh rằng `dataDir` trỏ đến một thư mục tồn tại và ứng dụng có quyền ghi. |
| **Lịch không được phản ánh trong các công việc** | Gán lịch mới tạo cho tài nguyên hoặc công việc bằng cách sử dụng `task.setCalendar(cal)`. |

## Câu hỏi thường gặp

**Q: Tôi có thể định nghĩa các ngày không làm việc tùy chỉnh bằng Aspose.Tasks cho Java không?**  
A: Có. Đặt thuộc tính `DayWorking` thành `false` cho bất kỳ `WeekDay` nào bạn muốn coi là ngày không làm việc.

**Q: Làm thế nào tôi có thể thêm ngày lễ hoặc ngoại lệ toàn công ty?**  
A: Tạo các đối tượng `CalendarException`, chỉ định các ngày ngoại lệ, và thêm chúng vào `cal.getExceptions()`.

**Q: Thư viện có tương thích với các phiên bản MS Project cũ không?**  
A: Hoàn toàn. Aspose.Tasks hỗ trợ các định dạng MPP, MPT và XML trên nhiều phiên bản Project.

**Q: Tôi có thể sửa đổi một lịch hiện có trong dự án đã nhập không?**  
A: Tải dự án bằng `new Project("existing.mpp")`, lấy lịch mong muốn, thực hiện thay đổi và lưu.

**Q: Aspose.Tasks có xử lý các công việc lặp lại không?**  
A: Có, bạn có thể tạo và chỉnh sửa các công việc lặp lại bằng lớp `RecurringTask`.

## Kết luận
Bạn giờ đã biết **how to set calendar ms project**, định nghĩa các ngày trong tuần, thêm ngày làm việc cuối tuần và cấu hình lịch ngắn cho Thứ Sáu — tất cả đều với Aspose.Tasks cho Java. Lưu kết quả dưới dạng XML và tích hợp logic lịch vào bất kỳ giải pháp quản lý dự án dựa trên Java nào.

---

**Cập nhật lần cuối:** 2026-08-08  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Thêm lịch vào dự án với Aspose.Tasks cho Java](/tasks/java/calendars/create/)
- [Xác định Ngày làm việc & Giờ làm việc với Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Thêm ngày lễ vào lịch và lưu dưới dạng MPP với Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}