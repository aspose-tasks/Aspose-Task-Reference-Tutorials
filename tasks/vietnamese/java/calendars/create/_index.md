---
date: 2026-08-03
description: Tìm hiểu cách tạo lịch ms project, thêm lịch vào dự án và lưu dự án dưới
  dạng XML bằng Aspose.Tasks cho Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Thêm Lịch vào Dự án bằng Aspose.Tasks
og_description: Tạo lịch ms project một cách lập trình bằng Aspose.Tasks cho Java.
  Thêm lịch, tùy chỉnh lịch trình và xuất ra XML trong vài phút.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Tạo lịch ms project với Aspose.Tasks cho Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Tạo lịch ms project với Aspose.Tasks cho Java
url: /vi/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo lịch ms project với Aspose.Tasks cho Java

## Giới thiệu
Trong các quy trình quản lý dự án hiện đại, khả năng **create ms project calendar** một cách lập trình có thể tiết kiệm hàng giờ chỉnh sửa thủ công. Aspose.Tasks cho Java cung cấp cho bạn một API sạch, an toàn kiểu để thao tác các tệp Microsoft Project mà không cần mở client trên máy tính để bàn. Trong hướng dẫn này, bạn sẽ học cách thêm lịch, cách tạo lịch MS Project, và cách lưu dự án dưới dạng XML—tất cả chỉ với vài dòng mã Java.

## Câu trả lời nhanh
- **“create ms project calendar” có nghĩa là gì?**  
  Nó có nghĩa là chèn một định nghĩa thời gian làm việc mới (lịch) vào tệp Microsoft Project bằng mã.  
- **Thư viện nào xử lý việc này?**  
  Aspose.Tasks cho Java cung cấp lớp `Calendar` và container `Project` để quản lý lịch.  
- **Tôi có cần giấy phép không?**  
  Giấy phép đánh giá tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ là bắt buộc cho việc sử dụng trong môi trường sản xuất.  
- **Tôi có thể lưu tệp dưới dạng XML không?**  
  Có—sử dụng `SaveFileFormat.Xml` để xuất dự án dưới dạng tệp XML.  
- **Các điều kiện tiên quyết là gì?**  
  Java JDK 8+ và JAR Aspose.Tasks cho Java trong classpath của bạn.  

## “create ms project calendar” là gì?
Tạo một lịch MS Project có nghĩa là thêm một định nghĩa lịch mới vào tệp Project một cách lập trình, chỉ định các ngày làm việc, các ngoại lệ và giờ làm việc hàng ngày, sau đó gán lịch đó cho các công việc, tài nguyên, hoặc toàn bộ dự án để các phép tính lịch trình tuân theo thời gian làm việc đã định nghĩa.

## Tại sao nên sử dụng Aspose.Tasks cho Java để thêm lịch vào dự án?
Bạn nên sử dụng Aspose.Tasks cho Java vì nó cung cấp một API hoàn toàn an toàn kiểu, hoạt động mà không cần cài đặt Microsoft Project, hỗ trợ tất cả các phiên bản Project chính (2007‑2021, bao gồm hơn 5 bản phát hành), và có thể xuất sang XML, MPP, và **10+** định dạng khác, cho phép tạo lịch hàng loạt tự động trên bất kỳ máy chủ nào.

## Điều kiện tiên quyết
- **Java Development Kit (JDK) 8 hoặc mới hơn** đã được cài đặt và cấu hình.  
- **Thư viện Aspose.Tasks cho Java** – tải xuống từ [trang web chính thức](https://releases.aspose.com/tasks/java/) và thêm JAR vào classpath của dự án.  
- Một IDE hoặc công cụ xây dựng (Maven/Gradle) mà bạn lựa chọn.  

## Hướng dẫn từng bước

### Bước 1: nhập gói Aspose.Tasks cần thiết
Đầu tiên, đưa các lớp Aspose.Tasks vào phạm vi để bạn có thể làm việc với dự án và lịch.

```java
import com.aspose.tasks.*;
```

### Bước 2: đặt đường dẫn thư mục dữ liệu
Xác định nơi tệp dự án được tạo sẽ được ghi. Thay thế phần giữ chỗ bằng đường dẫn tuyệt đối hoặc tương đối trên máy của bạn.

```java
String dataDir = "Your Data Directory";
```

### Bước 3: tạo một thể hiện Project mới
`Project` là lớp cốt lõi đại diện cho tệp Microsoft Project trong bộ nhớ.

```java
Project prj = new Project();
```

### Bước 4: định nghĩa các lịch bạn muốn thêm
`Calendar` định nghĩa một lịch trình với các ngày làm việc, ngoại lệ và thời gian làm việc cho một dự án.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Mẹo chuyên nghiệp:** Sau khi thêm lịch, bạn có thể tùy chỉnh các ngày làm việc của nó bằng `cal1.getWeekDays().add(...)` và đặt giờ làm việc hàng ngày bằng `cal1.getBaseCalendar().setWorkingTime(...)`.

### Bước 5: lưu dự án (lưu dự án dưới dạng XML)
`SaveFileFormat.Xml` cho Aspose.Tasks biết ghi dự án ở định dạng XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Bước 6: hiển thị thông báo hoàn thành
Cho người dùng biết thao tác đã hoàn thành thành công.

```java
System.out.println("Process completed Successfully");
```

Bằng cách làm theo sáu bước ngắn gọn này, bạn đã thành công **thêm một lịch vào dự án** và lưu kết quả dưới dạng tệp XML.

## Các vấn đề thường gặp và giải pháp
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | Đối tượng Project không được khởi tạo đúng cách. | Đảm bảo gọi `new Project()` trước khi truy cập lịch. |
| **File not found when saving** | `dataDir` trỏ tới thư mục không tồn tại. | Tạo thư mục trước hoặc sử dụng đường dẫn tuyệt đối. |
| **Calendar name appears as “no info”** | Các tên giữ chỗ đã được sử dụng trong mẫu. | Thay thế bằng các tên có ý nghĩa phản ánh lịch trình (ví dụ, “Lịch nghỉ lễ US”). |
| **Saved XML cannot be opened in MS Project** | Sử dụng phiên bản Aspose.Tasks lỗi thời. | Cập nhật lên phiên bản Aspose.Tasks cho Java mới nhất. |

## Câu hỏi thường gặp

**Q: Aspose.Tasks có thể xử lý lịch phức tạp với nhiều ngoại lệ không?**  
A: Có – sau khi thêm lịch bạn có thể định nghĩa các ngoại lệ, giờ làm việc và ngày không làm việc bằng các lớp `WeekDay` và `Exception`.

**Q: Có thể gán lịch mới cho các công việc cụ thể không?**  
A: Chắc chắn. Lấy một công việc bằng `prj.getRootTask().getChildren().add("Task Name")` và đặt `task.set(Tsk.CALENDAR, cal3);`.

**Q: Thư viện có hỗ trợ lưu ở các định dạng khác như MPP không?**  
A: Có. Thay `SaveFileFormat.Xml` bằng `SaveFileFormat.Mpp` hoặc `SaveFileFormat.P6` khi cần; Aspose.Tasks hỗ trợ **12** định dạng xuất.

**Q: Tôi có cần giấy phép cho các bản dựng phát triển không?**  
A: Giấy phép đánh giá tạm thời đủ cho việc thử nghiệm; giấy phép đầy đủ là bắt buộc cho triển khai trong môi trường sản xuất.

**Q: Tôi có thể nhận được trợ giúp ở đâu nếu gặp vấn đề?**  
A: Diễn đàn cộng đồng Aspose.Tasks là một nguồn tài nguyên tuyệt vời: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Cập nhật lần cuối:** 2026-08-03  
**Kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách định nghĩa ngày trong tuần trong Lịch MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Cách đặt Lịch dự án Java với Aspose.Tasks](/tasks/java/calendars/properties/)
- [Tạo ngoại lệ lịch tùy chỉnh với Aspose.Tasks cho Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}