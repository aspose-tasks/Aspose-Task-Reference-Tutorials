---
title: Tạo đường cơ sở nhiệm vụ dự án MS trong Aspose.Tasks
linktitle: Tạo Đường cơ sở nhiệm vụ trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách tạo đường cơ sở nhiệm vụ Microsoft Project trong Java bằng Aspose.Tasks, một thư viện mạnh mẽ để quản lý dữ liệu dự án một cách dễ dàng.
weight: 11
url: /vi/java/task-baselines/create-task-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo đường cơ sở nhiệm vụ dự án MS trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình tạo đường cơ sở nhiệm vụ của Microsoft Project bằng cách sử dụng Aspose.Tasks cho Java. Aspose.Tasks là một thư viện Java mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project mà không yêu cầu cài đặt Microsoft Project. Với Aspose.Tasks, bạn có thể dễ dàng thao tác dữ liệu dự án, bao gồm các nhiệm vụ, tài nguyên và lịch để hợp lý hóa các nhiệm vụ quản lý dự án.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Aspose.Tasks dành cho Java yêu cầu cài đặt JDK trên hệ thống của bạn. Bạn có thể tải xuống và cài đặt JDK từ trang web của Oracle.
2.  Aspose.Tasks cho Thư viện Java: Tải xuống thư viện Aspose.Tasks cho Java từ[Liên kết tải xuống](https://releases.aspose.com/tasks/java/) cung cấp.

## Gói nhập khẩu
Để bắt đầu làm việc với Aspose.Tasks trong dự án Java của bạn, hãy nhập các gói cần thiết:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Bước 1: Tạo đối tượng dự án
```java
Project project = new Project();
```
 Đầu tiên, tạo một cái mới`Project` sự vật. Đối tượng này đại diện cho tệp Microsoft Project mà bạn sẽ làm việc.
## Bước 2: Thêm tác vụ vào dự án
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 Sử dụng`getRootTask()` phương thức, truy cập vào tác vụ gốc của dự án và sau đó thêm một tác vụ mới vào nó bằng cách sử dụng`add()` phương pháp. Đặt tên cho tác vụ trong dấu ngoặc đơn.
## Bước 3: Đặt đường cơ sở cho các nhiệm vụ được chỉ định
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Để đặt đường cơ sở cho các nhiệm vụ cụ thể, hãy tạo danh sách các nhiệm vụ (`myList` trong trường hợp này) và điền vào đó các nhiệm vụ mà bạn muốn đặt đường cơ sở. Sau đó, sử dụng`setBaseline()` phương thức, chỉ định loại đường cơ sở và danh sách các nhiệm vụ.
## Bước 4: Đặt đường cơ sở cho toàn bộ dự án
```java
project.setBaseline(BaselineType.Baseline);
```
 Ngoài ra, bạn có thể đặt đường cơ sở cho toàn bộ dự án bằng cách gọi`setBaseline()` phương thức với loại đường cơ sở được chỉ định.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá cách tạo đường cơ sở nhiệm vụ Microsoft Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước được nêu ở trên, bạn có thể quản lý dữ liệu dự án một cách hiệu quả và hợp lý hóa các nhiệm vụ quản lý dự án một cách dễ dàng.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks cho Java mà không cần cài đặt Microsoft Project không?
Có, Aspose.Tasks for Java cho phép bạn làm việc với các tệp Microsoft Project mà không yêu cầu cài đặt Microsoft Project trên hệ thống của bạn.
### Aspose.Tasks cho Java có tương thích với các phiên bản khác nhau của Microsoft Project không?
Có, Aspose.Tasks for Java hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.
### Tôi có thể thao tác tài nguyên dự án bằng Aspose.Tasks cho Java không?
Hoàn toàn có thể, Aspose.Tasks for Java cung cấp các tính năng mạnh mẽ để thao tác tài nguyên dự án, bao gồm thêm, cập nhật và xóa tài nguyên khi cần.
### Aspose.Tasks cho Java có hỗ trợ thiết lập các phần phụ thuộc của tác vụ không?
Có, bạn có thể dễ dàng thiết lập các phần phụ thuộc của nhiệm vụ bằng cách sử dụng Aspose.Tasks cho Java, cho phép bạn thiết lập chuỗi nhiệm vụ trong dự án của mình.
### Có hỗ trợ kỹ thuật cho Aspose.Tasks cho Java không?
 Có, bạn có thể truy cập hỗ trợ kỹ thuật cho Aspose.Tasks for Java thông qua[diễn đàn hỗ trợ](https://forum.aspose.com/c/tasks/15), nơi bạn có thể đặt câu hỏi và tìm kiếm sự trợ giúp từ cộng đồng cũng như nhân viên hỗ trợ của Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
