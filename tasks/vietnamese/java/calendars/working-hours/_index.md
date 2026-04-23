---
date: 2026-02-05
description: Tìm hiểu cách xác định ngày làm việc và tính thời gian thực hiện nhiệm
  vụ bằng cách trích xuất giờ làm việc từ lịch MS Project bằng Aspose.Tasks cho Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Xác định ngày làm việc và giờ làm việc với Aspose.Tasks
url: /vi/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xác Định Ngày Làm Việc & Giờ Làm Việc với Aspose.Tasks

## Giới thiệu
Quản lý lịch dự án là một phần cốt lõi của việc lập kế hoạch dự án thành công. Trong hướng dẫn này, bạn sẽ **xác định ngày làm việc** cho bất kỳ nhiệm vụ nào và **trích xuất giờ làm việc** từ lịch MS Project bằng Aspose.Tasks cho Java. Khi hoàn thành, bạn sẽ có khả năng **tính thời lượng nhiệm vụ**, tùy chỉnh giờ làm việc, và **tải tệp MPP** một cách đáng tin cậy để lấy dữ liệu cần thiết. Bạn cũng sẽ thấy cách **đọc tệp MS Project** mà không cần cài đặt Microsoft Project, giúp tự động hoá trên bất kỳ nền tảng nào.

## Câu trả lời nhanh
- **“Xác định ngày làm việc” có nghĩa là gì?** Nó có nghĩa là xác định những ngày trong lịch được coi là ngày làm việc cho một nhiệm vụ cụ thể.  
- **Tôi nên dùng thư viện nào?** Aspose.Tasks cho Java cung cấp API đầy đủ tính năng để làm việc với tệp MS Project.  
- **Thời gian thực hiện khoảng bao lâu?** Thường khoảng 10–15 phút cho một việc trích xuất cơ bản.  
- **Tôi có cần giấy phép không?** Có phiên bản dùng thử miễn phí; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể tùy chỉnh giờ làm việc không?** Có – bạn có thể chỉnh sửa lịch, thêm ngày nghỉ lễ và đặt các khoảng thời gian làm việc tùy chỉnh.  

## “Xác định ngày làm việc” là gì?
Khi một nhiệm vụ được lên lịch, lịch dự án xác định ngày nào là ngày làm việc và ngày nào không làm việc (cuối tuần, ngày lễ). Xác định ngày làm việc có nghĩa là truy vấn lịch đó để biết chính xác thời điểm công việc có thể diễn ra, điều này rất quan trọng cho việc **tính thời lượng nhiệm vụ** một cách chính xác.

## Tại sao nên dùng Aspose.Tasks để lấy giờ làm việc?
- **Không cần Microsoft Project** – bạn có thể đọc tệp MS Project trực tiếp từ mã Java.  
- **Hỗ trợ đầy đủ lịch** – bao gồm lịch mặc định, lịch nguồn lực và lịch nhiệm vụ.  
- **Hiệu suất cao** – xử lý các dự án lớn nhanh chóng.  
- **Tài liệu phong phú** – ví dụ và tham chiếu API luôn sẵn có.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Java Development Kit (JDK)** – phiên bản 8 trở lên.  
2. **Aspose.Tasks cho Java** – tải JAR mới nhất từ [đây](https://releases.aspose.com/tasks/java/).  
3. Kiến thức cơ bản về lập trình Java.  

## Nhập khẩu các gói
Đầu tiên, nhập không gian tên cốt lõi của Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Cách tải tệp MPP bằng Aspose.Tasks?
Tải tệp dự án là bước đầu tiên cho bất kỳ phân tích lịch nào. API cho phép bạn **tải tệp MPP** chỉ bằng một dòng mã, mà không cần giao diện MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Lấy Thông tin Nhiệm vụ và Lịch
Chọn nhiệm vụ bạn muốn phân tích và lấy lịch liên quan. Đây là nơi chúng ta **truy xuất giờ làm việc** cho nhiệm vụ:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Xác định Ngày Bắt đầu và Kết thúc
Thiết lập cửa sổ thời gian mà bạn muốn **xác định ngày làm việc**. Sử dụng ngày bắt đầu và ngày kết thúc của nhiệm vụ giúp bạn chỉ đánh giá khoảng thời gian liên quan.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Lặp qua các ngày
Duyệt qua từng ngày trong thời gian của nhiệm vụ. Vòng lặp này sẽ giúp chúng ta **tùy chỉnh giờ làm việc** sau này nếu cần:

```java
java.util.Calendar tempDate = calStartDate;
```

## Tính thời lượng
Trong quá trình lặp, chúng ta kiểm tra mỗi ngày có phải là ngày làm việc không, cộng tổng giờ làm việc, và cuối cùng tính thời lượng của nhiệm vụ tính bằng phút, giờ và ngày. Bước này minh họa cách **tính ngày làm việc** và **tính thời lượng nhiệm vụ** một cách lập trình.

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

## Cách tùy chỉnh giờ làm việc và ngày nghỉ lễ
Aspose.Tasks cho phép bạn chỉnh sửa các khoảng thời gian làm việc của lịch và thêm các ngoại lệ như ngày nghỉ lễ. Bạn có thể gọi `taskCalendar.addWorkingTime()` hoặc `taskCalendar.addException()` để điều chỉnh lịch cho phù hợp với chính sách của tổ chức. Điều này hữu ích khi lịch 9‑5 mặc định không phản ánh thực tế.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Nhiệm vụ trả về `null` cho lịch** | Đảm bảo nhiệm vụ thực sự có lịch được gán; nếu không, nó sẽ kế thừa lịch mặc định của dự án. |
| **Thời lượng không chính xác do ngày lễ** | Kiểm tra xem các ngày lễ đã được định nghĩa trong lịch của nhiệm vụ hoặc trong lịch cơ bản của dự án chưa. |
| **Mâu thuẫn múi giờ** | Sử dụng `java.util.TimeZone` để đồng bộ múi giờ của lịch với hệ thống nếu cần. |

## Câu hỏi thường gặp
### Hỏi: Aspose.Tasks cho Java có thể xử lý cấu trúc dự án phức tạp không?
A: Có, Aspose.Tasks cho Java cung cấp hỗ trợ toàn diện cho việc xử lý các cấu trúc dự án phức tạp, bao gồm nhiệm vụ, nguồn lực và lịch.

### Hỏi: Aspose.Tasks cho Java có tương thích với các phiên bản khác nhau của MS Project không?
A: Chắc chắn, Aspose.Tasks cho Java hỗ trợ nhiều phiên bản của MS Project, đảm bảo tính tương thích trên các môi trường khác nhau.

### Hỏi: Tôi có thể tùy chỉnh giờ làm việc và ngày nghỉ lễ trong lịch dự án không?
A: Có, bạn có thể dễ dàng tùy chỉnh giờ làm việc và ngày nghỉ lễ theo yêu cầu dự án bằng các API của Aspose.Tasks cho Java.

### Hỏi: Aspose.Tasks cho Java có cung cấp hỗ trợ và tài liệu không?
A: Có, Aspose.Tasks cho Java cung cấp tài liệu chi tiết và diễn đàn hỗ trợ chuyên dụng để giúp các nhà phát triển tận dụng các tính năng một cách hiệu quả.

### Hỏi: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
A: Có, bạn có thể truy cập phiên bản dùng thử miễn phí của Aspose.Tasks cho Java từ [đây](https://releases.aspose.com/).

## Kết luận
Trong hướng dẫn này, chúng tôi đã minh họa cách **xác định ngày làm việc**, **truy xuất giờ làm việc**, và **tính thời lượng nhiệm vụ** từ lịch MS Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước trên, bạn có thể tự động hoá việc phân tích lịch, tùy chỉnh lịch và duy trì kế hoạch dự án chính xác, luôn cập nhật. Giờ đây, bạn đã có công cụ để **đọc dữ liệu MS Project**, **tải tệp MPP**, và thực hiện các phép tính thời lượng chính xác mà không cần Microsoft Project.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}