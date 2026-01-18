---
date: 2026-01-18
description: Tìm hiểu cách lên lịch baseline quản lý dự án bằng Aspose.Tasks cho Java,
  cho phép bạn quản lý các baseline dự án và so sánh tiến độ dự kiến với thực tế.
linktitle: Baseline Task Scheduling in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cơ sở quản lý dự án – Lập lịch công việc với Aspose.Tasks
url: /vi/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cơ sở quản lý dự án – Lập lịch nhiệm vụ với Aspose.Tasks

## Giới thiệu về Cơ sở quản lý dự án
Quản lý một **cơ sở quản lý dự án** là nền tảng của việc quản lý dự án hiệu quả. Nó cho phép bạn ghi lại kế hoạch gốc và sau đó so sánh **kế hoạch so với tiến độ thực tế** để bạn có thể phát hiện sự chênh lệch sớm. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách lập lịch cơ sở nhiệm vụ bằng Aspose.Tasks cho Java, cung cấp cho bạn công cụ để **quản lý cơ sở dự án** một cách tự tin và giữ cho dự án của bạn luôn trên đúng hướng.

## Câu trả lời nhanh
- **Cơ sở quản lý dự án đại diện cho gì?**  
  Cơ sở ghi lại lịch trình, chi phí và phạm vi gốc để phân tích chênh lệch sau này.  
- **Thư viện nào xử lý lập lịch cơ sở trong Java?**  
  Aspose.Tasks cho Java cung cấp một API mạnh mẽ để tạo và quản lý các cơ sở.  
- **Tôi có cần giấy phép để chạy mã không?**  
  Bản dùng thử miễn phí hoạt động cho việc thử nghiệm; giấy phép thương mại là bắt buộc cho môi trường sản xuất.  
- **Các yêu cầu chính là gì?**  
  Java Development Kit (JDK) và thư viện Aspose.Tasks cho Java.  
- **Tôi có thể xem ngày cơ sở sau khi thiết lập không?**  
  Có — sử dụng đối tượng `TaskBaseline` để đọc giá trị start, finish và duration.

## Cơ sở quản lý dự án là gì?
Cơ sở quản lý dự án ghi lại phiên bản đã được phê duyệt của lịch trình, ngân sách và phạm vi dự án ngay khi bắt đầu thực hiện. Nó đóng vai trò là điểm tham chiếu để đo lường hiệu suất và xác định các sai lệch trong suốt vòng đời dự án.

## Tại sao nên sử dụng Aspose.Tasks để lập lịch cơ sở?
Aspose.Tasks cung cấp một API thuần Java hoạt động mà không cần cài đặt Microsoft Project. Nó cho phép bạn **tạo một thể hiện dự án**, định nghĩa các nhiệm vụ, thiết lập cơ sở và truy xuất thông tin cơ sở một cách lập trình — lý tưởng cho báo cáo tự động hoặc tích hợp vào các công cụ quản lý dự án tùy chỉnh.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã chuẩn bị các yếu tố sau:

### Môi trường phát triển Java
Đảm bảo bạn đã cài đặt Java Development Kit (JDK) trên hệ thống của mình. Bạn có thể tải và cài đặt JDK từ [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Thư viện Aspose.Tasks cho Java
Tải thư viện Aspose.Tasks cho Java từ [trang tải xuống](https://releases.aspose.com/tasks/java/) và đưa nó vào dự án Java của bạn.

## Nhập các gói
Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

Bây giờ, chúng ta sẽ phân tích ví dụ đã cung cấp thành nhiều bước:

## Bước 1: Tạo một thể hiện Dự án mới
```java
Project project = new Project();
```

## Bước 2: Định nghĩa một Nhiệm vụ và Đặt Cơ sở
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Bước 3: Truy cập Thông tin Cơ sở
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Bước 4: Hiển thị Thời lượng Cơ sở
```java
System.out.println(baseline.getDuration().toString());
```

## Bước 5: Hiển thị Ngày bắt đầu Cơ sở
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Bước 6: Hiển thị Ngày kết thúc Cơ sở
```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

Bằng cách thực hiện các bước này, bạn có thể sử dụng Aspose.Tasks cho Java một cách hiệu quả để **quản lý cơ sở dự án** trong các dự án của mình.

## Các vấn đề thường gặp và giải pháp
- **Baseline not set:** Đảm bảo bạn gọi `project.setBaseline(BaselineType.Baseline)` **sau** khi thêm các nhiệm vụ; nếu không, bộ sưu tập cơ sở sẽ rỗng.  
- **Null values:** Nếu `task.getBaselines()` trả về danh sách rỗng, hãy xác nhận rằng nhiệm vụ đã được thêm vào cấu trúc dự án trước khi thiết lập cơ sở.  
- **Date format:** Các phương thức `getStart()` và `getFinish()` trả về đối tượng `Date`. Sử dụng bộ định dạng nếu bạn cần hiển thị theo định dạng tùy chỉnh.

## Câu hỏi thường gặp
### Aspose.Tasks cho Java có thể xử lý cấu trúc dự án phức tạp không?
Có, Aspose.Tasks cho Java cung cấp khả năng mạnh mẽ để quản lý các dự án có độ phức tạp đa dạng một cách hiệu quả.

### Aspose.Tasks cho Java có tương thích với các thư viện Java khác không?
Chắc chắn, Aspose.Tasks cho Java tích hợp liền mạch với các thư viện Java khác, nâng cao khả năng quản lý dự án của bạn.

### Tôi có thể tùy chỉnh cơ sở nhiệm vụ bằng Aspose.Tasks cho Java không?
Tất nhiên, Aspose.Tasks cho Java cung cấp các chức năng phong phú để tùy chỉnh và quản lý cơ sở nhiệm vụ theo yêu cầu dự án của bạn.

### Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Tasks cho Java từ [trang phát hành](https://releases.aspose.com/).

### Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho Java ở đâu?
Đối với bất kỳ câu hỏi hoặc hỗ trợ nào, bạn có thể truy cập diễn đàn Aspose.Tasks [tại đây](https://forum.aspose.com/c/tasks/15).

## Câu hỏi thường gặp

**Q: Làm thế nào để tạo một thể hiện dự án mới trong Aspose.Tasks?**  
A: Khởi tạo lớp `Project` (`Project project = new Project();`). Điều này tạo một tệp dự án mới sẵn sàng cho các nhiệm vụ và cơ sở.

**Q: Sự khác biệt giữa `BaselineType.Baseline` và các loại cơ sở khác là gì?**  
A: `BaselineType.Baseline` đề cập đến cơ sở chính (Baseline 1). Aspose.Tasks cũng hỗ trợ Baseline 2‑10 cho các snapshot bổ sung.

**Q: Tôi có thể xuất dữ liệu cơ sở ra Excel hoặc CSV không?**  
A: Có, bạn có thể lặp qua các đối tượng `TaskBaseline` và ghi các giá trị vào tệp CSV bằng I/O chuẩn của Java.

**Q: Việc thiết lập một cơ sở có ảnh hưởng đến ngày nhiệm vụ hiện có không?**  
A: Thiết lập cơ sở ghi lại các ngày hiện tại nhưng không thay đổi lịch trình hoạt động của nhiệm vụ. Bạn vẫn có thể điều chỉnh ngày bắt đầu/kết thúc sau khi cơ sở đã được thiết lập.

**Q: Có thể so sánh nhiều cơ sở một cách lập trình được không?**  
A: Chắc chắn. Lấy mỗi cơ sở qua `task.getBaselines().get(index)` và so sánh các thuộc tính `Start`, `Finish` và `Duration` của chúng.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-01-18  
**Kiểm thử với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose