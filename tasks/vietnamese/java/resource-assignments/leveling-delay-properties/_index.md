---
title: Xử lý các thuộc tính độ trễ cân bằng trong Aspose.Tasks
linktitle: Xử lý các thuộc tính độ trễ cân bằng cho việc gán tài nguyên trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách xử lý các thuộc tính độ trễ cân bằng cho các nhiệm vụ tài nguyên trong Aspose.Tasks cho Java với hướng dẫn toàn diện này.
weight: 17
url: /vi/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xử lý các thuộc tính độ trễ cân bằng trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu quy trình xử lý các thuộc tính độ trễ cân bằng cho việc gán tài nguyên trong Aspose.Tasks cho Java. Aspose.Tasks là một thư viện Java mạnh mẽ cho phép bạn làm việc với các tệp Microsoft Project mà không yêu cầu cài đặt Microsoft Project trên hệ thống của bạn.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo rằng bạn đã cài đặt Java JDK trên hệ thống của mình. Bạn có thể tải xuống và cài đặt nó từ[trang mạng](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks cho Thư viện Java: Tải xuống thư viện Aspose.Tasks cho Java từ[trang tải xuống](https://releases.aspose.com/tasks/java/).

## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết vào dự án Java của bạn để sử dụng các chức năng của Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Bước 1: Tạo đối tượng dự án
 Khởi tạo một`Project` sự vật:
```java
Project prj = new Project();
```
## Bước 2: Tạo tác vụ
Thêm nhiệm vụ vào dự án:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Bước 3: Đặt ngày bắt đầu và thời lượng nhiệm vụ
Đặt ngày bắt đầu và thời lượng cho tác vụ:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Bước 4: Thêm tài nguyên
Thêm tài nguyên vào dự án:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Bước 5: Tạo phân công nguồn lực
Tạo phân công tài nguyên cho nhiệm vụ và tài nguyên:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Bước 6: Đặt độ trễ cân bằng
Đặt độ trễ cân bằng cho bài tập:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Bước 7: Hiển thị kết quả
In độ trễ cân bằng và các thông tin liên quan khác:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách xử lý các thuộc tính độ trễ cân bằng cho việc gán tài nguyên trong Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn có thể quản lý hiệu quả việc phân công tài nguyên trong các dự án Java của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các thư viện Java khác không?

Trả lời: Có, Aspose.Tasks có thể được tích hợp với các thư viện Java khác để nâng cao khả năng quản lý dự án.

### Câu hỏi: Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?

Trả lời: Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.

### Câu hỏi: Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Tasks ở đâu?

 Đáp: Bạn có thể tìm thấy sự hỗ trợ và nguồn lực trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Câu hỏi: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?

 Trả lời: Có, bạn có thể nhận bản dùng thử miễn phí Aspose.Tasks từ[trang phát hành](https://releases.aspose.com/).

### Câu hỏi: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Tasks?

 Đáp: Bạn có thể yêu cầu giấy phép tạm thời từ[trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) cho mục đích đánh giá.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
