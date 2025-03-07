---
title: Tỷ lệ phần trăm tính toán hoàn thành cho các nhiệm vụ trong Aspose.Tasks
linktitle: Tỷ lệ phần trăm tính toán hoàn thành cho các nhiệm vụ trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Khám phá Aspose.Tasks dành cho Java và hợp lý hóa việc theo dõi tiến độ dự án. Dễ dàng tính toán tỷ lệ phần trăm nhiệm vụ để quản lý dự án hiệu quả.
weight: 25
url: /vi/java/task-properties/percentage-complete-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tỷ lệ phần trăm tính toán hoàn thành cho các nhiệm vụ trong Aspose.Tasks

## Giới thiệu
Chào mừng bạn đến với hướng dẫn chuyên sâu của chúng tôi về cách tính toán phần trăm nhiệm vụ thành thạo bằng Aspose.Tasks cho Java. Aspose.Tasks là một thư viện Java mạnh mẽ được thiết kế để làm việc với các tệp Microsoft Project, cung cấp một bộ tính năng mạnh mẽ để quản lý dự án. Trong hướng dẫn này, chúng tôi sẽ tập trung vào tính toán Tỷ lệ phần trăm hoàn thành, cung cấp cho bạn kiến thức để theo dõi và phân tích tiến độ dự án một cách hiệu quả.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Môi trường phát triển Java: Đảm bảo bạn đã cài đặt Java trên hệ thống của mình.
-  Thư viện Aspose.Tasks: Tải xuống thư viện Aspose.Tasks cho Java từ[liên kết này](https://releases.aspose.com/tasks/java/).
## Gói nhập khẩu
Hãy bắt đầu bằng cách nhập các gói cần thiết cho dự án Aspose.Tasks for Java của bạn. Bao gồm đoạn mã sau vào dự án của bạn:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Bây giờ, hãy chia nhỏ từng bước với lời giải thích chi tiết.
## Bước 1: Nhập gói
Ở bước đầu tiên, chúng tôi nhập các gói cần thiết để thiết lập dự án Aspose.Tasks của mình.
## Bước 2: Thiết lập thư mục tài liệu
 Xác định đường dẫn đến thư mục tài liệu của bạn bằng cách sử dụng`dataDir`Biến đổi. Đảm bảo tệp Microsoft Project của bạn, như "Software Development.mpp," nằm trong thư mục này.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
```
## Bước 3: Tải dự án
 Khởi tạo một cái mới`Project` object và tải tệp Microsoft Project của bạn vào phiên bản dự án.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## Bước 4: Truy xuất bộ sưu tập tác vụ
 Nhận tác vụ gốc của dự án và truy xuất các phần tử con của nó dưới dạng bộ sưu tập bằng cách sử dụng`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## Bước 5: Hoàn thành phần trăm in
Lặp lại từng nhiệm vụ trong bộ sưu tập và in Phần trăm hoàn thành, Phần trăm hoàn thành công việc và Phần trăm hoàn thành vật lý.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Lặp lại các bước này cho từng nhiệm vụ trong dự án của bạn để hiểu rõ hơn về tiến độ của từng nhiệm vụ.
## Phần kết luận
Chúc mừng! Bạn đã thành thạo cách tính tỷ lệ phần trăm nhiệm vụ bằng cách sử dụng Aspose.Tasks cho Java. Thư viện mạnh mẽ này trao quyền cho các nhà phát triển quản lý và phân tích tiến độ dự án một cách hiệu quả.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tìm tài liệu Aspose.Tasks ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/tasks/java/).
### Câu hỏi: Làm cách nào tôi có thể tải xuống thư viện Aspose.Tasks cho Java?
 Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/java/).
### Hỏi: Có bản dùng thử miễn phí không?
Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?
 Truy cập diễn đàn hỗ trợ[đây](https://forum.aspose.com/c/tasks/15).
### Hỏi: Làm cách nào để có được giấy phép tạm thời?
 Bạn có thể có được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
