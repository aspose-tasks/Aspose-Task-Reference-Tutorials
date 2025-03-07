---
title: Nhận giờ làm việc từ Lịch bằng Aspose.Tasks
linktitle: Nhận giờ làm việc từ Lịch bằng Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Dễ dàng trích xuất giờ làm việc từ lịch MS Project bằng Aspose.Tasks cho Java. Đơn giản hóa nhiệm vụ quản lý dự án.
weight: 13
url: /vi/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nhận giờ làm việc từ Lịch bằng Aspose.Tasks

## Giới thiệu
Quản lý lịch dự án và trích xuất giờ làm việc là điều cần thiết để quản lý dự án hiệu quả. Aspose.Tasks for Java cung cấp chức năng mạnh mẽ để truy xuất giờ làm việc từ lịch MS Project một cách dễ dàng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
2.  Thư viện Aspose.Tasks dành cho Java đã được tải xuống và thêm vào dự án của bạn. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).
3. Hiểu biết cơ bản về ngôn ngữ lập trình Java.
## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết để hoạt động với Aspose.Tasks cho Java:
```java
import com.aspose.tasks.*;
```
## Bước 1: Tải tệp dự án
Bắt đầu bằng cách tải tệp MS Project của bạn:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Bước 2: Truy xuất thông tin nhiệm vụ và lịch
Trích xuất chi tiết nhiệm vụ và lịch từ dự án:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Bước 3: Xác định ngày bắt đầu và ngày kết thúc
Thiết lập ngày bắt đầu và ngày kết thúc cho nhiệm vụ:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Bước 4: Lặp lại các ngày
Lặp lại qua các ngày trong thời gian thực hiện nhiệm vụ:
```java
java.util.Calendar tempDate = calStartDate;
```
## Bước 5: Tính toán thời lượng
Tính thời lượng theo phút, giờ và ngày:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã đề cập đến cách truy xuất giờ làm việc từ lịch MS Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn có thể quản lý lịch trình dự án một cách hiệu quả và tính toán thời hạn thực hiện nhiệm vụ một cách dễ dàng.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks cho Java có thể xử lý các cấu trúc dự án phức tạp không?
Trả lời: Có, Aspose.Tasks cho Java cung cấp hỗ trợ toàn diện để xử lý các cấu trúc dự án phức tạp, bao gồm các tác vụ, tài nguyên và lịch.
### Câu hỏi: Aspose.Tasks dành cho Java có tương thích với các phiên bản khác nhau của MS Project không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks for Java hỗ trợ nhiều phiên bản khác nhau của MS Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.
### Hỏi: Tôi có thể tùy chỉnh giờ làm việc và ngày nghỉ trong lịch dự án không?
Trả lời: Có, bạn có thể dễ dàng tùy chỉnh giờ làm việc và ngày nghỉ theo yêu cầu dự án của mình bằng cách sử dụng Aspose.Tasks dành cho API Java.
### Câu hỏi: Aspose.Tasks dành cho Java có cung cấp hỗ trợ và tài liệu không?
Trả lời: Có, Aspose.Tasks for Java cung cấp tài liệu phong phú và các diễn đàn hỗ trợ chuyên dụng để hỗ trợ các nhà phát triển sử dụng các tính năng của nó một cách hiệu quả.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
 Trả lời: Có, bạn có thể truy cập phiên bản dùng thử miễn phí của Aspose.Tasks cho Java từ[đây](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
