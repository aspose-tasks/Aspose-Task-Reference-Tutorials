---
title: Đọc Tuần làm việc từ Lịch dự án MS với Aspose.Tasks
linktitle: Đọc Tuần làm việc từ Lịch với Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách đọc tuần làm việc từ lịch MS Project bằng Aspose.Tasks cho Java. Nhận hướng dẫn từng bước trong hướng dẫn toàn diện này.
weight: 15
url: /vi/java/calendars/read-work-weeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc Tuần làm việc từ Lịch dự án MS với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng Aspose.Tasks cho Java để đọc thông tin về tuần làm việc từ lịch Microsoft Project. Aspose.Tasks là một thư viện Java mạnh mẽ cho phép bạn thao tác và quản lý các tài liệu Microsoft Project theo chương trình.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
2.  Aspose.Tasks cho thư viện Java đã được tải xuống và cài đặt. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).
## Gói nhập khẩu
Trước tiên, hãy nhập các gói cần thiết để bắt đầu với mã của chúng tôi:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## Bước 1: Thiết lập thư mục dữ liệu của bạn
Thiết lập đường dẫn thư mục chứa tệp MS Project của bạn:
```java
String dataDir = "Your Data Directory";
```
## Bước 2: Tạo phiên bản dự án và lịch truy cập
Tạo một phiên bản mới của lớp Project và truy cập vào bộ sưu tập lịch và tuần làm việc:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## Bước 3: Lặp lại các tuần làm việc
Lặp lại qua bộ sưu tập các tuần làm việc và hiển thị thông tin của chúng:
```java
for (WorkWeek workWeek : collection) {
    // Hiển thị tên tuần làm việc, từ và đến ngày
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Truy cập ngày trong tuần và thời gian làm việc
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Xử lý thêm thời gian làm việc nếu cần
    }
}
```
## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách đọc thông tin về tuần làm việc từ lịch Microsoft Project bằng Aspose.Tasks cho Java. Thư viện mạnh mẽ này cho phép thao tác liền mạch các tệp Dự án, cho phép các nhà phát triển tự động hóa nhiều tác vụ khác nhau một cách hiệu quả.
## Câu hỏi thường gặp
### Tôi có thể sửa đổi thông tin về tuần làm việc bằng Aspose.Tasks cho Java không?
Có, Aspose.Tasks cung cấp API để sửa đổi, thêm hoặc xóa các tuần làm việc và thông tin liên quan của chúng.
### Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?
Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm các định dạng MPP và XML.
### Tôi có thể tích hợp Aspose.Tasks với các khung công tác Java khác không?
Hoàn toàn có thể, Aspose.Tasks có thể được tích hợp liền mạch với các khung và thư viện Java khác để nâng cao chức năng.
### Có phiên bản dùng thử cho Aspose.Tasks không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Tasks từ[đây](https://releases.aspose.com/).
### Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?
Bạn có thể tìm thấy sự hỗ trợ và trợ giúp trên diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
