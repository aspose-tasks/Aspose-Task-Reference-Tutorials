---
title: Phân chia ngày kết thúc nhiệm vụ trong Aspose.Tasks
linktitle: Phân chia ngày kết thúc nhiệm vụ trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách phân chia ngày hoàn thành nhiệm vụ một cách dễ dàng bằng cách sử dụng Aspose.Tasks cho Java. Tăng cường quản lý dự án với các mốc thời gian chính xác.
type: docs
weight: 28
url: /vi/java/task-properties/split-task-finish-date/
---
## Giới thiệu
Trong quản lý dự án, việc hiểu rõ các mốc thời gian của nhiệm vụ là rất quan trọng để hoàn thành dự án thành công. Aspose.Tasks cho Java cung cấp các tính năng mạnh mẽ để thao tác các tác vụ dự án một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc phân chia ngày hoàn thành nhiệm vụ bằng Aspose.Tasks, giúp bạn quản lý tiến trình dự án một cách hiệu quả.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
- Kiến thức cơ bản về lập trình Java.
-  Aspose.Tasks cho thư viện Java đã được cài đặt. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/java/).
- Một môi trường phát triển Java được thiết lập.
## Gói nhập khẩu
Bắt đầu bằng cách đưa các gói cần thiết vào dự án Java của bạn:
```java
import com.aspose.tasks.*;
```
## Bước 1: Tìm nhiệm vụ phân chia
Xác định vị trí nhiệm vụ bạn muốn phân chia trong dự án:
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Đọc dự án
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Bước 2: Tìm Lịch dự án
Truy xuất lịch dự án để tính toán ngày chính xác:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Bước 3: Tính ngày kết thúc nhiệm vụ với các khoảng thời gian khác nhau
Bây giờ, hãy tính ngày kết thúc của nhiệm vụ trong các khoảng thời gian khác nhau:
## Bước 3.1: Thời lượng 8 giờ
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Lặp lại mã trên cho các khoảng thời gian khác nhau, điều chỉnh giờ cho phù hợp.
## Phần kết luận
Nắm vững nghệ thuật điều chỉnh ngày hoàn thành nhiệm vụ là điều then chốt để quản lý dự án hiệu quả. Aspose.Tasks dành cho Java đơn giản hóa quy trình này, cho phép bạn sắp xếp hợp lý các mốc thời gian dự án của mình một cách dễ dàng.
## Câu hỏi thường gặp
### Câu hỏi 1: Làm cách nào tôi có thể tải xuống Aspose.Tasks cho Java?
 A1: Bạn có thể tải xuống[đây](https://releases.aspose.com/tasks/java/).
### Câu hỏi 2: Tôi có thể tìm tài liệu về Aspose.Tasks ở đâu?
 A2: Tham khảo tài liệu[đây](https://reference.aspose.com/tasks/java/).
### Câu hỏi 3: Làm cách nào để tôi có được giấy phép tạm thời cho Aspose.Tasks?
 A3: Xin giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi 4: Tôi có thể tìm kiếm sự hỗ trợ cho Aspose.Tasks ở đâu?
 A4: Truy cập diễn đàn hỗ trợ[đây](https://forum.aspose.com/c/tasks/15).
### Câu 5: Tôi có thể mua Aspose.Tasks không?
 A5: Có, bạn có thể mua nó[đây](https://purchase.aspose.com/buy).