---
title: Quản lý thời lượng của nhiệm vụ trong Aspose.Tasks
linktitle: Quản lý thời lượng của nhiệm vụ trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Khám phá Aspose.Tasks cho Java và tìm hiểu cách quản lý thời lượng nhiệm vụ một cách dễ dàng. Hãy làm theo hướng dẫn từng bước của chúng tôi để lập kế hoạch và thực hiện dự án hiệu quả.
weight: 20
url: /vi/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Quản lý thời lượng của nhiệm vụ trong Aspose.Tasks

## Giới thiệu
Aspose.Tasks cho Java cung cấp một giải pháp mạnh mẽ để quản lý các nhiệm vụ và thời lượng dự án một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý thời lượng của các nhiệm vụ bằng Aspose.Tasks, hướng dẫn bạn qua từng bước. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay người mới bắt đầu, hướng dẫn này sẽ giúp bạn nắm bắt được những điều cần thiết khi làm việc với thời lượng nhiệm vụ trong dự án của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Bộ công cụ phát triển Java (JDK): Đảm bảo rằng bạn đã cài đặt Java trên máy của mình. Bạn có thể tải nó xuống[đây](https://www.oracle.com/java/technologies/javase-downloads.html).
- Thư viện Aspose.Tasks: Tải xuống và đưa thư viện Aspose.Tasks vào dự án của bạn. Bạn có thể tìm thấy thư viện[đây](https://releases.aspose.com/tasks/java/).
## Gói nhập khẩu
Trong dự án Java của bạn, hãy nhập các gói cần thiết để hoạt động với Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Bước 1: Thiết lập dự án của bạn
```java
// Tạo một dự án mới
Project project = new Project();
```
## Bước 2: Thêm nhiệm vụ mới
```java
// Thêm nhiệm vụ mới vào dự án
Task task = project.getRootTask().getChildren().add("Task");
```
## Bước 3: Nhận và chuyển đổi thời lượng nhiệm vụ
```java
// Nhận thời gian thực hiện nhiệm vụ theo ngày (đơn vị thời gian mặc định)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Chuyển đổi thời lượng sang đơn vị thời gian giờ
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Bước 4: Cập nhật thời lượng nhiệm vụ thành 1 tuần
```java
// Tăng thời gian thực hiện nhiệm vụ lên 1 tuần
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Bước 5: Giảm thời lượng nhiệm vụ
```java
// Giảm thời gian thực hiện nhiệm vụ
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Bằng cách làm theo các bước này, bạn đã quản lý thành công thời lượng của các tác vụ trong dự án Aspose.Tasks for Java của mình.
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày các kiến thức cơ bản về quản lý thời lượng tác vụ bằng cách sử dụng Aspose.Tasks cho Java. Giờ đây, bạn có thể tự tin kết hợp các kỹ thuật này vào dự án của mình để quản lý thời gian thực hiện nhiệm vụ một cách hiệu quả.
## Câu hỏi thường gặp
### Aspose.Tasks có tương thích với tất cả các phiên bản Java không?
Aspose.Tasks tương thích với Java 6 và các phiên bản mới hơn.
### Tôi có thể sử dụng Aspose.Tasks cho các dự án thương mại không?
 Có, bạn có thể sử dụng Aspose.Tasks cho cả dự án cá nhân và thương mại. Thăm nom[đây](https://purchase.aspose.com/buy) để biết chi tiết cấp phép.
### Tôi có thể tìm thêm sự hỗ trợ và nguồn lực ở đâu?
 Tham quan[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được cộng đồng hỗ trợ và thảo luận.
### Làm cách nào để có được giấy phép tạm thời cho mục đích thử nghiệm?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/) để kiểm tra và đánh giá.
### Có bản dùng thử miễn phí cho Aspose.Tasks không?
 Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/) để khám phá Aspose.Tasks trước khi mua hàng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
