---
date: 2026-02-23
description: Học cách đặt ngày bắt đầu dự án, thiết lập thời lượng công việc và lưu
  dự án dưới dạng MPP bằng Aspose.Tasks cho Java. Quản lý hiệu quả các công việc cha
  và con.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Đặt ngày bắt đầu dự án và quản lý các nhiệm vụ cha và con trong Aspose.Tasks
url: /vi/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt ngày bắt đầu dự án và quản lý nhiệm vụ cha và con trong Aspose.Tasks

## Giới thiệu
Việc tổ chức nhiệm vụ hiệu quả là nền tảng của quản lý dự án thành công, và **đặt ngày bắt đầu dự án** một cách chính xác là bước đầu tiên hướng tới một lịch trình có cấu trúc tốt. Trong hướng dẫn này, bạn sẽ thấy cách **đặt ngày bắt đầu dự án**, cấu hình thời lượng nhiệm vụ, và quản lý quan hệ cha‑con bằng Aspose.Tasks cho Java. Khi hoàn thành, bạn sẽ sẵn sàng **lưu dự án dưới dạng MPP**, cập nhật phần trăm hoàn thành nhiệm vụ, và tùy chỉnh các thuộc tính nhiệm vụ để phù hợp với bất kỳ kịch bản thực tế nào.

## Câu trả lời nhanh
- **Làm thế nào để đặt ngày bắt đầu dự án?** Sử dụng `proj.set(Prj.START_DATE, startDate);` sau khi khởi tạo đối tượng `Project`.  
- **Tôi có thể thêm nhiệm vụ con dưới một nhiệm vụ cha không?** Có – gọi `parentTask.getChildren().add("Child Task")`.  
- **Aspose.Tasks lưu file ở định dạng nào?** Sử dụng `SaveFileFormat.Mpp` để **lưu dự án dưới dạng MPP**.  
- **Làm sao để cập nhật phần trăm hoàn thành nhiệm vụ?** Đặt `Tsk.PERCENT_COMPLETE` trên đối tượng nhiệm vụ.  
- **Tôi có thể lấy giấy phép tạm thời ở đâu?** Truy cập trang giấy phép tạm thời được liên kết trong phần Câu hỏi thường gặp.

## Yêu cầu trước
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:
- Hiểu biết cơ bản về lập trình Java.  
- Thư viện Aspose.Tasks cho Java đã được cài đặt. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/tasks/java/).  
- Một môi trường phát triển tích hợp (IDE) cho Java đã được thiết lập trên hệ thống của bạn.

## Nhập gói
Để bắt đầu, nhập các gói cần thiết vào dự án Java của bạn. Các gói này hỗ trợ tích hợp liền mạch với các chức năng của Aspose.Tasks cho Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Bước 1: Đặt ngày bắt đầu dự án
Bắt đầu bằng việc đặt ngày bắt đầu dự án và các tham số liên quan khác.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Bước 2: Thêm nhiệm vụ cha (Nhiệm vụ 1)
Tạo một nhiệm vụ cha có tên “Task 1” và cấu hình các thuộc tính của nó, bao gồm **đặt thời lượng nhiệm vụ**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Bước 3: Thêm nhiệm vụ cha (Nhiệm vụ 2) với các nhiệm vụ con
Tiếp theo, thêm một nhiệm vụ cha khác có tên “Task 2” và bao gồm các nhiệm vụ con (Task 3 và Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Bước 4: Cấu hình nhiệm vụ con
Xác định ngày bắt đầu, thời lượng và các ràng buộc cho Task 3 và Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Bước 5: Cập nhật phần trăm hoàn thành nhiệm vụ
Điều chỉnh phần trăm hoàn thành cho Task 3 và Task 4 – đây là cách bạn **cập nhật hoàn thành nhiệm vụ**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Bước 6: Lưu dự án
Cuối cùng, **lưu dự án dưới dạng MPP** với các thay đổi đã áp dụng.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Hướng dẫn từng bước này minh họa cách quản lý hiệu quả các nhiệm vụ cha và con bằng Aspose.Tasks cho Java. Hãy thử nghiệm với các cấu hình khác nhau để phù hợp với yêu cầu dự án của bạn.

## Tại sao cần tùy chỉnh thuộc tính nhiệm vụ?
Việc tùy chỉnh các thuộc tính nhiệm vụ như ngày bắt đầu, thời lượng, ràng buộc và phần trăm hoàn thành giúp bạn kiểm soát chi tiết hành vi lịch trình. Dù bạn cần đồng bộ nhiệm vụ với khả năng cung cấp nguồn lực hay thực thi các quy tắc kinh doanh, Aspose.Tasks cho phép bạn **tùy chỉnh thuộc tính nhiệm vụ** một cách lập trình.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Ngày bắt đầu không được áp dụng** | Đảm bảo bạn gọi `proj.set(Prj.START_DATE, …)` **sau** khi tạo đối tượng `Project` và **trước** khi thêm nhiệm vụ. |
| **Nhiệm vụ con kế thừa ràng buộc sai** | Đặt rõ ràng `ConstraintType` và `ConstraintDate` cho mỗi nhiệm vụ con, như đã minh họa ở Bước 4. |
| **File đã lưu không mở được trong MS Project** | Kiểm tra bạn đang sử dụng phiên bản mới nhất của Aspose.Tasks và lưu bằng `SaveFileFormat.Mpp`. |
| **Phần trăm không hiển thị trong UI** | Sau khi đặt `Tsk.PERCENT_COMPLETE`, gọi `proj.calculateTaskSchedule()` nếu cần tính lại ngày. |

## Câu hỏi thường gặp
### Aspose.Tasks cho Java có tương thích với các định dạng file dự án khác nhau không?
Có, Aspose.Tasks cho Java hỗ trợ nhiều định dạng file dự án, bao gồm MPP và XML.

### Tôi có thể tùy chỉnh các thuộc tính nhiệm vụ ngoài những gì trong hướng dẫn này không?
Chắc chắn! Aspose.Tasks cho Java cung cấp nhiều tùy chọn tùy chỉnh cho các thuộc tính nhiệm vụ.

### Có diễn đàn cộng đồng nào cho Aspose.Tasks để tôi có thể tìm kiếm hỗ trợ không?
Có – bạn có thể truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận hỗ trợ từ cộng đồng.

### Làm sao tôi có thể lấy giấy phép tạm thời cho Aspose.Tasks cho Java?
Bạn có thể lấy giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks cho Java ở đâu?
Tài liệu có sẵn [tại đây](https://reference.aspose.com/tasks/java/).

**Câu hỏi & Trả lời bổ sung**

**H: Làm thế nào để lập trình lấy giấy phép tạm thời?**  
Đ: Tải file giấy phép tạm thời bằng cách sử dụng `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**H: Tôi có thể thay đổi đơn vị thời lượng mặc định của nhiệm vụ không?**  
Đ: Có – sửa đối số `TimeUnitType` trong `proj.getDuration(value, TimeUnitType.YourChoice)`.

**H: Phiên bản Aspose.Tasks nào cần thiết để sử dụng `SaveFileFormat.Mpp`?**  
Đ: Tất cả các phiên bản gần đây (2022‑2026) đều hỗ trợ lưu dưới dạng MPP; hãy kiểm tra ghi chú phát hành để biết thay đổi quan trọng.

---

**Cập nhật lần cuối:** 2026-02-23  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}