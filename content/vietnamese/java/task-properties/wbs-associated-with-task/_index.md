---
title: WBS được liên kết với nhiệm vụ trong Aspose.Tasks
linktitle: WBS được liên kết với nhiệm vụ trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Làm chủ WBS với Aspose.Tasks cho Java - Tìm hiểu cách đọc và đánh số lại mã WBS của tác vụ. Tăng hiệu quả quản lý dự án!
type: docs
weight: 36
url: /vi/java/task-properties/wbs-associated-with-task/
---
## Giới thiệu
Chào mừng bạn đến với thế giới quản lý dự án với Aspose.Tasks cho Java! Trong hướng dẫn này, chúng ta sẽ đi sâu vào sự phức tạp của Cấu trúc phân chia công việc (WBS) liên quan đến các tác vụ sử dụng Aspose.Tasks cho Java. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu, hướng dẫn này sẽ giúp bạn tìm hiểu các yếu tố cần thiết để quản lý mã WBS một cách hiệu quả.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên máy của bạn.
-  Thư viện Aspose.Tasks dành cho Java đã được tải xuống và thêm vào dự án của bạn. Bạn có thể lấy nó từ[đây](https://releases.aspose.com/tasks/java/).
## Gói nhập khẩu
Đảm bảo bạn nhập các gói cần thiết để khởi động dự án của mình:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Đọc mã WBS
Hãy bắt đầu bằng cách đọc mã WBS liên quan đến nhiệm vụ. Thực hiện theo các bước sau:
## Bước 1: Tải dự án
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Bước 2: Thu thập nhiệm vụ
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Bước 3: Phân tích và tùy chỉnh
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Đoạn mã này đọc và tùy chỉnh mã WBS được liên kết với các tác vụ trong dự án của bạn.
## Đánh số lại mã WBS của tác vụ
Bây giờ, hãy khám phá việc đánh số lại mã WBS cho các tác vụ:
## Bước 1: Tải dự án
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Bước 2: Chọn tất cả nhiệm vụ
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Bước 3: Xuất mã WBS ban đầu
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Bước 4: Đánh số lại mã WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Bước 5: Xuất mã WBS được cập nhật
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Bằng cách làm theo các bước này, bạn sẽ đánh số lại mã WBS cho các nhiệm vụ trong dự án của mình một cách hiệu quả.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách làm việc với mã WBS bằng Aspose.Tasks cho Java. Kiến thức này sẽ giúp bạn quản lý và tùy chỉnh hiệu quả hệ thống phân cấp nhiệm vụ của dự án.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tìm tài liệu về Aspose.Tasks cho Java ở đâu?
 A: Tài liệu có sẵn[đây](https://reference.aspose.com/tasks/java/).
### Hỏi: Làm cách nào tôi có thể tải xuống Aspose.Tasks cho Java?
 Trả lời: Bạn có thể tải xuống[đây](https://releases.aspose.com/tasks/java/).
### Câu hỏi: Có bản dùng thử miễn phí dành cho Aspose.Tasks dành cho Java không?
 Đ: Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?
 Đáp: Hãy ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để hỗ trợ.
### Câu hỏi: Tôi có thể xin giấy phép tạm thời cho Aspose.Tasks cho Java không?
 A: Có, xin giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).