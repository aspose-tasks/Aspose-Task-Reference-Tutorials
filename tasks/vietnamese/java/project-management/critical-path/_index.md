---
date: 2025-12-23
description: Tìm hiểu cách tạo phụ thuộc công việc và tính toán đường đi quan trọng
  trong MS Project bằng Aspose.Tasks cho Java. Hướng dẫn từng bước cho quản lý dự
  án.
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Tạo các phụ thuộc công việc và tính Đường dẫn quan trọng trong Aspose.Tasks
url: /vi/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Các Phụ Thuộc Nhiệm Vụ và Tính Đường Găng Quan Trọng trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, **bạn sẽ học cách tạo các phụ thuộc nhiệm vụ** và tính đường găng quan trọng trong tệp MS Project bằng Aspose.Tasks cho Java. Hiểu và trực quan hoá đường găng quan trọng giúp bạn giữ dự án đúng tiến độ, trong khi việc liên kết nhiệm vụ đúng cách đảm bảo bất kỳ sự chậm trễ nào đều được hiển thị ngay lập tức. Hãy cùng đi qua toàn bộ quy trình, từ thiết lập môi trường đến hiển thị đường găng quan trọng cuối cùng.

## Câu trả lời nhanh
- **Bước đầu tiên là gì?** Set up your Java project and add the Aspose.Tasks library.  
- **Chế độ nào phải được bật?** `CalculationMode.Automatic` (set automatic calculation).  
- **Làm thế nào để liên kết các nhiệm vụ?** Use `project.getTaskLinks().add(...)` to create task dependencies.  
- **Làm sao tôi có thể xem đường găng quan trọng?** Iterate over `project.getCriticalPath()` and print each task name.  
- **Tôi có cần giấy phép không?** Yes, a valid Aspose.Tasks license is required for production use.

## Tạo phụ thuộc nhiệm vụ là gì?
Tạo phụ thuộc nhiệm vụ có nghĩa là xác định các mối quan hệ (ví dụ: Kết thúc‑đến‑Bắt đầu) giữa các nhiệm vụ để lịch trình phản ánh các ràng buộc thực tế. Trong Aspose.Tasks, việc này được thực hiện thông qua các đối tượng `TaskLink`.

## Tại sao tính đường găng quan trọng trong MS Project?
**Đường găng quan trọng của MS Project** hiển thị chuỗi dài nhất các nhiệm vụ phụ thuộc quyết định thời gian tối thiểu của dự án. Bằng cách tính toán nó, bạn có thể nhanh chóng xác định những nhiệm vụ không thể trễ mà không ảnh hưởng đến toàn bộ thời gian—điều thiết yếu cho các ứng dụng **project management Java** hiệu quả.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

1. Java Development Kit (JDK) được cài đặt trên hệ thống của bạn.  
2. Thư viện Aspose.Tasks cho Java đã được tải về và thêm vào dự án của bạn. Bạn có thể tải nó từ [here](https://releases.aspose.com/tasks/java/).  

## Nhập các gói
Để bắt đầu, nhập các gói cần thiết trong lớp Java của bạn:
```java
import com.aspose.tasks.*;
```

## Cách thiết lập tính toán tự động?
Việc đặt chế độ tính toán thành tự động đảm bảo bất kỳ thay đổi nào đối với nhiệm vụ hoặc liên kết đều cập nhật ngay lập tức lịch trình, bao gồm cả đường găng quan trọng.
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập thư mục dữ liệu
Xác định đường dẫn tới thư mục chứa tệp MS Project của bạn.
```java
String dataDir = "Your Data Directory";
```

### Bước 2: Tải tệp MS Project
Tải tệp dự án hiện có (ví dụ, *New project 2013.mpp*) bằng Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### Bước 3: Thêm nhiệm vụ
Tạo ba nhiệm vụ con đơn giản mà chúng ta sẽ liên kết sau này.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### Bước 4: Tạo liên kết nhiệm vụ (tạo phụ thuộc nhiệm vụ)
Xác định các phụ thuộc giữa các nhiệm vụ. Ở đây chúng ta sử dụng liên kết Kết thúc‑đến‑Bắt đầu, là loại phổ biến nhất.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### Bước 5: Hiển thị đường găng quan trọng (display critical path)
Lấy và in ra đường găng quan trọng. Phương thức `getCriticalPath()` trả về danh sách các nhiệm vụ tạo thành chuỗi quan trọng.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### Bước 6: Xác nhận hoàn thành
Hiển thị một thông báo thân thiện khi quá trình kết thúc.
```java
System.out.println("Process completed Successfully");
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Đường găng quan trọng rỗng** | Đảm bảo `CalculationMode.Automatic` được đặt trước khi thêm liên kết. |
| **Nhiệm vụ chưa được liên kết** | Xác minh rằng bạn đã thêm các đối tượng `TaskLink` cho mỗi phụ thuộc. |
| **Ngoại lệ giấy phép** | Tải một giấy phép Aspose.Tasks hợp lệ trước khi tạo đối tượng `Project`. |

## Câu hỏi thường gặp
### Q: Tôi có thể sử dụng Aspose.Tasks cho Java với bất kỳ phiên bản nào của tệp MS Project không?
A: Có, Aspose.Tasks cho Java hỗ trợ nhiều phiên bản tệp MS Project, bao gồm các tệp .mpp từ MS Project 2003 đến MS Project 2019.  

### Q: Có bản dùng thử miễn phí cho Aspose.Tasks cho Java không?
A: Có, bạn có thể tải bản dùng thử miễn phí từ [here](https://releases.aspose.com/).  

### Q: Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho Java ở đâu?
A: Bạn có thể tìm hỗ trợ trên [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).  

### Q: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?
A: Có, bạn có thể mua giấy phép tạm thời từ [here](https://purchase.aspose.com/temporary-license/).  

### Q: Làm sao tôi có thể mua Aspose.Tasks cho Java?
A: Bạn có thể mua Aspose.Tasks cho Java từ trang web [here](https://purchase.aspose.com/buy).

## Kết luận
Bằng cách thực hiện các bước này, bạn đã **tạo các phụ thuộc nhiệm vụ**, thiết lập **tính toán tự động**, và thành công **hiển thị đường găng quan trọng** cho tệp MS Project của mình. Quy trình làm việc này cung cấp cho bạn toàn quyền kiểm soát logic lịch trình và giúp duy trì dự án trên đúng lộ trình bằng mã **project management** dựa trên Java.

---

**Cập nhật lần cuối:** 2025-12-23  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}