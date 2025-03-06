---
title: Xác định các ngày trong tuần trong Lịch với Aspose.Tasks
linktitle: Xác định các ngày trong tuần trong Lịch với Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách xác định các ngày trong tuần trong Lịch MS Project bằng Aspose.Tasks cho Java. Tùy chỉnh ngày làm việc và thời gian một cách dễ dàng.
weight: 12
url: /vi/java/calendars/define-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xác định các ngày trong tuần trong Lịch với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu quy trình xác định các ngày trong tuần trong Lịch MS Project bằng cách sử dụng Aspose.Tasks cho Java. Aspose.Tasks là một thư viện Java mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project theo chương trình.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình. Bạn có thể tải nó xuống từ[Trang web của Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) nếu bạn chưa làm vậy.
2.  Aspose.Tasks for Java Library: Tải xuống và cài đặt thư viện Aspose.Tasks for Java từ[trang tải xuống](https://releases.aspose.com/tasks/java/). Thực hiện theo các hướng dẫn cài đặt được cung cấp trong tài liệu.

## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói cần thiết để làm việc với Aspose.Tasks trong dự án Java của bạn:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Bước 1: Tạo một phiên bản dự án
Khởi tạo một đối tượng Project, đại diện cho tệp MS Project mà bạn sẽ làm việc với:
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Bước 2: Xác định Lịch
Tạo một phiên bản lịch mới và thêm nó vào dự án:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Bước 3: Thêm ngày làm việc
Xác định ngày làm việc bằng cách thêm từ Thứ Hai đến Thứ Năm với thời gian mặc định:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Bước 4: Đặt ngày làm việc tùy chỉnh
Xác định thứ bảy và chủ nhật là ngày làm việc:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Bước 5: Đặt ngày làm việc ngắn
Đặt Thứ Sáu là một ngày làm việc ngắn với thời gian làm việc tùy chỉnh:
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
## Bước 6: Lưu dự án
Lưu dự án đã sửa đổi vào tệp XML:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Phần kết luận
Chúc mừng! Bạn đã xác định thành công các ngày trong tuần trong Lịch MS Project bằng Aspose.Tasks cho Java. Bây giờ bạn có thể tích hợp chức năng này vào các ứng dụng Java của mình để thao tác với các tệp MS Project theo chương trình.
## Câu hỏi thường gặp
### Câu hỏi 1: Tôi có thể xác định những ngày không làm việc tùy chỉnh bằng Aspose.Tasks cho Java không?
 Trả lời: Có, bạn có thể xác định những ngày không làm việc tùy chỉnh bằng cách đặt`DayWorking` tài sản để`false` cho ngày trong tuần tương ứng.
### Q2: Làm cách nào để thêm ngày nghỉ vào lịch?
 Đáp: Bạn có thể thêm ngày nghỉ bằng cách tạo các phiên bản của`CalendarExceptions`và chỉ định những ngày không làm việc.
### Câu hỏi 3: Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp MS Project không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp MS Project, bao gồm các định dạng MPP, MPT và XML.
### Câu hỏi 4: Tôi có thể sửa đổi lịch hiện có trong tệp MS Project không?
Đáp: Có, bạn có thể tải lịch dự án hiện có, thực hiện sửa đổi và sau đó lưu các thay đổi trở lại tệp gốc.
### Câu hỏi 5: Aspose.Tasks có hỗ trợ các tác vụ định kỳ không?
Trả lời: Có, Aspose.Tasks cho phép bạn làm việc với các tác vụ định kỳ, bao gồm cả việc xác định mô hình và thời lượng lặp lại của chúng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
