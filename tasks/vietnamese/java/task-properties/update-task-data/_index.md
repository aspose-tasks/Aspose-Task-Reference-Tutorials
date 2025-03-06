---
title: Cập nhật dữ liệu tác vụ sang định dạng MPP trong Aspose.Tasks
linktitle: Cập nhật dữ liệu tác vụ sang định dạng MPP trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách cập nhật dữ liệu tác vụ sang định dạng MPP bằng Aspose.Tasks cho Java. Hãy làm theo hướng dẫn từng bước của chúng tôi để quản lý dự án hiệu quả.
weight: 35
url: /vi/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cập nhật dữ liệu tác vụ sang định dạng MPP trong Aspose.Tasks

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về cách cập nhật dữ liệu tác vụ sang định dạng MPP bằng Aspose.Tasks cho Java. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn thực hiện quy trình, đảm bảo rằng bạn nắm bắt từng bước một cách rõ ràng. Aspose.Tasks cho Java cung cấp một giải pháp mạnh mẽ để làm việc với các tệp Microsoft Project và khi kết thúc hướng dẫn này, bạn sẽ có thể cập nhật dữ liệu tác vụ một cách hiệu quả ở định dạng MPP.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Aspose.Tasks dành cho Java: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Tasks. Bạn có thể tải nó xuống từ[trang phát hành](https://releases.aspose.com/tasks/java/).
- Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt Java trên hệ thống của mình.
- Môi trường phát triển tích hợp (IDE): Sử dụng IDE bạn chọn để phát triển Java.
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn. Đoạn mã sau đây trình bày cách nhập gói:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Tạo và cấu hình tác vụ ban đầu
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Tiếp tục với phần còn lại của mã)
```
## 2. Đặt ngày bắt đầu và thời lượng
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Tiếp tục với phần còn lại của mã)
```
## 3. Tạo nhiệm vụ tóm tắt
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Tiếp tục với phần còn lại của mã)
```
## 4. Đặt thời hạn và ghi chú nhiệm vụ
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Tiếp tục với phần còn lại của mã)
```
## 5. Cấu hình các ràng buộc nhiệm vụ
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Tiếp tục với phần còn lại của mã)
```
## 6. Tạo nhiệm vụ bổ sung
```java
//Tạo 10 nhiệm vụ mới
for (int i = 0; i < 10; i++) {
    //... (Tiếp tục với phần còn lại của mã)
}
//... (Tiếp tục với phần còn lại của mã)
```
## 7. Lưu dự án
```java
// Lưu dự án
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Bằng cách làm theo các bước này, bạn đã cập nhật thành công dữ liệu tác vụ sang định dạng MPP bằng Aspose.Tasks cho Java.
## Phần kết luận
Chúc mừng! Bạn đã hoàn thành hướng dẫn toàn diện về cách cập nhật dữ liệu tác vụ ở định dạng MPP bằng Aspose.Tasks cho Java. Thư viện mạnh mẽ này đơn giản hóa các tác vụ quản lý dự án, khiến nó trở thành một công cụ có giá trị cho các nhà phát triển Java.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tìm tài liệu Aspose.Tasks dành cho Java ở đâu?
 A: Tài liệu có sẵn[đây](https://reference.aspose.com/tasks/java/).
### Hỏi: Làm cách nào tôi có thể tải xuống Aspose.Tasks cho Java?
 Trả lời: Bạn có thể tải xuống từ[trang phát hành](https://releases.aspose.com/tasks/java/).
### Hỏi: Có bản dùng thử miễn phí không?
 Đ: Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?
 A: Truy cập diễn đàn hỗ trợ[đây](https://forum.aspose.com/c/tasks/15).
### Hỏi: Bạn có cung cấp giấy phép tạm thời cho mục đích thử nghiệm không?
 A: Có, bạn có thể xin giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
