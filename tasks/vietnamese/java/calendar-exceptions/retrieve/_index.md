---
title: Truy xuất ngoại lệ lịch với Aspose.Tasks
linktitle: Truy xuất ngoại lệ lịch với Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách truy xuất các ngoại lệ lịch từ MS Project bằng Aspose.Tasks cho Java. Hướng dẫn từng bước để tích hợp liền mạch.
weight: 13
url: /vi/java/calendar-exceptions/retrieve/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Truy xuất ngoại lệ lịch với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách truy xuất các ngoại lệ lịch từ MS Project bằng thư viện Aspose.Tasks cho Java. Aspose.Tasks là một công cụ mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project theo chương trình. Chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình, chia nhỏ từng ví dụ thành nhiều bước để dễ hiểu.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Tasks cho Java: Tải xuống và cài đặt Aspose.Tasks cho Java từ[đây](https://releases.aspose.com/tasks/java/).
3. Môi trường phát triển tích hợp (IDE): Bạn có thể sử dụng bất kỳ IDE nào bạn chọn, chẳng hạn như IntelliJ IDEA hoặc Eclipse.

## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết để làm việc với Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Bước 1: Thiết lập thư mục dữ liệu của bạn
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Data Directory";
```
 Đảm bảo thay thế`"Your Data Directory"` với đường dẫn đến thư mục chứa tệp MS Project của bạn.
## Bước 2: Tải tệp dự án MS
```java
Project project = new Project(dataDir + "project.mpp");
```
 Dòng này khởi tạo một cái mới`Project` đối tượng bằng cách tải tệp MS Project được chỉ định bởi đường dẫn.
## Bước 3: Truy xuất ngoại lệ lịch
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Ở đây, chúng tôi lặp qua từng lịch trong dự án và sau đó qua từng ngoại lệ lịch trong lịch đó. Chúng tôi in ra ngày bắt đầu và ngày kết thúc của từng ngoại lệ.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách truy xuất các ngoại lệ lịch từ MS Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước đơn giản này, bạn có thể tích hợp liền mạch chức năng này vào các ứng dụng Java của mình.
## Các câu hỏi thường gặp
### Aspose.Tasks có thể xử lý các phiên bản khác nhau của tệp MS Project không?
Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp MS Project, bao gồm các định dạng MPP, MPT và XML.
### Có bản dùng thử miễn phí cho Aspose.Tasks không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí Aspose.Tasks từ[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu về Aspose.Tasks cho Java ở đâu?
 Bạn có thể tham khảo tài liệu[đây](https://reference.aspose.com/tasks/java/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks?
 Bạn có thể nhận được hỗ trợ từ diễn đàn cộng đồng[đây](https://forum.aspose.com/c/tasks/15).
### Có tùy chọn cấp giấy phép tạm thời cho Aspose.Tasks không?
 Có, bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
