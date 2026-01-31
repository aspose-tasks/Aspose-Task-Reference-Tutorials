---
date: 2026-01-31
description: Tìm hiểu cách tạo lịch dự án, thêm lịch ngày lễ và xuất XML dự án bằng
  Aspose.Tasks cho Java.
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách tạo lịch dự án bằng Aspose.Tasks cho Java
url: /vi/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo lịch dự án với Aspose.Tasks cho Java

## Giới thiệu
Trong các quy trình quản lý dự án hiện đại, khả năng **tạo lịch dự án** một cách lập trình có thể tiết kiệm hàng giờ chỉnh sửa thủ công. Asp sạch, không cần mở client desktop. Trong hướng dẫn **cách thêm lịch**, **cách tạo lịch MS Project**, và **xuất XML dự án** — chỉ với vài dòng mã Java.

## Câu trả lời nhanh
- **“Tạo lịch dự án” có nghĩa là gì?**  
 mới (lịch) bên trong tệp Microsoft Project thông qua mã.  
- **Th cung cấp lớp `Calendar` và container `Project` để quản lý lịch.  
- **Tôi có cần giấy phép không?**  
  Giấy phép đánh giá tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể xuất tệp dưới dạng XML không?**  
  Có — sử dụng `SaveFileFormat.Xml` để xuất dự án dưới dạng tệp XML.  
- **Các yêu cầu trước là gì?**  
  Java JDK 8+ và JAR Aspose.Tasks cho Java trong classpath của bạn.

## “Tạo lịch dự án” là gì?
Tạo một lịch dự án định nghĩa các ngày làm việc, ngày nghỉ lễ và giờ làm việc hàng ngày cho một dự án. Khi lịch được gắn vào các công việc, nguồn lực, hoặc toàn bộ dự án, tất cả các phép tính lập lịch sẽ tuân theo thời gian làm việc đã định nghĩa.

## Tại sao nên sử dụng Aspose.Tasks cho Java để tạo lịch dự án?
- **Kiểm soát đầy đủ** – Tự động tạo hàng loạt lịch cho nhiều dự án mà không cần giao diện người dùng.  
- **Tương thích đa phiên bản** – Hoạt động với các tệp Project 2007, 2010, 2013, 2016 đặt Microsoft Project** – Chạy trên bất kỳ máy chủ hoặc pipeline CI nào.  
- **Linh hoạt khi xuất** – Lưu dưới dạng XML, MPP hoặc các định dạng hỗ trợ khác.

## Yêu cầu trước
- **Java Development Kit (JDK) 8 hoặc mới hơn** đã được cài đặt và cấu hình.  
- **Thư viện – tải xuống từ [trang web chính thức](https://releases.aspose.com/tasks/java/)Maven/Gradle) mà bạn### Bước 1: Nhập gói Aspose.Tasks cần thiết
Đầu tiên, đưa các lớp Aspose.Tasks vào phạm vi để bạn có thể làm việc với dự án và lịch.

```java
import com.aspose.tasks.*;
```

### Bước 2: Đặt đường dẫn thư mục dữ liệu
Xác định nơi tệp dự án được tạo sẽ được ghi. Thay thế placeholder bằng đường dẫn tuyệt đối hoặc tương đối trên máy của bạn.

```java
String dataDir = "Your Data Directory";
```

### Bước 3: Tạo một thể hiện Project mới
Khởi tạo một đối tượng `Project` – đại diện cho một tệp Microsoft Project trống mà bạn có thể điền dữ liệu.

```java
Project prj = new Project();
```

### Bước 4: Xác định các lịch bạn muốn thêm
Sử dụng phương thức `Calendars.add(String name)` để tạo các mục lịch mới. Trong ví dụ này chúng ta thêm ba lịch, nhưng bạn có thể thêm bao nhiêu tùy ý và cấu hình thời gian làm việc sau này.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Mẹo chuyên nghiệp:** Sau khi thêm một lịch, bạn có thể tùy chỉnh các ngày làm việc của ngày bằng `cal1.getBaseCalendar().setWorkingTime(...)`.

### Bước 5: Lưu dự án (xuất XML dự án)
Lưu dự án, bao gồm các lịch mới được thêm, vào một tệp XML. Định dạng này dễ kiểm tra và tương thích với nhiều công cụ.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Bước 6: Hiển thị thông báo hoàn thành
Cho người dùng biết thao tác đã hoàn thành thành công.

```java
System.out.println("Process completed Successfully");
```

Bằng cách thực hiện sáu bước ngắn gọn này, bạn đã **tạo thành công một lịch dự án**, thêm nó vào tệp Microsoft Project dưới dạngấn|-------|------------|----------------|
| **`NullPointerException` trên `prj.getCalendars()`** | Đối tượng Project không được khởi tạo đúng **File không tìm thấy khi lưu** | `dataDir` trỏ tới thư mục không tồn tại. **Tên lịch hiển thị là “no info”** | Các tên placeholder đã được sử dụng trong mẫu. | Thay thế bằng các tên có ý nghĩa phản ánh lịch trình (ví dụ: “Lịch nghỉ lễ Mỹ”). |
| **XML đã lưu không mở được trong MS Project** | Sử dụng phiên bản Aspose.Tasks lỗi nhật lên phiên bản Aspose hỏi thường gặp

**Q:**  
A: Có – sau khi thêm một lịch các lớp `WeekDay` và `Exception`.

**Q: Có thể gán lịch mới cho các công việc cụ thể không?**  
A: Chắc chắn.getChildren().add("Task Name")` và đặt `task.set(Tsk.CALENDAR, cal3);`.

**Q: Thư viện có hỗ trợ lưu ở các định dạng khác như MPP không?**  
A: Có. Thpp` hoặc `SaveFileFormat.P6` tùy nhu cầu.

**Q: Tôi có cần giấy phép cho: Giấy phép đánh giá tạm thời đủ cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho triển khai sản xuất.

**Q: Tôi có thể nhận được hỗ trợ nếu gặp vấn đề ở đâu?**  
A: Diễn đàn cộng đồng Aspose.Tasks là nguồn tài nguyên tuyệt vời: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Kết dự án**, tùy chỉnh các quy tắc lập lịch, và **xuất XML dự án** chỉ với vài dòng mã. Tự động hoá này giảm thiểu công sức thủ công, loại bỏ lỗi con người, và cho phép xử lý hàng loạt các danh mục dự án lớn.

---

**Cập nhật lần cuối:** 2026-01-31  
**Kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}