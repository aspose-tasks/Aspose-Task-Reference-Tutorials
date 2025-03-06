---
title: Truy xuất thông tin lịch dự án MS trong Aspose.Tasks
linktitle: Truy xuất thông tin lịch trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách truy xuất thông tin lịch MS Project bằng Aspose.Tasks cho Java. Hướng dẫn từng bước để truy cập chi tiết lịch theo chương trình.
type: docs
weight: 14
url: /vi/java/project-file-operations/retrieve-calendar-info/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách truy xuất thông tin lịch từ các tệp Microsoft Project bằng thư viện Aspose.Tasks cho Java. Aspose.Tasks cung cấp các tính năng mạnh mẽ để thao tác dữ liệu dự án, bao gồm truy cập các chi tiết lịch như ngày và giờ làm việc.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:
- Kiến thức cơ bản về lập trình Java.
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Aspose.Tasks cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).
## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết trong mã Java của mình để sử dụng các chức năng của Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Bây giờ hãy chia ví dụ được cung cấp thành nhiều bước để hiểu rõ hơn.
## Bước 1: Đặt thư mục dữ liệu
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"` với đường dẫn đến thư mục tệp dự án của bạn.
## Bước 2: Xác định đơn vị thời gian
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Các hằng số này biểu thị đơn vị thời gian tính bằng micro giây.
## Bước 3: Tạo phiên bản dự án
```java
Project project = new Project(dataDir + "project.mpp");
```
 Dòng này tạo ra một thể hiện của`Project` class, khởi tạo nó bằng đường dẫn đến tệp dự án (`project.mpp`).
## Bước 4: Truy xuất thông tin lịch
```java
CalendarCollection alCals = project.getCalendars();
```
Ở đây, chúng tôi truy xuất một tập hợp các lịch có trong tệp dự án.
## Bước 5: Lặp lại lịch
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Thông tin lịch
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Lặp lại các ngày trong tuần
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Thời gian tính bằng mili giây
            double time = ts / (OneHour); // Chuyển đổi sang giờ
            if (wd.getDayWorking()) {
                // Hiển thị ngày và giờ làm việc
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Vòng lặp này lặp qua từng lịch và in UID, tên và ngày làm việc với giờ làm việc tương ứng.
## Bước 6: Hiển thị thông báo hoàn thành
```java
System.out.println("Process completed Successfully");
```
Cuối cùng, một thông báo được hiển thị cho biết quá trình đã hoàn tất.
## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách truy xuất thông tin lịch từ các tệp MS Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn có thể truy cập và thao tác dữ liệu dự án một cách hiệu quả trong các ứng dụng Java của mình.

## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều nền tảng và ngôn ngữ lập trình, bao gồm .NET, C++, Python và Java.
### Câu hỏi: Aspose.Tasks có bản dùng thử miễn phí không?
 Đ: Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks?
Trả lời: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks không?
 Đáp: Có, giấy phép tạm thời có sẵn để mua[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Tôi có thể tìm tài liệu chi tiết về Aspose.Tasks ở đâu?
 Đáp: Bạn có thể tham khảo tài liệu[đây](https://reference.aspose.com/tasks/java/).