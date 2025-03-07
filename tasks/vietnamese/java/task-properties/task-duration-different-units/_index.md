---
title: Thời lượng nhiệm vụ trong các đơn vị khác nhau với Aspose.Tasks
linktitle: Thời lượng nhiệm vụ trong các đơn vị khác nhau với Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Khám phá việc quản lý thời gian thực hiện nhiệm vụ trong các dự án Java với Aspose.Tasks. Tính toán và chuyển đổi chính xác thời lượng theo phút, ngày, giờ, tuần và tháng.
weight: 32
url: /vi/java/task-properties/task-duration-different-units/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thời lượng nhiệm vụ trong các đơn vị khác nhau với Aspose.Tasks

## Giới thiệu
Trong lĩnh vực quản lý dự án, việc hiểu và quản lý thời gian thực hiện nhiệm vụ là một khía cạnh quan trọng. Aspose.Tasks for Java cung cấp một bộ công cụ mạnh mẽ để xử lý việc này một cách hiệu quả. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn truy xuất thời lượng nhiệm vụ trong các đơn vị khác nhau bằng Aspose.Tasks.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
- Đã cài đặt Bộ công cụ phát triển Java (JDK)
-  Aspose.Tasks cho thư viện Java. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/java/)
- Hiểu biết cơ bản về lập trình Java
## Gói nhập khẩu
Trong dự án Java của bạn, hãy bao gồm thư viện Aspose.Tasks. Thêm câu lệnh nhập sau vào đầu mã của bạn:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Bước 1: Thiết lập dự án của bạn
Bắt đầu bằng cách tạo một dự án Java mới trong Môi trường phát triển tích hợp (IDE) ưa thích của bạn. Đảm bảo đưa thư viện Aspose.Tasks vào phần phụ thuộc của dự án của bạn.
## Bước 2: Đọc mẫu dự án
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Đọc tệp mẫu MS Project
String fileName = dataDir + "project.xml";
// Đọc tệp đầu vào dưới dạng Dự án
Project project = new Project(fileName);
```
 Đảm bảo thay thế`"Your Document Directory"` với đường dẫn thực tế đến các tệp dự án của bạn.
## Bước 3: Truy xuất một tác vụ
```java
// Nhận một nhiệm vụ để tính toán thời lượng của nó ở các định dạng khác nhau
Task task = project.getRootTask().getChildren().getById(1);
```
 Ở đây, chúng tôi đang nhận được một nhiệm vụ từ dự án. Điều chỉnh`getById(1)` dựa trên ID nhiệm vụ của dự án của bạn.
## Bước 4: Thời lượng tính bằng phút
```java
// Nhận thời lượng tính bằng phút
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
Bước này tính toán thời gian thực hiện nhiệm vụ tính bằng phút.
## Bước 5: Thời lượng tính bằng ngày
```java
// Nhận thời lượng tính bằng Ngày
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
Bước này tính toán thời gian thực hiện nhiệm vụ theo ngày.
## Bước 6: Thời lượng tính bằng giờ
```java
// Nhận thời lượng tính bằng giờ
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
Bước này tính toán thời gian thực hiện nhiệm vụ tính bằng giờ.
## Bước 7: Thời lượng tính bằng tuần
```java
// Nhận thời lượng tính bằng Tuần
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
Bước này tính toán thời gian thực hiện nhiệm vụ theo tuần.
## Bước 8: Thời lượng tính theo tháng
```java
// Nhận thời lượng tính bằng tháng
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
Bước này tính toán thời gian thực hiện nhiệm vụ theo tháng.
## Phần kết luận
Việc quản lý thời lượng nhiệm vụ được thực hiện đơn giản với Aspose.Tasks cho Java. Hướng dẫn này đã hướng dẫn bạn từng bước thực hiện quy trình, cung cấp sự rõ ràng về các đơn vị thời gian khác nhau.
## Các câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho Java với bất kỳ IDE Java nào không?
Có, Aspose.Tasks cho Java tương thích với mọi Môi trường phát triển tích hợp Java (IDE).
### Câu hỏi: Làm cách nào tôi có thể lấy ID của tác vụ trong tệp Microsoft Project?
Bạn có thể kiểm tra tệp dự án hoặc sử dụng API Aspose.Tasks để truy xuất ID tác vụ theo chương trình.
### Câu hỏi: Aspose.Tasks có phù hợp để xử lý các dự án quy mô lớn không?
Tuyệt đối. Aspose.Tasks được thiết kế để xử lý hiệu quả các dự án có quy mô khác nhau.
### Hỏi: Tôi có thể tìm thêm tài liệu ở đâu?
 Tham quan[tài liệu](https://reference.aspose.com/tasks/java/)để có nguồn tài nguyên toàn diện.
### Câu hỏi: Tôi có thể dùng thử Aspose.Tasks cho Java trước khi mua không?
 Có, bạn có thể khám phá một[dùng thử miễn phí](https://releases.aspose.com/) để đánh giá khả năng của nó.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
