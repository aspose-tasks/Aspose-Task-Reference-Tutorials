---
date: 2025-12-20
description: Tìm hiểu cách sử dụng Aspose.Tasks để trích xuất chi tiết lịch dự án
  từ các tệp Microsoft Project bằng Java. Hướng dẫn từng bước kèm ví dụ mã.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách sử dụng Aspose.Tasks để lấy thông tin lịch của MS Project
url: /vi/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Sử Dụng Aspose.Tasks Để Lấy Thông Tin Lịch Trình MS Project

## Giới Thiệu
Trong hướng dẫn này, **bạn sẽ khám phá cách sử dụng Aspose.Tasks** để lập trình lấy thông tin lịch trình từ các tệp Microsoft Project. Truy cập dữ liệu lịch như ngày làm việc, giờ làm và các ngoại lệ là rất quan trọng khi bạn cần **trích xuất lịch dự án** cho việc báo cáo, tích hợp hoặc logic lập lịch tùy chỉnh. Hãy cùng đi qua quy trình từng bước.

## Câu Trả Lời Nhanh
- **Thư viện nào được sử dụng trong hướng dẫn này?** Aspose.Tasks for Java.  
- **Từ khóa chính được đề cập là gì?** *how to use aspose.tasks*.  
- **Bạn có thể trích xuất gì?** Lịch dự án, bao gồm ngày làm việc và giờ làm việc.  
- **Tôi có cần giấy phép không?** Có bản dùng thử miễn phí; giấy phép cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc cao hơn.

## Tại Sao cần trích xuất thông tin lịch dự án?
Lịch dự án quyết định ngày thực hiện công việc, phân bổ nguồn lực và tính toán thời gian tổng thể. Bằng cách trích xuất dữ liệu này, bạn có thể:
- Tạo báo cáo tùy chỉnh phản ánh lịch làm việc thực tế.  
- Đồng bộ thời gian Microsoft Project với các hệ thống bên ngoài (ERP, BI, v.v.).  
- Thực hiện phân tích “what‑if” bằng cách thay đổi cài đặt lịch trình một cách lập trình.

## Yêu Cầu Trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

- Kiến thức cơ bản về lập trình Java.  
- Java Development Kit (JDK) đã được cài đặt trên hệ thống của bạn.  
- Thư viện Aspose.Tasks for Java. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/tasks/java/).

## Nhập Gói
Đầu tiên, nhập các lớp Aspose.Tasks cần thiết vào dự án Java của bạn.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Bước 1: Đặt Thư Mục Dữ Liệu
Xác định thư mục chứa tệp *.mpp* của bạn.

```java
String dataDir = "Your Data Directory";
```

Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối tới thư mục chứa **project.mpp**.

## Bước 2: Định Nghĩa Đơn Vị Thời Gian
Tạo các hằng số giúp chuyển đổi biểu diễn thời gian nội bộ sang giờ có thể đọc được bởi con người.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Các giá trị này được biểu thị bằng microseconds, là cách Aspose.Tasks lưu trữ thời gian bên trong.

## Bước 3: Tạo Đối Tượng Project
Tải tệp Microsoft Project vào một đối tượng `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Bộ khởi tạo `Project` sẽ phân tích tệp *.mpp* và làm cho tất cả dữ liệu dự án, bao gồm lịch, có thể truy cập thông qua API.

## Bước 4: Lấy Thông Tin Lịch Trình
Lấy tập hợp các lịch được định nghĩa trong dự án.

```java
CalendarCollection alCals = project.getCalendars();
```

Một dự án có thể chứa nhiều lịch (lịch chuẩn, lịch nguồn lực và lịch tùy chỉnh). Tập hợp này cho phép bạn truy cập từng lịch một.

## Bước 5: Duyệt Qua Các Lịch Trình
Lặp qua mọi lịch, hiển thị UID, tên và các ngày làm việc cùng với giờ làm việc tương ứng.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Vòng lặp bên trong kiểm tra từng đối tượng `WeekDay`. Nếu ngày được đánh dấu là ngày làm việc, nó sẽ in loại ngày (Monday, Tuesday, …) cùng với số giờ làm việc đã tính.

## Bước 6: Hiển Thị Thông Báo Hoàn Thành
Thông báo rằng quá trình trích xuất đã kết thúc.

```java
System.out.println("Process completed Successfully");
```

## Kết Luận
Bằng cách thực hiện các bước trên, **bây giờ bạn đã biết cách sử dụng Aspose.Tasks để trích xuất thông tin lịch dự án** từ tệp MS Project bằng Java. Bạn có thể tích hợp logic này vào các ứng dụng lớn hơn, tự động hoá báo cáo, hoặc đồng bộ lịch với các hệ thống doanh nghiệp khác.

## Câu Hỏi Thường Gặp

**Q: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
A: Có, Aspose.Tasks hỗ trợ nhiều nền tảng và ngôn ngữ lập trình, bao gồm .NET, C++, Python và Java.

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks không?**  
A: Có, bạn có thể tải phiên bản dùng thử miễn phí từ [đây](https://releases.aspose.com/).

**Q: Làm sao tôi có thể nhận được hỗ trợ cho Aspose.Tasks?**  
A: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks [đây](https://forum.aspose.com/c/tasks/15).

**Q: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks không?**  
A: Có, giấy phép tạm thời có sẵn để mua [đây](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks ở đâu?**  
A: Bạn có thể tham khảo tài liệu [đây](https://reference.aspose.com/tasks/java/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}