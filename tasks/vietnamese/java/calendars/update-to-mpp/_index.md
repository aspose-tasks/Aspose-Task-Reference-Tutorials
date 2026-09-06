---
date: 2026-08-13
description: Tìm hiểu cách thêm ngày nghỉ vào calendar, gán calendar cho một project,
  và lưu file MS Project dưới dạng MPP bằng Aspose.Tasks for Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Cập nhật calendar sang định dạng MPP trong Aspose.Tasks
og_description: Thêm ngày nghỉ vào calendar, gán nó cho một project, và chuyển đổi
  schedule sang MPP bằng Aspose.Tasks for Java. Tìm hiểu tự động hoá từng bước.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Thêm ngày nghỉ vào calendar và lưu dưới dạng MPP với Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Thêm ngày nghỉ vào calendar và lưu dưới dạng MPP với Aspose.Tasks
url: /vi/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm ngày nghỉ vào lịch và lưu dưới dạng MPP với Aspose.Tasks

## Giới thiệu

Trong quản lý dự án hiện đại, bạn thường cần **thêm ngày nghỉ vào lịch** các tệp, tạo một **lịch MS Project**, và sau đó chia sẻ lịch trình ở định dạng MPP gốc. Cho dù bạn đang hợp nhất các thời gian biểu từ nhiều nguồn hoặc di chuyển dữ liệu cũ, việc tạo lịch một cách lập trình loại bỏ lỗi thủ công và tăng tốc độ giao hàng. Hướng dẫn này sẽ đưa bạn qua toàn bộ quy trình tạo lịch trong MS Project, tùy chỉnh nó với các ngày nghỉ, **gán lịch cho dự án**, và cuối cùng **chuyển dự án sang MPP** bằng API Aspose.Tasks cho Java.

## Câu trả lời nhanh
- **Câu hỏi: Hướng dẫn này đề cập đến gì?** Thêm ngày nghỉ vào lịch, gán nó cho dự án, và lưu kết quả dưới dạng tệp MPP với Aspose.Tasks cho Java.  
- **Cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Phiên bản Java yêu cầu?** Java 8 hoặc cao hơn (JDK 8+).  
- **Có thể tùy chỉnh lịch không?** Có – bạn có thể thêm thời gian làm việc, ngoại lệ và ngày nghỉ.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một lịch cơ bản.  

## Tạo lịch MS Project là gì?

Tạo lịch MS Project có nghĩa là xác định các ngày làm việc, giờ làm và các ngoại lệ điều khiển việc lên lịch nhiệm vụ trong tệp Microsoft Project. Sử dụng Aspose.Tasks, bạn có thể xây dựng lịch này một cách lập trình, đặt ngày nghỉ, và nhúng nó vào dự án mà không cần mở giao diện MS Project.

## Tại sao nên sử dụng Aspose.Tasks cho nhiệm vụ này?

Bạn nên sử dụng Aspose.Tasks vì nó cung cấp khả năng tương thích đầy đủ với Java, không cần Microsoft Office, và cho phép bạn tạo và lưu các tệp MPP gốc trực tiếp từ mã. Thư viện hỗ trợ mọi tính năng của lịch, hoạt động trên bất kỳ môi trường máy chủ nào, và xử lý các dự án lên tới 10.000 nhiệm vụ trong chưa đầy một giây.

## Yêu cầu trước

1. **Bộ công cụ phát triển Java (JDK) 8+** – đảm bảo `java -version` trả về 1.8 hoặc mới hơn.  
2. **Aspose.Tasks cho Java** – tải JAR mới nhất từ [trang web Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo nào bạn thích.  
4. **Kiến thức Java cơ bản** – quen thuộc với các lớp, phương thức và I/O tệp.

## Cách thêm ngày nghỉ vào lịch

Để thêm ngày nghỉ, bạn tạo một đối tượng `Calendar` mới, lấy bộ sưu tập `Exceptions` của nó, và thêm các mục `DateException` cho mỗi ngày nghỉ. `DateException` đại diện cho một ngày hoặc khoảng thời gian không làm việc trong lịch. Aspose.Tasks sẽ xem những ngày này là ngày không làm việc, đảm bảo các nhiệm vụ được lên lịch xung quanh các ngày nghỉ đã định.

### Bước 1: nhập các gói cần thiết

First, bring the Aspose.Tasks classes and Java utilities into scope.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Bước 2: thiết lập thư mục dữ liệu

Define where your input template and output files will live. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

### Bước 3: xác định tên tệp đầu vào và đầu ra

We’ll load an existing MPP file (or a blank project) and write the result to a new file.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Bước 4: tải dự án và thêm lịch mới

`Project` class represents an MS Project file in memory and provides access to its calendars, tasks, and resources.

Create a `Project` instance from the source file and add a calendar named **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Bước 5: tùy chỉnh lịch (tùy chọn)

`Calendar` object defines working days, hours, and exceptions for a project schedule.

If you need specific working times, holidays, or exceptions, call your own helper method. The sample uses `GetTestCalendar` as a placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Mẹo chuyên nghiệp:** Bạn có thể thao tác trực tiếp `cal1.getWeekDays()` để đặt giờ làm việc cho mỗi ngày trong tuần, hoặc sử dụng `cal1.getExceptions()` để **thêm ngày nghỉ vào lịch**.

### Bước 6: gán lịch cho dự án

Tell the project to use the newly created calendar for all its scheduling calculations.

```java
project.set(Prj.CALENDAR, cal1);
```

### Bước 7: lưu dự án dưới dạng MPP

`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating native Microsoft Project format.

Now **convert project to MPP** by saving it with the `SaveFileFormat.Mpp` option.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Bước 8: xác nhận hoàn thành thành công

A simple console message lets you know the process finished without errors.

```java
System.out.println("Process completed Successfully");
```

## Các trường hợp sử dụng phổ biến

- **Tự động tạo lịch** cho các dự án lặp lại (ví dụ: sprint hàng tuần).  
- **Di chuyển lịch CSV hoặc Excel cũ** vào tệp MS Project đầy đủ tính năng.  
- **Báo cáo phía máy chủ** nơi dịch vụ web trả về tệp MPP theo yêu cầu.  

## Xử lý sự cố & những khó khăn thường gặp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| `NullPointerException` khi `project.save` | `dataDir` trỏ tới thư mục không tồn tại | Đảm bảo thư mục tồn tại hoặc tạo nó bằng chương trình. |
| Lịch không được áp dụng cho các nhiệm vụ | Các nhiệm vụ vẫn tham chiếu lịch mặc định | Sau khi đặt `Prj.CALENDAR`, cũng cập nhật `Task.CALENDAR` của mỗi nhiệm vụ nếu chúng đã bị ghi đè trước đó. |
| Tệp đầu ra có kích thước 0 KB | Thiếu quyền ghi | Chạy JVM với quyền hệ thống tệp phù hợp hoặc chọn đường dẫn có thể ghi. |

## Câu hỏi thường gặp

**Hỏi: Aspose.Tasks cho Java có tương thích với các phiên bản khác nhau của MS Project không?**  
**Đáp:** Có, Aspose.Tasks hỗ trợ tất cả các định dạng tệp Microsoft Project từ Project 2007 đến Project 2024, bao gồm hơn 10 phiên bản.

**Hỏi: Tôi có thể tùy chỉnh lịch theo yêu cầu dự án cụ thể không?**  
**Đáp:** Chắc chắn. Bạn có thể xác định các ngày làm việc, đặt tuần làm việc tùy chỉnh, thêm ngày nghỉ, và thậm chí tạo nhiều lịch trong một tệp dự án duy nhất.

**Hỏi: Aspose.Tasks cho Java có cung cấp hỗ trợ giải quyết sự cố và trợ giúp không?**  
**Đáp:** Có, bạn có thể nhận trợ giúp từ diễn đàn cộng đồng Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Hỏi: Có bản dùng thử miễn phí cho Aspose.Tasks cho Java không?**  
**Đáp:** Có, bản dùng thử miễn phí đầy đủ chức năng có sẵn [Aspose.Tasks free trial](https://releases.aspose.com/).

**Hỏi: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Tasks cho Java?**  
**Đáp:** Giấy phép tạm thời có thể yêu cầu qua trang web Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-08-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các hướng dẫn liên quan

- [Thêm lịch vào dự án với Aspose.Tasks cho Java](/tasks/java/calendars/create/)
- [Cách xác định ngày trong tuần trong Lịch MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Tạo ngoại lệ lịch tùy chỉnh với Aspose.Tasks cho Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}