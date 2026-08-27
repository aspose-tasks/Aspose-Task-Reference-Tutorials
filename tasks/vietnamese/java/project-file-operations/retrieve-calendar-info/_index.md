---
date: 2026-03-27
description: Tìm hiểu cách sử dụng Aspose và Aspose.Tasks để trích xuất chi tiết lịch
  dự án từ các tệp Microsoft Project bằng Java. Hướng dẫn từng bước kèm ví dụ mã.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách sử dụng Aspose.Tasks để lấy thông tin lịch MS Project
url: /vi/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Sử Dụng Aspose.Tasks Để Lấy Thông Tin Lịch Trình MS Project

## Giới thiệu
Trong hướng dẫn này, **bạn sẽ khám phá cách sử dụng Aspose.Tasks** để lập trình lấy thông tin lịch trình từ các tệp Microsoft Project. Truy cập dữ liệu lịch như ngày làm việc, giờ làm và các ngoại lệ là rất quan trọng khi bạn cần **trích xuất lịch dự án** cho báo cáo, tích hợp hoặc logic lập lịch tùy chỉnh. Hãy cùng đi qua quy trình từng bước, và bạn sẽ thấy **cách sử dụng Aspose** để lấy dữ liệu này từ tệp *.mpp*.

## Câu trả lời nhanh
- **Thư viện nào được sử dụng trong hướng dẫn này?** Aspose.Tasks for Java.  
- **Từ khóa chính được đề cập là gì?** *how to use aspose*.  
- **Bạn có thể trích xuất gì?** Lịch dự án, bao gồm ngày và giờ làm việc.  
- **Có cần giấy phép không?** Có bản dùng thử miễn phí; giấy phép cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 trở lên.

## Aspose.Tasks là gì và tại sao nên dùng?
Aspose.Tasks là một API Java mạnh mẽ cho phép các nhà phát triển đọc, ghi và thao tác các tệp Microsoft Project mà không cần cài đặt Microsoft Project. Bằng cách sử dụng Aspose.Tasks, bạn có thể **cách trích xuất lịch** thông tin, tự động tính toán lịch trình, và tích hợp dữ liệu dự án với các hệ thống doanh nghiệp khác — tất cả chỉ bằng mã Java thuần.

## Tại sao cần trích xuất thông tin lịch dự án?
Lịch dự án quyết định ngày thực hiện công việc, phân bổ nguồn lực và tính toán tổng thời gian. Bằng cách trích xuất dữ liệu này, bạn có thể:
- Tạo báo cáo tùy chỉnh phản ánh lịch làm việc thực tế.  
- Đồng bộ thời gian của Microsoft Project với các hệ thống bên ngoài (ERP, BI, v.v.).  
- Thực hiện phân tích “what‑if” bằng cách thay đổi cài đặt lịch trình một cách lập trình.  
- **Trích xuất dữ liệu lịch MS Project** để di chuyển sang các công cụ lập kế hoạch khác.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- Kiến thức cơ bản về lập trình Java.  
- Java Development Kit (JDK) được cài đặt trên máy tính.  
- Thư viện Aspose.Tasks for Java. Bạn có thể tải về từ [đây](https://releases.aspose.com/tasks/java/).

## Nhập khẩu các gói
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

Thay `"Your Data Directory"` bằng đường dẫn tuyệt đối tới thư mục chứa **project.mpp**.

## Bước 2: Định Nghĩa Đơn Vị Thời Gian
Tạo các hằng số giúp chuyển đổi biểu diễn thời gian nội bộ sang giờ có thể đọc được.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Các giá trị này được biểu diễn bằng microseconds, là cách Aspose.Tasks lưu trữ thời gian bên trong.

## Bước 3: Tạo Đối Tượng Project
Nạp tệp Microsoft Project vào một đối tượng `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Constructor `Project` sẽ phân tích tệp *.mpp* và cung cấp toàn bộ dữ liệu dự án, bao gồm cả lịch, thông qua API.

## Bước 4: Lấy Thông Tin Lịch
Lấy bộ sưu tập các lịch được định nghĩa trong dự án.

```java
CalendarCollection alCals = project.getCalendars();
```

Một dự án có thể chứa nhiều lịch (lịch tiêu chuẩn, lịch nguồn lực và lịch tùy chỉnh). Bộ sưu tập này cho phép bạn truy cập từng lịch một.

## Bước 5: Duyệt Qua Các Lịch
Lặp qua mỗi lịch, hiển thị UID, tên và các ngày làm việc cùng giờ tương ứng.

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

Vòng lặp bên trong kiểm tra từng đối tượng `WeekDay`. Nếu ngày được đánh dấu là làm việc, nó sẽ in loại ngày (Monday, Tuesday, …) cùng với số giờ làm việc đã tính.

## Bước 6: Hiển Thị Thông Báo Hoàn Thành
Thông báo quá trình trích xuất đã hoàn tất.

```java
System.out.println("Process completed Successfully");
```

## Các Vấn Đề Thường Gặp và Giải Pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| **Không có lịch nào được trả về** | Tệp dự án có thể không chứa lịch tùy chỉnh nào. | Kiểm tra xem *.mpp* thực sự có định nghĩa lịch hay mở nó trong Microsoft Project để xác nhận. |
| **Giờ làm việc không đúng** | Các hằng số chuyển đổi thời gian không phù hợp với phiên bản Project khác. | Điều chỉnh `OneSec`, `OneMin`, `OneHour` nếu bạn dùng phiên bản Aspose.Tasks mới hơn thay đổi đơn vị thời gian nội bộ. |
| **`NullPointerException` ở `cal.getName()`** | Một số đối tượng lịch có thể null. | Thêm kiểm tra null trước khi truy cập thuộc tính (đã được minh họa trong mã). |

## Câu Hỏi Thường Gặp

**H: Tôi có thể dùng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
Đ: Có, Aspose.Tasks hỗ trợ nhiều nền tảng và ngôn ngữ lập trình, bao gồm .NET, C++, Python và Java.

**H: Có bản dùng thử miễn phí cho Aspose.Tasks không?**  
Đ: Có, bạn có thể tải bản dùng thử miễn phí từ [đây](https://releases.aspose.com/).

**H: Làm sao để nhận hỗ trợ cho Aspose.Tasks?**  
Đ: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks [tại đây](https://forum.aspose.com/c/tasks/15).

**H: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks không?**  
Đ: Có, giấy phép tạm thời có thể mua [tại đây](https://purchase.aspose.com/temporary-license/).

**H: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks ở đâu?**  
Đ: Bạn có thể tham khảo tài liệu [tại đây](https://reference.aspose.com/tasks/java/).

## Kết luận
Bằng cách thực hiện các bước trên, **bây giờ bạn đã biết cách sử dụng Aspose.Tasks để trích xuất thông tin lịch dự án** từ tệp MS Project bằng Java. Bạn có thể tích hợp logic này vào các ứng dụng lớn hơn, tự động hoá báo cáo, hoặc đồng bộ lịch trình với các hệ thống doanh nghiệp khác. Hãy nhớ, việc thành thạo **cách sử dụng aspose** mở ra nhiều kịch bản tự động hoá quản lý dự án nâng cao.

---

**Cập nhật lần cuối:** 2026-03-27  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}