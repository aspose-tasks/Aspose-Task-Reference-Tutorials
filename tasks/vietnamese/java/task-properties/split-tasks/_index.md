---
title: Phân chia nhiệm vụ trong Aspose.Tasks
linktitle: Phân chia nhiệm vụ trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Quản lý tác vụ thành thạo trong Java với Aspose.Tasks! Tìm hiểu cách phân chia nhiệm vụ hiệu quả để tối ưu hóa các mốc thời gian của dự án. Tải ngay!
weight: 29
url: /vi/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Phân chia nhiệm vụ trong Aspose.Tasks

## Giới thiệu
Bạn đang gặp khó khăn với việc quản lý tác vụ trong dự án Java của mình? Aspose.Tasks cho Java cung cấp một giải pháp mạnh mẽ để phân chia nhiệm vụ một cách hiệu quả, nâng cao khả năng quản lý dự án. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình phân chia nhiệm vụ bằng Aspose.Tasks cho Java, giúp bạn tối ưu hóa tiến trình dự án và phân bổ tài nguyên của mình.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên máy của bạn.
-  Thư viện Aspose.Tasks dành cho Java đã được tải xuống và thêm vào dự án của bạn. Bạn có thể tải nó xuống từ[Aspose.Tasks cho tài liệu Java](https://reference.aspose.com/tasks/java/).
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn:
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
## Bước 1: Tạo một dự án mới
Bắt đầu bằng cách tạo một dự án mới bằng thư viện Aspose.Tasks:
```java
// Tạo một dự án mới
Project splitTaskProject = new Project();
```
## Bước 2: Đặt lịch dự án
Đặt cài đặt lịch của dự án để thiết lập dòng thời gian:
```java
// Nhận lịch chuẩn
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Đặt cài đặt lịch của dự án
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (tiếp tục với ví dụ)
```
## Bước 3: Thêm tác vụ gốc
Thêm tác vụ gốc vào dự án của bạn:
```java
// Nhiệm vụ gốc
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Bước 4: Thêm nhiệm vụ mới vào phân chia
Thêm một nhiệm vụ mới vào dự án mà bạn muốn phân chia:
```java
// Thêm nhiệm vụ mới
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Bước 5: Tạo phân công nguồn lực
Tạo sự phân công tài nguyên mới cho nhiệm vụ:
```java
// Tạo phân công tài nguyên mới
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Bước 6: Tạo dữ liệu theo pha thời gian
Tạo dữ liệu theo pha thời gian phân công tài nguyên:
```java
// Tạo dữ liệu theo pha thời gian phân công tài nguyên
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Bước 7: Chia nhiệm vụ
Chia nhiệm vụ thành nhiều phần:
```java
// Chia nhiệm vụ thành 3 phần
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (tiếp tục với ví dụ)
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách phân chia nhiệm vụ bằng Aspose.Tasks cho Java. Thư viện mạnh mẽ này đơn giản hóa việc quản lý tác vụ trong các dự án Java, cung cấp các giải pháp hiệu quả để tối ưu hóa tiến trình dự án và phân bổ tài nguyên.
## Các câu hỏi thường gặp
### Tôi có thể chia nhiệm vụ với thời lượng khác nhau không?
Có, bạn có thể điều chỉnh thời lượng của nhiệm vụ theo yêu cầu dự án của mình.
### Aspose.Tasks for Java có tương thích với tất cả các phiên bản Java không?
Aspose.Tasks for Java được thiết kế để hoạt động trơn tru với nhiều phiên bản Java khác nhau, đảm bảo khả năng tương thích.
### Tôi có thể sử dụng Aspose.Tasks cho Java miễn phí không?
Aspose.Tasks for Java cung cấp bản dùng thử miễn phí, cho phép bạn khám phá các tính năng của nó trước khi mua hàng.
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho Java?
 Tham quan[Aspose.Tasks cho diễn đàn hỗ trợ Java](https://forum.aspose.com/c/tasks/15) để được hỗ trợ và kết nối với cộng đồng.
### Tôi có cần giấy phép tạm thời cho Aspose.Tasks for Java không?
 Bạn có thể xin giấy phép tạm thời từ[liên kết này](https://purchase.aspose.com/temporary-license/) nhằm mục đích kiểm tra và đánh giá.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
