---
date: 2026-02-26
description: Tìm hiểu cách chia nhỏ công việc với Aspose.Tasks cho Java – hướng dẫn
  toàn diện về cách chia nhỏ công việc, thiết lập lịch dự án và tạo phân công nguồn
  lực.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách chia tách nhiệm vụ trong Aspose.Tasks
url: /vi/java/task-properties/split-tasks/
weight: 29
---

 with translations.

Be careful to keep markdown formatting exactly.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tách Nhiệm Vụ trong Aspose.Tasks

## Giới thiệu
Nếu bạn đang tìm kiếm **cách tách nhiệm vụ** trong một dự án dựa trên Java, bạn đã đến đúng nơi. Aspose.Tasks for Java cung cấp cho bạn một cách tiếp cận lập trình sạch sẽ để chia một nhiệm vụ kéo dài thành các phần nhỏ hơn, dễ quản lý, giúp cân bằng tài nguyên, báo cáo chính xác và thời gian dự án chặt chẽ hơn. Trong hướng dẫn này, chúng tôi sẽ đi qua toàn bộ quy trình — từ việc thiết lập lịch dự án đến tạo một phân công tài nguyên và cuối cùng là tách nhiệm vụ thành nhiều đoạn.

## Câu trả lời nhanh
- **Task splitting là gì?** Việc chia một nhiệm vụ duy nhất thành nhiều khoảng thời gian nhỏ hơn trong khi vẫn giữ tổng thời lượng của nó.  
- **Tại sao tách nhiệm vụ trong Java?** Nó cho phép phân bổ tài nguyên chính xác và theo dõi tiến độ tốt hơn.  
- **Thư viện nào hỗ trợ?** Aspose.Tasks for Java cung cấp các phương thức tích hợp sẵn để tách và time‑phasing.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; cần giấy phép cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Thư viện hoạt động với Java 8 và các phiên bản mới hơn.

## Yêu cầu trước
Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:
- Java Development Kit (JDK) đã được cài đặt trên máy của bạn.  
- Thư viện Aspose.Tasks for Java đã được tải xuống và thêm vào dự án. Bạn có thể tải nó từ [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).

## Nhập khẩu các gói
Bắt đầu bằng việc nhập các gói cần thiết vào dự án Java của bạn:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Bước 1: Tạo một Dự án Mới
Bắt đầu bằng cách tạo một dự án mới sử dụng thư viện Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Bước 2: Đặt Lịch Dự Án
Việc đặt **project calendar** xác định các ngày làm việc, ngày nghỉ và tổng thời gian cho lịch trình của bạn. Bước này rất quan trọng để tính toán time‑phased một cách chính xác.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Bước 3: Thêm Nhiệm Vụ Gốc
Mỗi dự án cần một container gốc. Thêm một nhiệm vụ gốc sẽ cung cấp vị trí để gắn tất cả các nhiệm vụ tiếp theo.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Bước 4: Thêm Nhiệm Vụ Mới để Tách
Tạo nhiệm vụ mà bạn muốn tách. Ở đây chúng tôi đặt thời lượng ba ngày làm ví dụ.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Bước 5: Tạo Phân Công Tài Nguyên
Một **resource assignment** liên kết một tài nguyên (hoặc placeholder) với nhiệm vụ. Điều này là bắt buộc trước khi tạo dữ liệu time‑phased.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Bước 6: Tạo Dữ liệu Timephased
Dữ liệu time‑phased biểu thị cách công việc được phân phối trong suốt thời lượng của nhiệm vụ. Việc tạo nó chuẩn bị nhiệm vụ cho quá trình tách.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Bước 7: Tách Nhiệm Vụ
Bây giờ chúng ta **split the task into parts**. Trong ví dụ này, chúng tôi chia nhiệm vụ ba ngày thành ba đoạn một ngày.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Tại sao nên Tách Nhiệm Vụ?
Tách nhiệm vụ cho phép bạn kiểm soát chi tiết hơn về:
- **Resource leveling:** Gán các tài nguyên khác nhau cho mỗi đoạn.  
- **Progress tracking:** Cập nhật trạng thái theo từng đoạn.  
- **Reporting:** Tạo các biểu đồ Gantt và báo cáo chi tiết hơn.

## Các Vấn đề Thường gặp và Giải pháp
- **Missing calendar data:** Đảm bảo bạn gọi `timephasedDataFromTaskDuration` trước khi tách.  
- **Zero‑duration segments:** Kiểm tra mỗi khoảng tách có thời lượng khác 0; nếu không, thư viện sẽ bỏ qua.  
- **License exceptions:** Chạy mà không có giấy phép hợp lệ có thể thêm watermark vào các tệp xuất.

## Câu hỏi Thường gặp
### Tôi có thể tách nhiệm vụ với các thời lượng khác nhau không?
Có, bạn có thể điều chỉnh thời lượng của mỗi phần để phù hợp với yêu cầu dự án của mình.

### Aspose.Tasks for Java có tương thích với tất cả các phiên bản Java không?
Aspose.Tasks for Java được thiết kế để hoạt động liền mạch với Java 8 và các phiên bản mới hơn, đảm bảo tính tương thích rộng rãi.

### Tôi có thể sử dụng Aspose.Tasks for Java miễn phí không?
Aspose.Tasks for Java cung cấp bản dùng thử miễn phí, cho phép bạn khám phá các tính năng trước khi mua.

### Làm thế nào tôi có thể nhận hỗ trợ cho Aspose.Tasks for Java?
Truy cập [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) để được hỗ trợ và kết nối với cộng đồng.

### Tôi có cần giấy phép tạm thời cho Aspose.Tasks for Java không?
Bạn có thể lấy giấy phép tạm thời từ [this link](https://purchase.aspose.com/temporary-license/) để thử nghiệm và đánh giá.

---

**Cập nhật lần cuối:** 2026-02-26  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}