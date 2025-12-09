---
date: 2025-12-02
description: Tìm hiểu cách thêm lịch vào dự án, cách tạo lịch MS Project và lưu dự
  án dưới dạng XML bằng Aspose.Tasks cho Java.
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Thêm lịch vào dự án bằng Aspose.Tasks cho Java
url: /vi/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm lịch vào dự án với Aspose.Tasks cho Java

## Giới thiệu
Trong các quy trình quản lý dự án hiện đại, khả năng **thêm lịch vào dự án** thông qua lập trình có thể tiết kiệm hàng giờ chỉnh sửa thủ công. Aspose.Tasks cho Java cung cấp cho các nhà phát triển một API sạch, an toàn kiểu để thao tác các tệp Microsoft Project mà không cần mở client desktop. Trong hướng dẫn này, bạn sẽ học **cách thêm lịch**, **cách tạo lịch MS Project**, và **lưu dự án dưới dạng XML**—tất cả chỉ với vài dòng mã Java.

## Câu trả lời nhanh
- **“Thêm lịch vào dự án” có nghĩa là gì?**  
  Nó có nghĩa là chèn một định nghĩa thời gian làm việc mới (lịch) vào tệp Microsoft Project bằng mã.  
- **Thư viện nào thực hiện việc này?**  
  Aspose.Tasks cho Java cung cấp lớp `Calendar` và container `Project` để quản lý lịch.  
- **Tôi có cần giấy phép không?**  
  Giấy phép đánh giá tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể lưu tệp dưới dạng XML không?**  
  Có — sử dụng `SaveFileFormat.Xml` để xuất dự án dưới dạng tệp XML.  
- **Các yêu cầu tiên quyết là gì?**  
  Java JDK 8+ và JAR Aspose.Tasks cho Java có trong classpath của bạn.

## “Thêm lịch vào dự án” là gì?
Việc thêm lịch vào dự án tạo ra một lịch trình tùy chỉnh xác định các ngày làm việc, ngày nghỉ lễ và giờ làm việc hàng ngày. Lịch này sau đó có thể được gán cho các công việc, nguồn lực hoặc toàn bộ dự án, đảm bảo các phép tính như ngày bắt đầu và thời lượng tuân theo thời gian làm việc đã định nghĩa.

## Tại sao nên dùng Aspose.Tasks cho Java để thêm lịch vào dự án?
- **Kiểm soát toàn diện** – Không cần giao diện UI; tự động tạo hàng loạt lịch cho nhiều dự án.  
- **Tương thích đa phiên bản** – Hoạt động với các tệp Project 2007, 2010, 2013, 2016 và các phiên bản sau.  
- **Không cần cài đặt Microsoft Project** – Chạy trên bất kỳ máy chủ hoặc pipeline CI nào.  
- **Linh hoạt trong xuất khẩu** – Lưu dưới dạng XML, MPP hoặc các định dạng hỗ trợ khác.

## Yêu cầu tiên quyết
- **Java Development Kit (JDK) 8 hoặc mới hơn** đã được cài đặt và cấu hình.  
- **Thư viện Aspose.Tasks cho Java** – tải về từ [trang web chính thức](https://releases.aspose.com/tasks/java/) và thêm JAR vào classpath của dự án.  
- Một IDE hoặc công cụ xây dựng (Maven/Gradle) mà bạn ưa thích.

## Hướng dẫn từng bước

### Bước 1: Nhập gói Aspose.Tasks cần thiết
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

### Bước 4: Định nghĩa các lịch bạn muốn thêm
Sử dụng phương thức `Calendars.add(String name)` để tạo các mục lịch mới. Trong ví dụ này chúng ta thêm ba lịch, nhưng bạn có thể thêm bao nhiêu tùy ý và cấu hình thời gian làm việc sau này.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Mẹo chuyên nghiệp:** Sau khi thêm một lịch, bạn có thể tùy chỉnh các ngày làm việc của nó bằng `cal1.getWeekDays().add(...)` và đặt giờ làm việc hàng ngày bằng `cal1.getBaseCalendar().setWorkingTime(...)`.

### Bước 5: Lưu dự án (lưu dự án dưới dạng XML)
Ghi lại dự án, bao gồm các lịch vừa được thêm, vào một tệp XML. Định dạng này dễ kiểm tra và tương thích với nhiều công cụ.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Bước 6: Hiển thị thông báo hoàn thành
Cho người dùng biết thao tác đã hoàn thành thành công.

```java
System.out.println("Process completed Successfully");
```

Bằng cách thực hiện sáu bước ngắn gọn này, bạn đã **thêm lịch vào dự án** thành công và lưu kết quả dưới dạng tệp XML.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| **`NullPointerException` trên `prj.getCalendars()`** | Đối tượng Project chưa được khởi tạo đúng cách. | Đảm bảo gọi `new Project()` trước khi truy cập lịch. |
| **Không tìm thấy tệp khi lưu** | `dataDir` trỏ tới thư mục không tồn tại. | Tạo thư mục trước hoặc sử dụng đường dẫn tuyệt đối. |
| **Tên lịch hiển thị là “no info”** | Các tên placeholder đã được dùng trong mẫu. | Thay thế bằng các tên có ý nghĩa phản ánh lịch trình (ví dụ: “Lịch nghỉ lễ US”). |
| **XML đã lưu không mở được trong MS Project** | Sử dụng phiên bản Aspose.Tasks lỗi thời. | Cập lên phiên bản Aspose.Tasks cho Java mới nhất. |

## Câu hỏi thường gặp

**H: Aspose.Tasks có thể xử lý các lịch phức tạp với nhiều ngoại lệ không?**  
Đ: Có – sau khi thêm lịch, bạn có thể định nghĩa các ngoại lệ, giờ làm việc và ngày không làm việc bằng các lớp `WeekDay` và `Exception`.

**H: Có thể gán lịch mới cho các công việc cụ thể không?**  
Đ: Chắc chắn. Lấy một công việc qua `prj.getRootTask().getChildren().add("Task Name")` và đặt `task.set(Tsk.CALENDAR, cal3);`.

**H: Thư viện có hỗ trợ lưu ở các định dạng khác như MPP không?**  
Đ: Có. Thay `SaveFileFormat.Xml` bằng `SaveFileFormat.Mpp` hoặc `SaveFileFormat.P6` tùy nhu cầu.

**H: Tôi có cần giấy phép cho các bản dựng phát triển không?**  
Đ: Giấy phép đánh giá tạm thời đủ cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho triển khai sản xuất.

**H: Tôi có thể nhận hỗ trợ ở đâu nếu gặp vấn đề?**  
Đ: Diễn đàn cộng đồng Aspose.Tasks là nguồn tài nguyên tuyệt vời: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Kết luận
Sử dụng Aspose.Tasks cho Java, bạn có thể **thêm lịch vào dự án** một cách lập trình, tùy chỉnh các quy tắc lập lịch, và **lưu dự án dưới dạng XML** chỉ với vài dòng mã. Tự động hóa này giảm thiểu công sức thủ công, loại bỏ lỗi con người và cho phép xử lý hàng loạt các danh mục dự án lớn.

---

**Cập nhật lần cuối:** 2025-12-02  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}