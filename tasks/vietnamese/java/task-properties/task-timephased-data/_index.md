---
title: Dữ liệu theo thời gian của nhiệm vụ trong Aspose.Tasks
linktitle: Dữ liệu theo thời gian của nhiệm vụ trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Khám phá Aspose.Tasks dành cho Java và quản lý dữ liệu theo pha theo thời gian của tác vụ chính. Tải xuống thư viện, tận hưởng bản dùng thử miễn phí và hợp lý hóa việc theo dõi dự án của bạn.
weight: 34
url: /vi/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dữ liệu theo thời gian của nhiệm vụ trong Aspose.Tasks

## Giới thiệu
Trong lĩnh vực quản lý dự án, việc theo dõi chính xác dữ liệu theo thời gian của nhiệm vụ là rất quan trọng để thực hiện dự án hiệu quả. Aspose.Tasks cho Java nổi lên như một công cụ mạnh mẽ để hợp lý hóa quy trình này, cung cấp các tính năng mạnh mẽ và linh hoạt. Hướng dẫn này sẽ hướng dẫn bạn cách sử dụng Aspose.Tasks cho Java để quản lý dữ liệu theo pha thời gian của tác vụ một cách hiệu quả.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Môi trường phát triển Java: Đảm bảo bạn đã cài đặt Java trên hệ thống của mình.
-  Aspose.Tasks for Java Library: Tải xuống và đưa thư viện Aspose.Tasks vào dự án của bạn. Bạn có thể tìm thấy thư viện[đây](https://releases.aspose.com/tasks/java/).
- Thư mục Tài liệu: Thiết lập một thư mục cho các tài liệu dự án của bạn.
## Gói nhập khẩu
Trong dự án Java của bạn, hãy nhập các gói cần thiết cho Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## Bước 1: Đặt ngày bắt đầu dự án
```java
Project project = new Project(dataDir + "project.xml");
// Mã bổ sung để nhập gói
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Giải thích: Khởi tạo một đối tượng lịch, đặt ngày bắt đầu và áp dụng nó cho dự án.
## Bước 2: Xác định nhiệm vụ và tài nguyên
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Giải thích: Tạo một nhiệm vụ và nguồn lực, thiết lập mức lương tiêu chuẩn và làm thêm giờ.
## Bước 3: Đặt thời lượng tác vụ
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Giải thích: Xác định thời hạn của nhiệm vụ (ví dụ: 6 ngày).
## Bước 4: Gán tài nguyên cho tác vụ
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Giải thích: Gán tài nguyên cho nhiệm vụ.
## Bước 5: Cấu hình phân công tài nguyên
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Giải thích: Đặt các tham số như dừng, tiếp tục và đường viền công việc để phân công nguồn lực.
## Bước 6: Đặt đường cơ sở
```java
project.setBaseline(BaselineType.Baseline);
```
Giải thích: Thiết lập đường cơ sở cho dự án.
## Bước 7: Cập nhật hoàn thành nhiệm vụ
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Giải thích: Cho biết tỷ lệ phần trăm hoàn thành của nhiệm vụ.
## Bước 8: Truy xuất dữ liệu theo pha thời gian
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Giải thích: Truy xuất dữ liệu theo pha thời gian cho công việc còn lại được phân công.
## Bước 9: Hiển thị dữ liệu theo pha thời gian
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Mã bổ sung để hiển thị các giá trị khác
```
Giải thích: Xuất và hiển thị dữ liệu theo pha thời gian.
## Phần kết luận
Quản lý hiệu quả dữ liệu theo thời gian của nhiệm vụ là điều không thể thiếu để thành công của dự án. Aspose.Tasks dành cho Java đơn giản hóa quy trình này bằng cách cung cấp một bộ chức năng toàn diện. Bằng cách làm theo hướng dẫn này, bạn có thể tích hợp liền mạch Aspose.Tasks vào dự án Java của mình, đảm bảo kiểm soát chính xác các mốc thời gian của dự án và phân bổ tài nguyên.
## Các câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho Java trong bất kỳ dự án Java nào không?
Trả lời: Có, Aspose.Tasks for Java tương thích với mọi dự án dựa trên Java.
### Câu hỏi: Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Tasks dành cho Java ở đâu?
 Đáp: Hãy ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ và thảo luận.
### Câu hỏi: Có bản dùng thử miễn phí dành cho Aspose.Tasks dành cho Java không?
 Đ: Có, bạn có thể khám phá bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Tasks cho Java?
 A: Bạn có thể có được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Tôi có thể mua Aspose.Tasks cho Java ở đâu?
 Trả lời: Bạn có thể mua Aspose.Tasks cho Java[đây](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
