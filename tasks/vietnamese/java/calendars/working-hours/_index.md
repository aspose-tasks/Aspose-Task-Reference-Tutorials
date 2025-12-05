---
date: 2025-12-05
description: Tìm hiểu cách xác định ngày làm việc và tính thời gian thực hiện nhiệm
  vụ bằng cách trích xuất giờ làm việc từ lịch MS Project bằng Aspose.Tasks cho Java.
language: vi
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Xác định ngày làm việc và giờ làm việc với Aspose.Tasks
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xác Định Ngày Làm Việc & Giờ Làm Việc với Aspose.Tasks

## Giới thiệu
Quản lý lịch dự án là một phần cốt lõi của việc lập kế hoạch dự án thành công. Trong hướng dẫn này, bạn sẽ **xác định ngày làm việc** cho bất kỳ nhiệm vụ nào và **trích xuất giờ làm việc** từ lịch MS Project bằng Aspose.Tasks for Java. Khi kết thúc hướng dẫn, bạn sẽ có thể **tính toán thời lượng nhiệm vụ**, tùy chỉnh giờ làm việc, và một cách đáng tin cậy **tải tệp MPP** để lấy dữ liệu cần thiết.

## Câu trả lời nhanh
- **Xác định ngày làm việc có nghĩa là gì?** Nó có nghĩa là xác định những ngày trong lịch được coi là ngày làm việc cho một nhiệm vụ nhất định.  
- **Thư viện nào tôi nên sử dụng?** Aspose.Tasks for Java cung cấp một API đầy đủ tính năng để làm việc với các tệp MS Project.  
- **Thời gian thực hiện mất bao lâu?** Thông thường mất 10–15 phút cho một việc trích xuất cơ bản.  
- **Tôi có cần giấy phép không?** Có sẵn bản dùng thử miễn phí; giấy phép thương mại là bắt buộc cho việc sử dụng trong môi trường sản xuất.  
- **Tôi có thể tùy chỉnh giờ làm việc không?** Có – bạn có thể chỉnh sửa lịch, thêm ngày nghỉ, và đặt các khoảng thời gian làm việc tùy chỉnh.  

## “Xác định ngày làm việc” là gì?
Khi một nhiệm vụ được lên lịch, lịch dự án xác định ngày nào là ngày làm việc và ngày nào không làm việc (cuối tuần, ngày lễ). Xác định ngày làm việc có nghĩa là truy vấn lịch đó để biết chính xác thời điểm nào có thể thực hiện công việc, điều này rất quan trọng cho các phép **tính toán thời lượng nhiệm vụ** chính xác.

## Tại sao nên dùng Aspose.Tasks để lấy giờ làm việc?
- **Không cần Microsoft Project** – làm việc với các tệp .MPP trên bất kỳ nền tảng nào.  
- **Hỗ trợ đầy đủ lịch** – bao gồm lịch mặc định, lịch tài nguyên và lịch nhiệm vụ.  
- **Hiệu năng cao** – xử lý các dự án lớn nhanh chóng.  
- **Tài liệu phong phú** – các ví dụ và tham chiếu API có sẵn.  

## Yêu cầu trước
1. **Java Development Kit (JDK)** – phiên bản 8 trở lên.  
2. **Aspose.Tasks for Java** – tải JAR mới nhất từ [here](https://releases.aspose.com/tasks/java).  
3. Kiến thức cơ bản về lập trình Java.  

## Nhập khẩu các gói
Đầu tiên, nhập namespace cốt lõi của Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Bước 1: Tải tệp MPP
Tải tệp dự án của bạn (bước **load mpp file**) để bạn có thể làm việc với các lịch của nó:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Bước 2: Lấy thông tin Nhiệm vụ và Lịch
Chọn nhiệm vụ bạn muốn phân tích và lấy lịch liên quan của nó. Đây là nơi chúng ta **truy xuất giờ làm việc** cho nhiệm vụ:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Bước 3: Xác định Ngày Bắt đầu và Kết thúc
Thiết lập khoảng thời gian mà bạn muốn **xác định ngày làm việc**:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Bước 4: Lặp qua các Ngày
Lặp qua mỗi ngày trong thời lượng của nhiệm vụ. Vòng lặp này sẽ giúp chúng ta **tùy chỉnh giờ làm việc** sau này nếu cần:

```java
java.util.Calendar tempDate = calStartDate;
```

## Bước 5: Tính Thời Lượng
Trong quá trình lặp, chúng ta kiểm tra mỗi ngày có phải là ngày làm việc không, cộng tổng giờ làm việc, và cuối cùng tính thời lượng của nhiệm vụ bằng phút, giờ và ngày:

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

## Các vấn đề thường gặp và giải pháp
| Issue | Solution |
|-------|----------|
| **Nhiệm vụ trả về `null` cho lịch** | Đảm bảo nhiệm vụ thực sự được gán lịch; nếu không, nó sẽ kế thừa lịch mặc định của dự án. |
| **Thời lượng không đúng do ngày nghỉ** | Xác minh rằng các ngày nghỉ được định nghĩa trong lịch của nhiệm vụ hoặc trong lịch cơ bản của dự án. |
| **Không khớp múi giờ** | Sử dụng `java.util.TimeZone` để đồng bộ múi giờ của lịch với hệ thống của bạn nếu cần. |

## Câu hỏi thường gặp
### Q: Aspose.Tasks for Java có thể xử lý cấu trúc dự án phức tạp không?
A: Có, Aspose.Tasks for Java cung cấp hỗ trợ toàn diện cho việc xử lý các cấu trúc dự án phức tạp, bao gồm nhiệm vụ, tài nguyên và lịch.

### Q: Aspose.Tasks for Java có tương thích với các phiên bản khác nhau của MS Project không?
A: Chắc chắn, Aspose.Tasks for Java hỗ trợ nhiều phiên bản của MS Project, đảm bảo tính tương thích trên các môi trường khác nhau.

### Q: Tôi có thể tùy chỉnh giờ làm việc và ngày nghỉ trong lịch dự án không?
A: Có, bạn có thể dễ dàng tùy chỉnh giờ làm việc và ngày nghỉ theo yêu cầu dự án của mình bằng các API của Aspose.Tasks for Java.

### Q: Aspose.Tasks for Java có cung cấp hỗ trợ và tài liệu không?
A: Có, Aspose.Tasks for Java cung cấp tài liệu phong ph và các diễn đàn hỗ trợ chuyên dụng để giúp các các tính năng một cách hiệu quả.

### Q: Có phiên bản dùng thử cho Aspose.Tasks for Java không?
A: Có, bạn có thể truy cập phiên bản dùng thử miễn phí của Aspose.Tasks for Java từ [here](https://releases.aspose.com/).

## Kết luận
Trong hướng dẫn này, chúng tôi đã trình bày cách **xác định ngày làm việc**, **truy xuất giờ làm việc**, và **tính toán thời lượng nhiệm vụ** từ lịch MS Project bằng Aspose.Tasks for Java. Bằng cách làm theo các bước trên, bạn có thể tự động hoá việc phân tích lịch trình, tùy chỉnh lịch và giữ cho kế hoạch dự án của bạn luôn chính xác và cập nhật.

---

**Cập nhật lần cuối:** 2025-12-05  
**Kiểm thử với:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}