---
date: 2025-12-23
description: Tìm hiểu cách sử dụng Aspose.Tasks Java để cập nhật lịch trình dự án,
  đặt ngày bắt đầu tuần, thay đổi số ngày trong tháng và tùy chỉnh lịch dự án một
  cách hiệu quả.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Quản lý các thuộc tính ngày trong tuần
url: /vi/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Quản lý Thuộc tính Ngày trong tuần

## Giới thiệu
Aspose.Tasks for Java (aspose tasks java) là một API mạnh mẽ cho phép các nhà phát triển Java làm việc với các tệp Microsoft Project mà không cần cài đặt Microsoft Project. Trong hướng dẫn này, bạn sẽ học cách **tải tệp MPP**, **đặt ngày bắt đầu tuần**, **thay đổi số ngày trong tháng**, và **tùy chỉnh lịch dự án** — tất cả các bước quan trọng để cập nhật lịch trình dự án. Khi hoàn thành, bạn sẽ có thể điều chỉnh các thuộc tính ngày trong tuần một cách lập trình và lưu các thay đổi ở định dạng bạn cần.

## Câu trả lời nhanh
- **Lớp chính để xử lý dự án là gì?** `Project` từ thư viện Aspose.Tasks.  
- **Làm sao để thay đổi ngày bắt đầu tuần?** Sử dụng `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Tôi có thể tải một tệp .mpp hiện có không?** Có — khởi tạo `Project` với đường dẫn tệp.  
- **Phương thức nào lưu dự án dưới dạng XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép cần thiết cho môi trường sản xuất.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn đã có:

- **Java Development Kit (JDK)** – phiên bản mới nhất đã được cài đặt.  
- **Thư viện Aspose.Tasks for Java** – tải về [tại đây](https://releases.aspose.com/tasks/java/).  
- **Một IDE** như IntelliJ IDEA, Eclipse, hoặc NetBeans.  

## Nhập khẩu các gói
Để bắt đầu, nhập các lớp Aspose.Tasks cần thiết:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Bây giờ chúng ta sẽ đi qua từng bước để quản lý các thuộc tính ngày trong tuần.

## Bước 1: Tải tệp MPP
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Ở đây chúng ta **tải một tệp .mpp hiện có** (`load mpp file`) để có thể kiểm tra và sửa đổi các cài đặt lịch của nó.*

## Bước 2: Hiển thị các Thuộc tính Ngày trong tuần hiện tại
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Đoạn mã này in ra **ngày bắt đầu tuần**, **số ngày trong tháng**, **số phút trong ngày**, và **số phút trong tuần** hiện tại — các yếu tố cốt lõi mà bạn thường cần để **tùy chỉnh lịch dự án**.

## Bước 3: Đặt các Thuộc tính Ngày trong tuần mới
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Trong bước này chúng ta **đặt ngày bắt đầu tuần** thành Monday, **thay đổi số ngày trong tháng** thành 24, và điều chỉnh số phút hàng ngày và hàng tuần. Những cài đặt này thường được sử dụng khi bạn cần **cập nhật lịch trình dự án** để phù hợp với một lịch làm việc không chuẩn.

## Bước 4: Lưu Dự án Đã Cập nhật
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Dự án đã được sửa đổi sẽ được lưu dưới dạng tệp XML, giúp dễ dàng chia sẻ hoặc nhập vào các công cụ khác.

## Bước 5: Xác nhận Hoạt động
```java
System.out.println("Process completed Successfully");
```
Một thông báo console đơn giản sẽ cho bạn biết quy trình đã hoàn thành mà không có lỗi.

## Các vấn đề thường gặp & Mẹo
- **Đường dẫn tệp không đúng** – Kiểm tra `dataDir` có kết thúc bằng dấu gạch chéo hoặc sử dụng `Paths.get(...)` cho các đường dẫn độc lập nền tảng.  
- **Chưa đặt giấy phép** – Trong môi trường sản xuất, gọi `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` trước khi tạo `Project`.  
- **Ngày bắt đầu tuần không như mong đợi** – Đảm bảo bạn sử dụng giá trị enum `DayType` đúng (ví dụ, `DayType.Sunday`).  

## Câu hỏi thường gặp

**H: Aspose.Tasks for Java có thể xử lý cấu trúc dự án phức tạp không?**  
Đ: Có, Aspose.Tasks for Java cung cấp hỗ trợ toàn diện để xử lý các cấu trúc dự án phức tạp một cách dễ dàng.

**H: Aspose.Tasks for Java có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?**  
Đ: Hoàn toàn, Aspose.Tasks for Java hỗ trợ nhiều phiên bản tệp Microsoft Project, đảm bảo tính tương thích trên các nền tảng.

**H: Tôi có thể tích hợp Aspose.Tasks for Java vào các ứng dụng Java hiện có của mình không?**  
Đ: Có, Aspose.Tasks for Java cung cấp khả năng tích hợp liền mạch, cho phép bạn nâng cao các ứng dụng Java với các tính năng quản lý dự án mạnh mẽ.

**H: Aspose.Tasks for Java có cung cấp tài liệu và hỗ trợ không?**  
Đ: Có, bạn có thể truy cập tài liệu chi tiết và cộng đồng hỗ trợ cho Aspose.Tasks for Java trên [website](https://releases.aspose.com/).

**H: Có bản dùng thử miễn phí cho Aspose.Tasks for Java không?**  
Đ: Có, bạn có thể tải bản dùng thử miễn phí của Aspose.Tasks for Java từ [website](https://reference.aspose.com/tasks/java/) để khám phá các tính năng trước khi quyết định mua.

---

**Cập nhật lần cuối:** 2025-12-23  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}