---
title: Cập nhật & Lên lịch lại dự án MS trong Aspose.Tasks
linktitle: Cập nhật dự án và sắp xếp lại công việc chưa hoàn thành trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách cập nhật và sắp xếp lại các tệp MS Project theo chương trình bằng Aspose.Tasks cho Java.
type: docs
weight: 23
url: /vi/java/project-file-operations/update-project-reschedule-work/
---
## Giới thiệu
Microsoft Project là phần mềm quản lý dự án được sử dụng rộng rãi, cho phép người dùng quản lý các nhiệm vụ, tài nguyên và tiến trình một cách hiệu quả. Aspose.Tasks cho Java cung cấp một bộ API mạnh mẽ để thao tác với các tệp Microsoft Project theo chương trình. Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách cập nhật các tệp MS Project và sắp xếp lại công việc chưa hoàn thành bằng Aspose.Tasks cho Java.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
2.  Aspose.Tasks cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).
3. Hiểu biết cơ bản về ngôn ngữ lập trình Java.

## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết vào mã Java của bạn:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Bước 1: Thiết lập dự án
Khởi tạo một đối tượng Project mới và xác định các nhiệm vụ bên trong nó cùng với thời lượng và sự phụ thuộc của chúng.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Xác định nhiệm vụ và thời hạn của chúng
// ...
// Xác định sự phụ thuộc của nhiệm vụ
// ...
// Lưu trạng thái dự án ban đầu
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Bước 2: Cập nhật công việc dự án
Cập nhật công việc của dự án để đánh dấu nó là hoàn thành cho đến một ngày nhất định.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Lưu dự án đã cập nhật
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Bước 3: Lên lịch lại công việc chưa hoàn thành
Lên lịch lại mọi công việc chưa hoàn thành để bắt đầu sau một ngày được chỉ định.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Lưu dự án đã lên lịch lại
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách cập nhật các tệp MS Project và sắp xếp lại công việc chưa hoàn thành bằng Aspose.Tasks cho Java. Điều này có thể đặc biệt hữu ích trong các tình huống mà các mốc thời gian của dự án cần được điều chỉnh dựa trên tiến độ hoặc các ưu tiên thay đổi.

## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks cho Java có thể xử lý các cấu trúc dự án phức tạp không?
Trả lời: Có, Aspose.Tasks cho Java cung cấp các API mạnh mẽ để quản lý các tác vụ, phần phụ thuộc, tài nguyên và các thành phần khác của dự án một cách hiệu quả.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
 Đ: Có, bạn có thể dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho Java?
 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) cho bất kỳ sự trợ giúp hoặc thắc mắc.
### Câu hỏi: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?
 Đáp: Có, giấy phép tạm thời có sẵn để mua[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Tôi có thể tìm tài liệu chi tiết về Aspose.Tasks cho Java ở đâu?
 Đáp: Bạn có thể tham khảo tài liệu[đây](https://reference.aspose.com/tasks/java/) để có hướng dẫn toàn diện và tài liệu tham khảo API.