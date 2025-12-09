---
date: 2025-12-03
description: Tìm hiểu cách tạo lịch trong MS Project, chuyển đổi dự án sang định dạng
  MPP và lưu dự án MPP một cách dễ dàng bằng Aspose.Tasks cho Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tạo Lịch MS Project và Lưu dưới dạng MPP với Aspose.Tasks
url: /vi/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Lịch MS Project và Lưu dưới dạng MPP với Aspose.Tasks

## Giới thiệu

Trong quản lý dự án hiện đại, bạn thường cần **tạo lịch MS Project** và sau đó chia sẻ chúng ở định dạng MPP gốc. Dù bạn đang hợp nhất lịch trình từ nhiều nguồn khác nhau hay di chuyển dữ liệu kế thừa, khả năng tạo lịch một cách lập trình sẽ tiết kiệm thời gian và loại bỏ lỗi thủ công. Hướng dẫn này sẽ dẫn bạn qua toàn bộ quy trình tạo lịch trong MS Project, tùy chỉnh nó, và cuối cùng **chuyển đổi dự án sang MPP** bằng API Aspose.Tasks cho Java.

## Câu trả lời nhanh
- **Hướng dẫn này đề cập đến gì?** Tạo lịch trong MS Project và lưu nó dưới dạng tệp MPP bằng Aspose.Tasks cho Java.  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần cho môi trường sản xuất.  
- **Yêu cầu phiên bản Java nào?** Java 8 hoặc cao hơn (JDK 8+).  
- **Có thể tùy chỉnh lịch không?** Có – bạn có thể thêm giờ làm việc, ngoại lệ và ngày lễ.  
- **Thời gian triển khai khoảng bao lâu?** Khoảng 10‑15 phút cho một lịch cơ bản.

## “tạo lịch MS Project” là gì?

Tạo lịch MS Project có nghĩa là định nghĩa một cách lập trình các ngày làm việc, giờ làm và ngoại lệ điều khiển việc lên lịch nhiệm vụ trong tệp Microsoft Project. Bằng cách sử dụng Aspose.Tasks, bạn có thể xây dựng, sửa đổi và lưu các lịch này mà không cần mở giao diện Microsoft Project.

## Tại sao nên dùng Aspose.Tasks cho nhiệm vụ này?

- **Tương thích .NET/Java đầy đủ** – hoạt động trên bất kỳ nền tảng nào hỗ trợ Java.  
- **Không cần COM hay cài đặt Office** – lý tưởng cho tự động hoá phía máy chủ.  
- **API phong phú** – hỗ trợ mọi thuộc tính của lịch, bao gồm tuần làm việc tùy chỉnh và ngày lễ.  
- **Xuất trực tiếp MPP** – bạn có thể **lưu dự án dưới dạng MPP** mà không cần chuyển đổi trung gian.

## Điều kiện tiên quyết

1. **Java Development Kit (JDK) 8+** – đảm bảo `java -version` trả về 1.8 hoặc mới hơn.  
2. **Aspose.Tasks cho Java** – tải JAR mới nhất từ [trang web Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo nào bạn thích.  
4. **Kiến thức Java cơ bản** – quen thuộc với lớp, phương thức và I/O tệp.

## Hướng dẫn từng bước

### Bước 1: Nhập các gói cần thiết

Đầu tiên, đưa các lớp Aspose.Tasks và tiện ích Java vào phạm vi.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Bước 2: Thiết lập thư mục dữ liệu

Xác định nơi lưu trữ mẫu đầu vào và các tệp đầu ra. Thay thế placeholder bằng đường dẫn thực tế trên máy của bạn.

```java
String dataDir = "Your Data Directory";
```

### Bước 3: Định nghĩa tên tệp đầu vào và đầu ra

Chúng ta sẽ tải một tệp MPP hiện có (hoặc một dự án trống) và ghi kết quả vào một tệp mới.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Bước 4: Tải dự án và thêm lịch mới

Tạo một thể hiện `Project` từ tệp nguồn và thêm một lịch có tên **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Bước 5: Tùy chỉnh lịch (Tùy chọn)

Nếu bạn cần giờ làm việc, ngày lễ hoặc ngoại lệ cụ thể, hãy gọi phương thức trợ giúp của riêng bạn. Ví dụ sử dụng `GetTestCalendar` chỉ là placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Mẹo chuyên nghiệp:** Bạn có thể thao tác trực tiếp `cal1.getWeekDays()` để đặt giờ làm việc cho mỗi ngày trong tuần.

### Bước 6: Gán lịch cho dự án

Yêu cầu dự án sử dụng lịch mới tạo cho tất cả các phép tính lên lịch.

```java
project.set(Prj.CALENDAR, cal1);
```

### Bước 7: Lưu dự án dưới dạng MPP

Bây giờ **chuyển đổi dự án sang MPP** bằng cách lưu với tùy chọn `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Bước 8: Xác nhận hoàn thành thành công

Một thông báo console đơn giản sẽ cho bạn biết quá trình đã kết thúc mà không có lỗi.

```java
System.out.println("Process completed Successfully");
```

## Các trường hợp sử dụng phổ biến

- **Tự động tạo lịch** cho các dự án lặp lại (ví dụ: sprint hàng tuần).  
- **Di chuyển lịch CSV hoặc Excel kế thừa** vào tệp MS Project đầy đủ tính năng.  
- **Báo cáo phía máy chủ** nơi một dịch vụ web trả về tệp MPP theo yêu cầu.

## Khắc phục sự cố & Những lỗi thường gặp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| `NullPointerException` khi `project.save` | `dataDir` trỏ tới thư mục không tồn tại | Đảm bảo thư mục tồn tại hoặc tạo nó bằng mã. |
| Lịch không được áp dụng cho các nhiệm vụ | Các nhiệm vụ vẫn tham chiếu lịch mặc định | Sau khi đặt `Prj.CALENDAR`, cũng cập nhật `Task.CALENDAR` cho từng nhiệm vụ nếu chúng đã bị ghi đè. |
| Tệp đầu ra có kích thước 0 KB | Thiếu quyền ghi | Chạy JVM với quyền hệ thống tệp phù hợp hoặc chọn đường dẫn có thể ghi. |

## Câu hỏi thường gặp

**H: Aspose.Tasks cho Java có tương thích với các phiên bản MS Project khác nhau không?**  
Đ: Có, Aspose.Tasks cho Java hỗ trợ một loạt các phiên bản MS Project, từ Project 2007 tới bản phát hành mới nhất, đảm bảo tính tương thích liền mạch.

**H: Tôi có thể tùy chỉnh lịch theo yêu cầu dự án cụ thể không?**  
Đ: Chắc chắn. Bạn có thể định nghĩa ngày làm việc, thiết lập tuần làm việc tùy chỉnh, thêm ngày lễ và thậm chí tạo nhiều lịch trong cùng một tệp dự án.

**H: Aspose.Tasks cho Java có cung cấp hỗ trợ và trợ giúp khi gặp sự cố không?**  
Đ: Có, bạn có thể nhận trợ giúp từ diễn đàn cộng đồng Aspose.Tasks [tại đây](https://forum.aspose.com/c/tasks/15).

**H: Có bản dùng thử miễn phí cho Aspose.Tasks cho Java không?**  
Đ: Có, bản dùng thử đầy đủ chức năng có sẵn [tại đây](https://releases.aspose.com/).

**H: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Tasks cho Java?**  
Đ: Giấy phép tạm thời có thể yêu cầu qua trang web Aspose [tại đây](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2025-12-03  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}