---
date: 2026-08-13
description: Tìm hiểu cách đọc tuần làm việc từ lịch MS Project bằng Aspose.Tasks
  cho Java. Thực hiện theo hướng dẫn từng bước với các ví dụ mã và mẹo khắc phục sự
  cố.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Đọc tuần làm việc từ lịch bằng Aspose.Tasks
og_description: Cách đọc tuần làm việc từ lịch MS Project bằng Aspose.Tasks cho Java.
  Thực hiện theo hướng dẫn ngắn gọn với các bước cài đặt, đoạn mã mẫu và mẹo khắc
  phục sự cố.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Cách đọc tuần làm việc từ lịch MS bằng Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Cách đọc tuần làm việc từ lịch MS bằng Aspose.Tasks
url: /vi/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc tuần làm việc từ lịch MS bằng Aspose.Tasks

## Giới thiệu
Trong tutorial này, bạn sẽ **học cách đọc tuần làm việc** từ lịch Microsoft Project bằng thư viện Aspose.Tasks cho Java. Cho dù bạn đang xây dựng bảng điều khiển báo cáo, đồng bộ lịch trình với hệ thống ERP, hoặc tự động trích xuất dữ liệu cho phân tích, việc truy cập chương trình vào các định nghĩa tuần làm việc giúp tiết kiệm vô số giờ làm thủ công. Aspose.Tasks hỗ trợ **hơn 50 định dạng nhập và xuất** và có thể xử lý các tệp dự án hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại cả tính linh hoạt và hiệu suất.

## Câu trả lời nhanh
- **“Đọc tuần làm việc” có nghĩa là gì?** Nó đề cập đến việc trích xuất các định nghĩa tuần làm việc (ngày và quy tắc thời gian làm việc hàng ngày) từ tệp Project thông qua mã Java.  
- **Thư viện nào cần thiết?** Aspose.Tasks cho Java (có bản dùng thử miễn phí).  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử hoạt động cho việc thử nghiệm; giấy phép thương mại cần thiết cho triển khai sản xuất.  
- **Các định dạng tệp nào được hỗ trợ?** Cả tệp *.mpp* và Project XML đều được xử lý, cộng thêm hơn 50 định dạng khác cho nhập/xuất.  
- **Thời gian triển khai là bao lâu?** Thường dưới 10 phút sau khi thiết lập thư viện.

## Tuần làm việc là gì trong MS Project?
Tuần làm việc xác định các quy tắc lịch mà quyết định khi nào nguồn lực có sẵn trong một khoảng thời gian nhất định. Nó bao gồm ngày bắt đầu, ngày kết thúc và các khoảng thời gian làm việc hàng ngày (ví dụ, 9 h sáng–5 h chiều). Trong MS Project, mỗi lịch có thể chứa nhiều tuần làm việc, cho phép bạn mô hình hoá ngày lễ, ca làm việc, hoặc lịch trình theo mùa.

## Aspose.Tasks đọc tuần làm việc từ lịch như thế nào?
Aspose.Tasks cung cấp `WorkWeekCollection` của một đối tượng `Calendar`. Bằng cách tạo một thể hiện `Project`, chọn lịch mong muốn (theo UID hoặc tên), và lặp qua `WorkWeekCollection` của nó, bạn có thể lấy nhãn, phạm vi ngày hiệu lực và các khung thời gian làm việc chi tiết cho mỗi ngày. API tự động xử lý mọi chuyển đổi ngày‑giờ và tôn trọng cài đặt múi giờ của dự án.

## Tại sao cần đọc tuần làm việc Java từ lịch Microsoft Project?
Đọc tuần làm việc một cách lập trình loại bỏ việc sao chép‑dán thủ công, đảm bảo các hệ thống hạ nguồn (ERP, HR, báo cáo) sử dụng cùng một quy tắc lập lịch, và bảo đảm tính nhất quán giữa nhiều dự án. Tự động hóa cũng giảm lỗi con người và tăng tốc các quy trình tích hợp, đặc biệt khi bạn cần xử lý hàng chục tệp dự án mỗi đêm.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – phiên bản 8 hoặc mới hơn đã được cài đặt.  
2. **Aspose.Tasks cho Java** – tải JAR mới nhất từ trang chính thức: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Một **tệp Project mẫu** (`ReadWorkWeeksInformation.mpp`) được đặt trong thư mục đã biết trên máy của bạn.

## Nhập các gói
Đầu tiên, nhập các lớp chúng ta sẽ cần để tương tác với lịch và tuần làm việc:

`Project` đại diện cho một tệp Microsoft Project, `Calendar` cung cấp các lịch của nó, `WorkWeek` định nghĩa một tuần làm việc, và `WeekDay` đại diện cho một ngày.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Bước 1: thiết lập thư mục dữ liệu của bạn
Xác định thư mục chứa tệp `.mpp`. Thay thế phần giữ chỗ bằng đường dẫn thực tế trên máy của bạn:

```java
String dataDir = "Your Data Directory";
```

## Bước 2: tạo một thể hiện Project và truy cập lịch
Lớp `Project` đại diện cho một tệp Microsoft Project và cung cấp quyền truy cập vào các cấu trúc dữ liệu của nó, bao gồm lịch, nhiệm vụ và nguồn lực.  
Khởi tạo một đối tượng `Project`, chọn lịch bạn muốn (theo UID), và lấy `WorkWeekCollection` của nó:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Mẹo chuyên nghiệp:** Nếu bạn không chắc UID của lịch, hãy lặp qua `project.getCalendars()` và in ra tên và UID của mỗi lịch trước.

## Bước 3: lặp qua các tuần làm việc
Lớp `WorkWeek` bao hàm định nghĩa một tuần làm việc, chứa ngày bắt đầu/kết thúc và cài đặt thời gian làm việc hàng ngày.  
Duyệt qua mỗi `WorkWeek` để hiển thị tên, ngày bắt đầu/kết thúc và thời gian làm việc hàng ngày:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Bạn sẽ thấy:** Console sẽ in nhãn của mỗi tuần làm việc (ví dụ, “Standard”), phạm vi ngày hiệu lực, và bạn có thể xem chi tiết giờ làm việc cho từng ngày.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| `NullPointerException` khi truy cập `calendar` | UID sai hoặc lịch không tồn tại | Xác minh UID bằng `project.getCalendars().size()` và liệt kê các lịch có sẵn trước. |
| Không có đầu ra cho tuần làm việc | Lịch đã chọn không có tuần làm việc tùy chỉnh (sử dụng mặc định) | Sử dụng lịch mặc định (`project.getDefaultCalendar()`) hoặc tạo tuần làm việc bằng chương trình. |
| Định dạng ngày tháng trông lạ | `System.out.println` sử dụng định dạng mặc định của `java.util.Date` | Áp dụng `SimpleDateFormat` để định dạng ngày theo nhu cầu. |

## Câu hỏi thường gặp
**Q: Tôi có thể sửa đổi thông tin tuần làm việc bằng Aspose.Tasks cho Java không?**  
A: Có. API cung cấp `addWorkWeek()`, `removeWorkWeek()`, và các setter thuộc tính để thay đổi tên, ngày và thời gian làm việc.

**Q: Aspose.Tasks có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
A: Hoàn toàn. Nó hỗ trợ tệp MPP từ Project 98 đến các phiên bản mới nhất, cũng như tệp Project XML.

**Q: Tôi có thể tích hợp Aspose.Tasks với các framework Java khác không?**  
A: Có. Thư viện thuần Java, vì vậy bạn có thể dùng cùng với Spring, Jakarta EE hoặc bất kỳ framework nào khác.

**Q: Có phiên bản dùng thử cho Aspose.Tasks không?**  
A: Có, bạn có thể tải bản dùng thử miễn phí 30 ngày từ trang chính thức: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?**  
A: Diễn đàn cộng đồng Aspose là nơi tốt nhất: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Cập nhật lần cuối:** 2026-08-13  
**Kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Thêm lịch vào dự án với Aspose.Tasks cho Java](/tasks/java/calendars/create/)
- [Lấy ngoại lệ lịch với Aspose.Tasks – hướng dẫn java](/tasks/java/calendar-exceptions/retrieve/)
- [Cách đặt lịch và xác định ngày trong tuần trong MS Project với Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}