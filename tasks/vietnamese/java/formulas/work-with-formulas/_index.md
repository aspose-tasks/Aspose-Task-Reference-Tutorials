---
date: 2026-02-13
description: Tìm hiểu cách tính số ngày giữa các ngày, tạo dự án thử nghiệm và thêm
  trường tùy chỉnh khi thao tác với các tệp Microsoft Project bằng Aspose.Tasks cho
  Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tính số ngày giữa các ngày với Aspose.Tasks cho Java
url: /vi/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tính số ngày giữa các ngày với Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **tính số ngày giữa các ngày** bằng cách tạo một dự án thử nghiệm, thêm một trường tùy chỉnh và sử dụng các công thức Microsoft Project thông qua thư viện Aspose.Tasks cho Java. Dù bạn cần tạo lịch trình, tính toán thời hạn, hay tự động hoá báo cáo, Aspose.Tasks cho phép bạn thao tác dữ liệu Project một cách lập trình mà không cần cài đặt phần mềm trên máy tính. Khi kết thúc hướng dẫn, bạn sẽ có một ví dụ có thể chạy được, định nghĩa một thuộc tính mở rộng, đặt thời hạn cho một nhiệm vụ và lưu dự án dưới dạng tệp MPP.

## Trả lời nhanh
- **Nội dung hướng dẫn bao gồm gì?** Tạo dự án thử nghiệm, thêm trường tùy chỉnh, định nghĩa thuộc tính mở rộng và đặt thời hạn cho nhiệm vụ bằng công thức để tính số ngày giữa các ngày.  
- **Thư viện nào được yêu cầu?** Aspose.Tasks cho Java (phiên bản mới nhất).  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc phát triển; cần giấy phép cho môi trường sản xuất.  
- **IDE nào có thể dùng?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, VS Code) hỗ trợ JDK 8+.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút để sao chép mã và chạy thử.

## “Tính số ngày giữa các ngày” trong Aspose.Tasks là gì?
Tính số ngày giữa các ngày có nghĩa là sử dụng công thức Project để trừ một trường ngày (ví dụ, **Finish**) khỏi một trường ngày khác (ví dụ, **Deadline**) và trả về giá trị số ngày. Điều này hữu ích cho việc theo dõi trễ lịch, đo thời gian đệm, hoặc tạo báo cáo tùy chỉnh.

## Tại sao nên dùng Aspose.Tasks để tính số ngày giữa các ngày?
- **Bao phủ đầy đủ API** – truy cập mọi thuộc tính của Project, Task và Resource.  
- **Không cần cài đặt Office** – hoạt động trên máy chủ, pipeline CI và container Docker.  
- **Đa nền tảng** – chạy trên Windows, Linux và macOS với cùng một đoạn mã Java.  
- **Engine công thức mạnh mẽ** – cho phép bạn định nghĩa các phép tính như `[Deadline] - [Finish]` trực tiếp trong tệp dự án.

## Cách đặt thời hạn cho một nhiệm vụ
Đặt thời hạn là bước đầu tiên trước khi bạn có thể tính khoảng thời gian. Thời hạn được lưu trong trường `Tsk.DEADLINE` của một nhiệm vụ và có thể gán bằng một đối tượng `java.util.Calendar`.

## Cách định nghĩa thuộc tính mở rộng
Thuộc tính mở rộng là trường tùy chỉnh sẽ chứa kết quả của công thức. Bạn định nghĩa nó một lần, đặt một bí danh để dễ đọc, và sau đó gắn công thức thực hiện phép trừ ngày.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn đã có:

- **Java Development Kit (JDK) 8+** – tải về từ trang web Oracle hoặc sử dụng OpenJDK.  
- **Aspose.Tasks cho Java** – lấy JAR mới nhất từ [trang tải Aspose.Tasks cho Java](https://releases.aspose.com/tasks/java/) và thêm vào classpath của dự án hoặc vào phụ thuộc Maven/Gradle.

## Nhập gói
Đầu tiên, nhập các lớp cần thiết:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Hướng dẫn từng bước

### Bước 1: Tạo dự án thử nghiệm với trường tùy chỉnh
Chúng ta bắt đầu bằng **tạo một dự án thử nghiệm** và thêm một trường tùy chỉnh sẽ chứa kết quả công thức sau này.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Mẹo:* `CreateTestProjectWithCustomField()` là phương thức trợ giúp tạo một lịch tối thiểu và đăng ký một thuộc tính mở rộng sẵn sàng cho việc gán công thức.

### Bước 2: Định nghĩa thuộc tính mở rộng (Thêm trường tùy chỉnh)
Tiếp theo, chúng ta **định nghĩa một thuộc tính mở rộng** – về cơ bản là trường tùy chỉnh – và đặt cho nó một bí danh thân thiện. Đây là nơi chúng ta **thêm logic trường tùy chỉnh**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** giúp trường hiển thị dễ đọc trong Project.  
- **Formula** tính số ngày giữa ngày *Finish* và *Deadline* của nhiệm vụ – là trọng tâm của *tính số ngày giữa các ngày*.

### Bước 3: Đặt thời hạn cho một nhiệm vụ (Thêm nhiệm vụ Deadline & Đặt thời hạn)
Bây giờ chúng ta **thêm dữ liệu nhiệm vụ deadline** bằng cách đặt thuộc tính *Deadline* cho một nhiệm vụ cụ thể.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Đối tượng `Calendar` xác định thời điểm deadline chính xác.  
- `set(Tsk.DEADLINE, …)` **đặt thời hạn cho nhiệm vụ** đã chọn.

### Bước 4: Lưu dự án (Xử lý tệp Microsoft Project)
Cuối cùng, chúng ta **xử lý Microsoft Project** bằng cách ghi các thay đổi vào tệp MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Bạn có thể mở `SaveFile.mpp` trong Microsoft Project để xem trường tùy chỉnh, kết quả công thức và thời hạn đã được phản ánh trong lịch trình.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Công thức không tính toán** | Đảm bảo chuỗi `Formula` của thuộc tính sử dụng đúng tên trường (ví dụ, `[Deadline]`, `[Finish]`). |
| **Không tìm thấy nhiệm vụ** | Kiểm tra ID nhiệm vụ (`1` trong ví dụ) có tồn tại; dùng `project.getRootTask().getChildren().size()` để debug. |
| **Lỗi giấy phép** | Áp dụng giấy phép Aspose.Tasks hợp lệ trước khi gọi bất kỳ phương thức API nào (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Câu hỏi thường gặp

**Hỏi: Tôi có thể dùng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
Đáp: Có, Aspose.Tasks cung cấp API cho .NET, Java và các nền tảng khác, cho phép bạn **thao tác tệp Microsoft Project** bằng ngôn ngữ bạn chọn.

**Hỏi: Có bản dùng thử miễn phí cho Aspose.Tasks không?**  
Đáp: Chắc chắn. Tải bản dùng thử đầy đủ chức năng từ [trang tải Aspose.Tasks](https://releases.aspose.com/).

**Hỏi: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks ở đâu?**  
Đáp: Tài liệu chính thức được lưu trữ tại [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Hỏi: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Tasks?**  
Đáp: Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để đặt câu hỏi và chia sẻ kinh nghiệm với cộng đồng.

**Hỏi: Tôi có cần giấy phép tạm thời để đánh giá không?**  
Đáp: Có, giấy phép tạm thời có sẵn cho việc thử nghiệm ngắn hạn; bạn có thể yêu cầu tại [đây](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2026-02-13  
**Kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}