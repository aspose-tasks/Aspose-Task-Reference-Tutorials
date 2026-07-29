---
date: 2026-07-29
description: Tìm hiểu cách lên lịch ngày không làm việc bằng cách tạo lịch dự án với
  Aspose.Tasks for Java, định nghĩa các ngoại lệ ngày trong tuần và quản lý lịch nghỉ
  lễ.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Lên lịch ngày không làm việc – Tạo lịch dự án Aspose
og_description: Lên lịch ngày không làm việc bằng Aspose.Tasks for Java. Tìm hiểu
  cách định nghĩa các ngày trong tuần, thêm các ngoại lệ lịch và quản lý lịch nghỉ
  lễ một cách hiệu quả.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Lên lịch ngày không làm việc – Tạo lịch dự án Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Lên lịch ngày không làm việc – Tạo lịch dự án Aspose
url: /vi/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lịch Ngày Không Làm Việc – Tạo Lịch Dự Án Aspose

### Giới thiệu
Khi bạn cần **schedule non working days** cho một dự án, bạn phải có khả năng mô hình hóa các ngày lễ, ca làm việc đặc biệt, hoặc các thời gian đóng cửa tạm thời trực tiếp trong kế hoạch dự án. Aspose.Tasks for Java cung cấp cho bạn toàn quyền kiểm soát định nghĩa lịch, cho phép bạn thêm các ngoại lệ phản ánh lịch trình thực tế. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn chi tiết các bước để xác định các ngày trong tuần cho các ngoại lệ lịch, để thời gian dự án của bạn luôn chính xác và đáng tin cậy. Khi kết thúc, bạn cũng sẽ thấy cách điều này phù hợp với chiến lược **non‑working days schedule** rộng hơn cho bất kỳ dự án doanh nghiệp nào.

## Câu trả lời nhanh
- **What does “schedule non working days” mean?**  
  Điều này có nghĩa là sử dụng Aspose.Tasks để tạo một lịch đánh dấu các ngày cụ thể là không làm việc, tự động ảnh hưởng đến ngày thực hiện nhiệm vụ.  
- **Do I need a license to run the sample?**  
  Bản dùng thử miễn phí hoạt động cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Which IDEs are supported?**  
  IntelliJ IDEA, Eclipse, NetBeans, hoặc bất kỳ IDE nào hỗ trợ Java 8+.  
- **Can I add multiple exceptions to the same calendar?**  
  Có – bạn có thể thêm bao nhiêu đối tượng `CalendarException` tùy ý.  
- **What file formats can I save the project to?**  
  XML, MPP và một số định dạng khác được Aspose.Tasks hỗ trợ.  

## Lịch Dự Án là gì trong Aspose.Tasks?
**project calendar** là đối tượng cấp cao nhất của Aspose.Tasks, định nghĩa các ngày và giờ làm việc cho một dự án. Nó ảnh hưởng trực tiếp đến ngày bắt đầu/kết thúc của nhiệm vụ, phân bổ nguồn lực và các phép tính lịch trình tổng thể. Bằng cách tùy chỉnh lịch, bạn đảm bảo lịch trình tuân thủ các ràng buộc thực tế như ngày lễ công ty hoặc chính sách làm việc cuối tuần.

## Tại sao phải định nghĩa các ngày trong tuần cho các ngoại lệ lịch?
Việc định nghĩa các ngoại lệ ngày trong tuần đảm bảo rằng công cụ dự án xem những ngày đó là không làm việc, ngăn các nhiệm vụ được lên lịch tự động vào chúng và giữ cho thời gian dự án phù hợp với các ràng buộc thực tế như ngày lễ, thời gian bảo trì, hoặc các mẫu ca làm việc đặc biệt trong toàn tổ chức.

- **Accurate timelines:** Các nhiệm vụ sẽ không được đặt vào ngày lễ hoặc khoảng thời gian cấm.  
- **Resource planning:** Nguồn lực chỉ được phân bổ trong các ngày làm việc hợp lệ, tránh việc phân bổ quá mức.  
- **Compliance:** Lịch trình tự động tuân theo chính sách tổ chức hoặc lịch ngày lễ pháp lý.  

## Lịch Ngày Không Làm Việc với Các Ngoại Lệ Lịch
Khi bạn duy trì một **non‑working days schedule**, thường bạn sẽ có một danh sách chính các ngày lễ, thời gian bảo trì, hoặc các khoảng thời gian cấm khác. Thêm những ngày này dưới dạng các đối tượng `CalendarException` đảm bảo mọi phép tính—cho dù là phân tích đường truyền quan trọng hay cân bằng nguồn lực—tự động tuân thủ các ràng buộc đó. Cách tiếp cận này loại bỏ việc điều chỉnh ngày thủ công và giảm nguy cơ lệch lịch.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – phiên bản 8 trở lên.  
2. **Aspose.Tasks for Java** – tải xuống từ trang [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans, hoặc bất kỳ trình soạn thảo nào hỗ trợ Java.  

## Cách lên lịch ngày không làm việc bằng cách sử dụng các ngoại lệ lịch
Tải dự án của bạn, tạo một lịch tùy chỉnh, và thêm các đối tượng `CalendarException` đánh dấu các ngày trong tuần mong muốn là không làm việc. Toàn bộ quá trình này có thể hoàn thành trong một vài bước đơn giản, và lịch kết quả sẽ tự động ảnh hưởng đến mọi logic lập lịch nhiệm vụ.

### Hướng dẫn từng bước

### Bước 1: Nhập các gói cần thiết
Chúng ta cần các lớp cốt lõi của Aspose.Tasks và `GregorianCalendar` của Java để xử lý ngày tháng.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Bước 2: Xác định Thư mục Dữ liệu
Xác định vị trí sẽ lưu tệp dự án được tạo.

```java
String dataDir = "Your Data Directory";
```

### Bước 3: Tạo một thể hiện Project
`Project` là đối tượng chính chứa tất cả dữ liệu dự án, bao gồm các nhiệm vụ, nguồn lực và lịch.

```java
Project project = new Project();
```

### Bước 4: Định nghĩa một Lịch
`Calendar` đại diện cho lịch làm việc và không làm việc trong một dự án.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Bước 5: Định nghĩa Ngoại lệ Ngày trong Tuần
`CalendarException` đại diện cho một khoảng thời gian được đánh dấu là không làm việc trong lịch.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Bước 6: Lưu Dự Án
Lưu dự án, bao gồm lịch tùy chỉnh và ngoại lệ của nó, vào một tệp XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Exception dates not applied** | Đảm bảo `setEnteredByOccurrences(false)` và các giá trị `FromDate/ToDate` đúng. |
| **Saved file is empty** | Kiểm tra `dataDir` trỏ tới thư mục có thể ghi và tên tệp kết thúc bằng `.xml`. |
| **Calendar not reflected in task scheduling** | Gán lịch cho các nhiệm vụ hoặc nguồn lực bằng cách sử dụng `task.setCalendar(cal)` hoặc `resource.setCalendar(cal)`. |

## Câu hỏi thường gặp

**Q: Tôi có thể định nghĩa nhiều ngoại lệ cho các ngày trong tuần khác nhau trong cùng một lịch không?**  
A: Yes. Add additional `CalendarException` objects to `cal.getExceptions()` for each distinct period or rule.

**Q: Aspose.Tasks for Java có tương thích với các IDE Java khác nhau không?**  
A: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and any IDE that supports standard Java projects.

**Q: Tôi có thể tùy chỉnh các loại ngoại lệ khác ngoài ngoại lệ hàng ngày không?**  
A: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit your scheduling needs.

**Q: Làm thế nào tôi có thể xử lý các ngoại lệ một cách động dựa trên yêu cầu dự án?**  
A: Build the exception objects programmatically—e.g., read holiday dates from a database or configuration file and create `CalendarException` instances in a loop.

**Q: Có phiên bản dùng thử cho Aspose.Tasks for Java không?**  
A: Yes, you can download a free trial from the [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Kết luận
Bằng cách thực hiện các bước này, bạn đã biết cách **schedule non working days** bằng cách tạo một lịch dự án và định nghĩa các ngoại lệ ngày trong tuần phản ánh chính xác các ngày lễ hoặc các khoảng thời gian không làm việc đặc biệt. Cấu hình lịch đúng là yếu tố quan trọng cho các lịch trình thực tế, phân bổ nguồn lực và thành công chung của dự án. Hãy khám phá thêm bằng cách gắn lịch tùy chỉnh vào các nhiệm vụ hoặc nguồn lực và thử nghiệm các loại ngoại lệ khác để xây dựng một **non‑working days schedule** toàn diện cho bất kỳ dự án nào.

---

**Cập nhật lần cuối:** 2026-07-29  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Thêm lịch vào dự án với Aspose.Tasks cho Java](/tasks/java/calendars/create/)
- [Tạo Ngoại lệ Lịch cho Aspose cho Java](/tasks/java/calendar-exceptions/add-remove/)
- [Cách Đặt Lịch và Định nghĩa Ngày trong Tuần trong MS Project với Aspose.Tasks](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}