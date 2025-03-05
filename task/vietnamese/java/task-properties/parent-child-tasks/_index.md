---
title: Quản lý nhiệm vụ của phụ huynh và trẻ em trong Aspose.Tasks
linktitle: Quản lý nhiệm vụ của phụ huynh và trẻ em trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Nâng cao hiệu quả quản lý dự án với Aspose.Tasks cho Java. Tìm hiểu cách quản lý nhiệm vụ của cha mẹ và con cái theo từng bước. Bắt đầu ngay bây giờ!
type: docs
weight: 24
url: /vi/java/task-properties/parent-child-tasks/
---
## Giới thiệu
Trong lĩnh vực quản lý dự án, việc tổ chức nhiệm vụ hiệu quả là rất quan trọng. Aspose.Tasks cho Java cung cấp một giải pháp mạnh mẽ để quản lý các tác vụ cha và con một cách hiệu quả. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình sử dụng Aspose.Tasks cho Java để hợp lý hóa các tác vụ dự án của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Hiểu biết cơ bản về lập trình Java.
-  Aspose.Tasks cho thư viện Java đã được cài đặt. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/java/).
- Môi trường phát triển tích hợp Java (IDE) được thiết lập trên hệ thống của bạn.
## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói cần thiết vào dự án Java của bạn. Các gói này tạo điều kiện tích hợp liền mạch với các chức năng Aspose.Tasks cho Java.
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
Bắt đầu bằng cách đặt ngày bắt đầu dự án và các thông số liên quan khác.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Mã bổ sung để nhập gói có thể được thêm vào đây
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Bước 2: Thêm nhiệm vụ dành cho phụ huynh (Nhiệm vụ 1)
Tạo tác vụ chính có tên "Nhiệm vụ 1" và định cấu hình các thuộc tính của nó.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Bước 3: Thêm Nhiệm vụ chính (Nhiệm vụ 2) với Nhiệm vụ con
Bây giờ, hãy thêm một nhiệm vụ cha khác có tên là "Nhiệm vụ 2" và bao gồm các nhiệm vụ con (Nhiệm vụ 3 và Nhiệm vụ 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Thêm nhiệm vụ con vào Nhiệm vụ 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Cấu hình bổ sung cho Task 3 và Task 4 có thể được thêm vào đây
```
## Bước 4: Định cấu hình nhiệm vụ con
Chỉ định ngày bắt đầu, thời lượng và các ràng buộc cho Nhiệm vụ 3 và Nhiệm vụ 4.
```java
// Cấu hình nhiệm vụ 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Cấu hình nhiệm vụ 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Bước 5: Cập nhật tỷ lệ hoàn thành nhiệm vụ
Điều chỉnh tỷ lệ phần trăm hoàn thành cho Nhiệm vụ 3 và Nhiệm vụ 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Bước 6: Lưu dự án
Cuối cùng, lưu dự án với những thay đổi được áp dụng.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Hướng dẫn từng bước này trình bày cách quản lý các tác vụ cha và con một cách hiệu quả bằng cách sử dụng Aspose.Tasks cho Java. Thử nghiệm với các cấu hình khác nhau để phù hợp với yêu cầu dự án của bạn.
## Phần kết luận
Tóm lại, Aspose.Tasks dành cho Java trao quyền cho các nhà phát triển xử lý hiệu quả các nhiệm vụ của dự án, đảm bảo tổ chức và theo dõi liền mạch. Thực hiện các bước đã nêu để nâng cao khả năng quản lý dự án của bạn.
## Câu hỏi thường gặp
### Aspose.Tasks cho Java có tương thích với các định dạng tệp dự án khác nhau không?
Có, Aspose.Tasks for Java hỗ trợ nhiều định dạng tệp dự án khác nhau, bao gồm MPP và XML.
### Tôi có thể tùy chỉnh các thuộc tính nhiệm vụ ngoài những gì được đề cập trong hướng dẫn này không?
Tuyệt đối! Aspose.Tasks for Java cung cấp các tùy chọn tùy chỉnh mở rộng cho các thuộc tính tác vụ.
### Có diễn đàn cộng đồng nào dành cho Aspose.Tasks để tôi có thể tìm kiếm sự hỗ trợ không?
 Có, bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để hỗ trợ cộng đồng.
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Tasks cho Java?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể tìm tài liệu toàn diện về Aspose.Tasks cho Java ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/tasks/java/).