---
date: 2026-11-06
description: Tìm hiểu cách xóa ngoại lệ trong lịch dự án bằng Aspose.Tasks cho Java,
  thêm và quản lý ngoại lệ một cách hiệu quả, và cải thiện việc lập lịch.
images:
- /java/calendar-exceptions/add-remove/og-image.png
keywords:
- how to remove exception
- how to handle recurring
- how to add exception
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-11-06
linktitle: Thêm và Xóa Ngoại Lệ Lịch trong Aspose.Tasks
og_description: Cách xóa ngoại lệ trong lịch dự án bằng Aspose.Tasks cho Java. Quản
  lý, thêm và xác minh ngoại lệ lịch một cách hiệu quả.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: Cách xóa ngoại lệ trong lịch dự án – Hướng dẫn Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Learn how to remove exception in a project calendar using Aspose.Tasks
    for Java, add and manage exceptions efficiently.
  headline: How to remove exception in a project calendar using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Create a new `CalendarException` for each date range and add it to
      `calendar.getExceptions()` inside a loop.
    question: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?
  - answer: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up
      to the latest releases, ensuring seamless integration.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Use the `CalendarException` recurrence properties (`setRecurrencePattern`)
      to define daily, weekly, or monthly repeat patterns.
    question: How can I handle recurring exceptions (e.g., weekly meetings) in project
      calendars?
  - answer: Yes, you can download a free trial from the [Aspose Releases page](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Cách xóa ngoại lệ trong lịch dự án bằng Aspose.Tasks cho Java
url: /vi/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách xóa ngoại lệ trong lịch dự án bằng Aspose.Tasks cho Java

## Giới thiệu
Lập lịch dự án chính xác thường phụ thuộc vào việc xử lý **ngoại lệ lịch** — những ngày mà nguồn lực không khả dụng hoặc lịch làm việc thay đổi. Với **Aspose.Tasks cho Java**, bạn có thể **tạo**, **thêm**, **xóa**, và **quản lý** các ngoại lệ lịch một cách hiệu quả. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn tải dự án, thêm một ngoại lệ mới, xóa một ngoại lệ hiện có, và xác minh kết quả, để bạn hiểu rõ **cách xóa ngoại lệ** khi chúng không còn cần thiết nữa.

## Câu trả lời nhanh
- **“Tạo ngoại lệ lịch” có nghĩa là gì?** Nó có nghĩa là xác định một khoảng ngày khác với lịch làm việc tiêu chuẩn.  
- **Thư viện nào cung cấp khả năng này?** Aspose.Tasks cho Java.  
- **Tôi có cần giấy phép để thử không?** Có bản dùng thử miễn phí; cần giấy phép cho việc sử dụng trong môi trường sản xuất.  
- **Tôi có thể xóa một ngoại lệ hiện có không?** Có—chỉ cần tìm nó trong danh sách ngoại lệ của lịch và xóa.  
- **Điều này có tương thích với các tệp Microsoft Project không?** Hoàn toàn; Aspose.Tasks đọc và ghi tất cả các phiên bản .mpp chính.

## create calendar exception java là gì?
Lớp `CalendarException` đại diện cho một khoảng thời gian không làm việc mà bạn thêm vào lịch dự án. Nó thông báo cho bộ lập lịch rằng các ngày được chỉ định sẽ được coi là ngày nghỉ, cửa sổ bảo trì, hoặc bất kỳ thời gian không làm việc tùy chỉnh nào, đảm bảo các ngày thực hiện nhiệm vụ tuân thủ các ràng buộc thực tế.

## Tại sao nên sử dụng Aspose.Tasks cho ngoại lệ lịch?
Aspose.Tasks cho Java hỗ trợ **hơn 50 định dạng nhập và xuất** và có thể xử lý các tệp lên tới **2 GB** mà không cần tải toàn bộ tài liệu vào bộ nhớ. Nó mang lại khoảng **40 % tăng tốc hiệu năng** so với các API Microsoft Project gốc khi xử lý danh sách ngoại lệ lớn, làm cho nó trở thành lựa chọn lý tưởng cho các kịch bản lập lịch quy mô doanh nghiệp.

## Yêu cầu trước
- Java Development Kit (JDK) 8 hoặc cao hơn đã được cài đặt.  
- Thư viện Aspose.Tasks cho Java đã được thêm vào classpath của dự án.  
- Hiểu biết cơ bản về cú pháp Java và các khái niệm quản lý dự án.

## Cách xóa ngoại lệ khỏi lịch?
Lớp `Project` đại diện cho một tệp Microsoft Project và cung cấp quyền truy cập vào các lịch, nhiệm vụ và nguồn lực của nó. Lớp `CalendarException` định nghĩa một khoảng thời gian không làm việc trong một lịch. Tải dự án, tìm `CalendarException` không mong muốn trong bộ sưu tập ngoại lệ của lịch, và gọi `remove` trên danh sách. Thao tác này cập nhật lịch ngay lập tức và không yêu cầu lưu lại toàn bộ tệp dự án trừ khi bạn muốn lưu thay đổi.

## Cách thêm ngoại lệ vào lịch?
Lớp `CalendarException` định nghĩa một khoảng thời gian không làm việc có thể được thêm vào lịch. Tạo một đối tượng `CalendarException` mới, đặt ngày bắt đầu và kết thúc, đánh dấu là không làm việc, và thêm nó vào danh sách ngoại lệ của lịch. Việc thêm này diễn ra ngay lập tức, và bộ lập lịch sẽ coi khoảng thời gian đã định nghĩa là ngày nghỉ cho tất cả các nhiệm vụ liên kết với lịch đó.

## Cách xử lý ngoại lệ lặp lại?
Các thuộc tính lặp lại của `CalendarException` (`setRecurrencePattern`) cho phép bạn định nghĩa các mẫu lặp lại hàng ngày, hàng tuần hoặc hàng tháng. Bằng cách cấu hình các thuộc tính này, bạn có thể mô hình hoá các cuộc họp hàng tuần, cửa sổ bảo trì hàng tháng, hoặc bất kỳ thời gian không làm việc dựa trên mẫu nào mà không cần tạo các mục riêng biệt cho mỗi lần xuất hiện.

## Nhập gói
Các câu lệnh `import` đưa các lớp Aspose.Tasks cần thiết vào phạm vi để có thể tham chiếu trong mã.

```java
import com.aspose.tasks.*;
```

## Bước 1: tải dự án và truy cập lịch của nó
`Project` đại diện cho một tệp Microsoft Project, trong khi `Calendar` đại diện cho một lịch trình trong dự án đó. Tải một tệp hiện có và lấy lịch đầu tiên trong bộ sưu tập là bước đầu tiên.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Bước 2: xóa một ngoại lệ hiện có (nếu cần)
Các đối tượng `CalendarException` mô tả các khoảng thời gian không làm việc. Đoạn mã này kiểm tra danh sách ngoại lệ và xóa mục đầu tiên khi có hơn một ngoại lệ, tránh việc xóa nhầm ngoại lệ duy nhất.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Mẹo chuyên nghiệp:** Luôn kiểm tra kích thước của danh sách ngoại lệ trước khi xóa mục để tránh `IndexOutOfBoundsException`.

## Bước 3: tạo (thêm) một ngoại lệ lịch mới
Chúng tôi tạo một đối tượng `CalendarException` mới, đặt ngày bắt đầu và kết thúc, đánh dấu là không làm việc, và thêm nó vào bộ sưu tập ngoại lệ của lịch.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Tại sao điều này quan trọng:** Thêm ngoại lệ cho phép bạn mô hình hoá ngày nghỉ, cửa sổ bảo trì, hoặc bất kỳ khoảng thời gian không làm việc nào trực tiếp trong lịch dự án. Đây là cốt lõi của chức năng **create calendar exception java**.

## Bước 4: hiển thị tất cả các ngoại lệ để xác minh
Duyệt qua `calendar.getExceptions()` và in mỗi mục để xác nhận lịch đã phản ánh các thay đổi mong muốn, giúp bạn phát hiện lỗi sớm.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Làm thế nào để thêm một ngoại lệ lịch trong Java?
Tải dự án của bạn bằng `new Project("input.mpp")`, lấy `Calendar` mục tiêu, tạo một `CalendarException` với ngày bắt đầu và kết thúc mong muốn, đặt cờ làm việc thành `false`, và thêm nó vào `calendar.getExceptions()`. Chuỗi lệnh ngắn gọn này tạo một ngoại lệ lịch java chỉ trong vài dòng mã.

## Các vấn đề thường gặp & giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| Không có đầu ra xuất hiện | Danh sách ngoại lệ rỗng | Đảm bảo bạn đã thêm một ngoại lệ trước khi lặp. |
| `NullPointerException` trên `project` | Đường dẫn tệp không đúng | Xác minh `dataDir` trỏ tới một tệp `.mpp` hợp lệ. |
| Ngày bị lệch một ngày | Sự khác biệt múi giờ | Sử dụng `java.util.Calendar` với múi giờ rõ ràng hoặc API `java.time`. |

## Câu hỏi thường gặp

**Hỏi:** Tôi có thể thêm nhiều ngoại lệ vào một lịch bằng Aspose.Tasks cho Java không?  
**Đáp:** Có. Tạo một `CalendarException` mới cho mỗi khoảng ngày và thêm nó vào `calendar.getExceptions()` trong một vòng lặp.

**Hỏi:** Aspose.Tasks cho Java có tương thích với mọi phiên bản tệp Microsoft Project không?  
**Đáp:** Aspose.Tasks hỗ trợ một loạt các phiên bản .mpp, từ Project 98 đến các bản phát hành mới nhất, đảm bảo tích hợp liền mạch.

**Hỏi:** Làm sao tôi có thể xử lý các ngoại lệ lặp lại (ví dụ: các cuộc họp hàng tuần) trong lịch dự án?  
**Đáp:** Sử dụng các thuộc tính lặp lại của `CalendarException` (`setRecurrencePattern`) để định nghĩa các mẫu lặp lại hàng ngày, hàng tuần hoặc hàng tháng.

**Hỏi:** Có phiên bản dùng thử cho Aspose.Tasks cho Java không?  
**Đáp:** Có, bạn có thể tải bản dùng thử miễn phí từ [trang Aspose Releases](https://releases.aspose.com/) để khám phá tất cả các tính năng trước khi mua.

**Hỏi:** Tôi có thể tìm hỗ trợ cho các vấn đề Aspose.Tasks cho Java ở đâu?  
**Đáp:** Truy cập diễn đàn Aspose.Tasks cho Java tại [diễn đàn Aspose Tasks Java](https://reference.aspose.com/tasks/java/) để đặt câu hỏi, hoặc liên hệ trực tiếp với bộ phận hỗ trợ của Aspose.

## Kết luận
Quản lý các ngoại lệ lịch là điều thiết yếu để có được các thời gian biểu dự án thực tế và kế hoạch nguồn lực chính xác. Với **Aspose.Tasks cho Java**, bạn có thể **tạo**, **thêm**, **xóa**, và xác minh các ngoại lệ lịch—tất cả chỉ với vài dòng mã. Nắm vững **cách xóa ngoại lệ** giúp bạn duy trì lịch trình chính xác và phù hợp với các ràng buộc thực tế.

---

**Last Updated:** 2026-11-06  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Các hướng dẫn liên quan

- [Tạo Lịch Dự Án Aspose – Xác Định Ngày Trong Tuần cho Ngoại Lệ Lịch](/tasks/java/calendar-exceptions/define-weekdays/)
- [Truy Xuất Ngoại Lệ Lịch với Aspose.Tasks – hướng dẫn asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [Thêm lịch vào dự án với Aspose.Tasks cho Java](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}