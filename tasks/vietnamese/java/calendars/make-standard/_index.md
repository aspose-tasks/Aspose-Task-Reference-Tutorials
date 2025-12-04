---
date: 2025-12-03
description: Tìm hiểu cách tạo lịch trong Java bằng Aspose.Tasks. Hướng dẫn từng bước
  này cho bạn biết cách tạo lịch chuẩn của MS Project, thêm lịch chuẩn và sử dụng
  Aspose.Tasks một cách hiệu quả.
language: vi
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách tạo lịch – Tạo lịch tiêu chuẩn trong Aspose.Tasks
url: /java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo Lịch – Tạo Lịch Chuẩn trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách tạo lịch** cho các tệp Microsoft Project bằng cách sử dụng thư viện Aspose.Tasks cho Java. Chúng tôi sẽ hướng dẫn cách tạo một lịch chuẩn MS Project, đặt nó làm lịch mặc định (chuẩn), và lưu tệp dự án. Khi kết thúc hướng dẫn, bạn sẽ có thể tích hợp việc tạo lịch vào bất kỳ giải pháp quản lý dự án nào dựa trên Java.

## Câu trả lời nhanh
- **“lịch chuẩn” có nghĩa là gì?** Đó là định nghĩa thời gian làm việc mặc định được sử dụng cho các nhiệm vụ không chỉ định một lịch tùy chỉnh.  
- **Thư viện nào được yêu cầu?** Aspose.Tasks cho Java (phần “cách sử dụng Aspose”).  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Định dạng tệp được tạo là gì?** Tệp Microsoft Project dựa trên XML (`.xml`).  
- **Thời gian triển khai mất bao lâu?** Khoảng 5‑10 phút cho một lịch cơ bản.

## Lịch Chuẩn trong Microsoft Project là gì?
Một **lịch chuẩn** xác định các ngày và giờ làm việc mặc định cho một dự án. Khi bạn thêm một lịch chuẩn, tất cả các nhiệm vụ không có lịch cụ thể được gán sẽ tuân theo lịch này.

## Tại sao nên sử dụng Aspose.Tasks để tạo Lịch?
Aspose.Tasks cung cấp một API thuần Java cho phép bạn thao tác các tệp Project mà không cần cài đặt Microsoft Project. Điều này làm cho nó trở nên lý tưởng cho tự động hoá phía máy chủ, các pipeline CI, hoặc bất kỳ ứng dụng Java nào cần **tạo đối tượng lịch MS Project** một cách lập trình.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo các điều sau đã sẵn sàng:

### Cài đặt Java Development Kit (JDK)
Cài đặt JDK mới nhất từ trang web Oracle hoặc một bản phân phối OpenJDK.

### Thư viện Aspose.Tasks cho Java
Tải thư viện từ [trang tải xuống](https://releases.aspose.com/tasks/java/). Thêm file JAR vào classpath của dự án.

## Nhập Gói
Chúng ta chỉ cần một import cho hướng dẫn này:

```java
import com.aspose.tasks.*;
```

## Hướng Dẫn Từng Bước

### Bước 1: Thiết lập Thư mục Dữ liệu
Xác định nơi tệp dự án được tạo sẽ được lưu.

```java
String dataDir = "Your Data Directory";
```

Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối trên máy của bạn (ví dụ, `C:/Projects/Output/`).

### Bước 2: Tạo một Instance Dự án
Khởi tạo một đối tượng Project mới, rỗng, sẽ chứa lịch.

```java
Project project = new Project();
```

### Bước 3: Định nghĩa và Đặt Lịch làm Chuẩn
Thêm một lịch mới có tên **“My Cal”** và nâng nó lên lịch chuẩn cho dự án.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Mẹo:** Phương thức `makeStandardCalendar` tự động đánh dấu lịch được cung cấp làm mặc định cho dự án, chính xác là những gì bạn cần khi muốn **thêm chức năng lịch chuẩn**.

### Bước 4: Lưu Dự án
Lưu dự án (bao gồm lịch mới) vào một tệp XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Bạn có thể thay đổi tên tệp hoặc định dạng (`SaveFileFormat.Pp`) nếu muốn một phiên bản Project khác.

### Bước 5: Hiển thị Thông báo Hoàn thành
Cung cấp cho mình một dấu hiệu trực quan rằng quá trình đã hoàn thành mà không có lỗi.

```java
System.out.println("Process completed Successfully");
```

## Các Vấn đề Thường gặp & Giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| **File not found** | `dataDir` trỏ tới một thư mục không tồn tại | Tạo thư mục hoặc sử dụng đường dẫn tuyệt đối |
| **License exception** | Chạy mà không có giấy phép Aspose.Tasks hợp lệ trong môi trường sản xuất | Áp dụng file giấy phép bằng `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Empty calendar** | Quên thêm định nghĩa thời gian làm việc | Sử dụng `cal1.getWeekDays().add(WeekDay.DayType.Monday)` v.v., nếu bạn cần giờ tùy chỉnh |

## Câu hỏi Thường gặp

**Q: Aspose.Tasks có tương thích với tất cả các phiên bản của Microsoft Project không?**  
A: Có, Aspose.Tasks hỗ trợ nhiều phiên bản Microsoft Project, từ 2000 đến các bản phát hành mới nhất.

**Q: Tôi có thể tùy chỉnh thêm cài đặt lịch không?**  
A: Chắc chắn! Bạn có thể chỉnh sửa các ngày làm việc, thêm ngoại lệ, và định nghĩa thời gian làm việc cụ thể bằng các lớp `WeekDay` và `WorkingTime`.

**Q: Aspose.Tasks có phù hợp cho các ứng dụng cấp doanh nghiệp không?**  
A: Chắc chắn. Thư viện được thiết kế cho môi trường hiệu năng cao, có khả năng mở rộng và cung cấp hỗ trợ toàn diện cho các tệp Project lớn.

**Q: Aspose.Tasks có cung cấp hỗ trợ kỹ thuật cho nhà phát triển không?**  
A: Có, Aspose cung cấp các diễn đàn chuyên biệt, hỗ trợ qua ticket, và tài liệu phong phú để giúp bạn giải quyết các vấn đề nhanh chóng.

**Q: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?**  
A: Có, bạn có thể khám phá phiên bản dùng thử miễn phí có trên [website](https://purchase.aspose.com/buy), cho phép bạn đánh giá tất cả các tính năng trước khi quyết định.

## Kết luận
Bây giờ bạn đã biết **cách tạo lịch** trong Aspose.Tasks cho Java, đặt chúng làm lịch chuẩn, và lưu tệp Project kết quả. Khả năng này cho phép bạn tự động hoá việc lên lịch dự án, đảm bảo thời gian làm việc nhất quán, và tích hợp dữ liệu Microsoft Project trực tiếp vào các ứng dụng Java của mình.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---