---
title: Tạo liên kết nhiệm vụ liên dự án trong Aspose.Tasks
linktitle: Tạo liên kết nhiệm vụ liên dự án trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tăng cường hợp tác dự án với Aspose.Tasks cho Java. Tìm hiểu cách tạo liên kết nhiệm vụ giữa các dự án từng bước. Tăng hiệu quả ngay bây giờ!
type: docs
weight: 10
url: /vi/java/task-links/create-cross-project-task-link/
---
## Giới thiệu
Trong thế giới năng động của quản lý dự án, hiệu quả và sự hợp tác là điều tối quan trọng. Aspose.Tasks for Java cung cấp một giải pháp mạnh mẽ để nâng cao khả năng quản lý dự án của bạn. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình tạo liên kết nhiệm vụ giữa các dự án bằng Aspose.Tasks cho Java. Hướng dẫn từng bước này sẽ trang bị cho bạn các kỹ năng để liên kết liền mạch các nhiệm vụ giữa các dự án khác nhau, thúc đẩy sự phối hợp được cải thiện và quy trình công việc hợp lý.
## Điều kiện tiên quyết
Trước khi chúng ta bắt tay vào hướng dẫn này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức làm việc về lập trình Java.
-  Aspose.Tasks cho Java đã được cài đặt. Bạn có thể tải nó xuống từ[Trang phát hành Aspose.Tasks cho Java](https://releases.aspose.com/tasks/java/).
- Hiểu biết cơ bản về quản lý dự án và sự phụ thuộc của nhiệm vụ.
## Gói nhập khẩu
Để bắt đầu quá trình, hãy nhập các gói cần thiết vào môi trường Java của bạn. Điều này đảm bảo rằng bạn có quyền truy cập vào các chức năng Aspose.Tasks dành cho Java. Sử dụng đoạn mã sau:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
Bây giờ, hãy chia đoạn mã trên thành các bước dễ hiểu:
## Bước 1: Thiết lập môi trường của bạn
Trước khi đi sâu vào mã, hãy đảm bảo bạn đã cài đặt Java và thư viện Aspose.Tasks for Java được thêm chính xác vào dự án của bạn.
## Bước 2: Tạo một phiên bản dự án
Khởi tạo một dự án mới bằng thư viện Aspose.Tasks:
```java
Project project = new Project();
```
## Bước 3: Thêm nhiệm vụ tóm tắt
Tạo tác vụ tóm tắt để sắp xếp và quản lý các tác vụ được liên kết:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## Bước 4: Thêm tác vụ bên ngoài
Để tạo liên kết tới một nhiệm vụ từ một dự án khác, hãy thêm một nhiệm vụ bên ngoài vào nhiệm vụ tóm tắt:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## Bước 5: Thêm tác vụ cục bộ
Thêm một nhiệm vụ cục bộ vào nhiệm vụ tóm tắt. Đây sẽ là nhiệm vụ được liên kết với nhiệm vụ bên ngoài:
```java
Task t = summary.getChildren().add("Task");
```
## Bước 6: Tạo liên kết nhiệm vụ
Thiết lập liên kết nhiệm vụ giữa nhiệm vụ bên ngoài và nhiệm vụ cục bộ:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## Bước 7: Hiển thị kết quả
Cuối cùng hiển thị kết quả chuyển đổi:
```java
System.out.println("Process completed Successfully");
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách tạo liên kết nhiệm vụ giữa các dự án bằng Aspose.Tasks cho Java. Chức năng này tăng cường sự cộng tác và phối hợp trong quản lý dự án, đảm bảo tích hợp liền mạch giữa các nhiệm vụ trong các dự án khác nhau.
## Câu hỏi thường gặp
### Tôi có thể liên kết các nhiệm vụ từ nhiều dự án bên ngoài trong cùng một nhiệm vụ tóm tắt không?
Có, bạn có thể liên kết các nhiệm vụ từ các dự án bên ngoài khác nhau trong cùng một nhiệm vụ tóm tắt, theo một quy trình tương tự.
### Điều gì xảy ra nếu tác vụ bên ngoài trong dự án được liên kết bị sửa đổi?
Mọi sửa đổi đối với tác vụ bên ngoài sẽ được phản ánh trong tác vụ được liên kết trong dự án hiện tại của bạn.
### Có thể tạo liên kết giữa các tác vụ ở các định dạng tệp khác nhau không?
Có, Aspose.Tasks for Java hỗ trợ liên kết các tác vụ giữa các dự án ở nhiều định dạng tệp khác nhau.
### Tôi có thể hủy liên kết các nhiệm vụ khi chúng được liên kết giữa các dự án không?
Có, bạn có thể hủy liên kết các tác vụ bằng cách xóa liên kết tác vụ bằng các phương pháp Aspose.Tasks thích hợp.
### Có bất kỳ hạn chế nào về số lượng nhiệm vụ có thể được liên kết giữa các dự án không?
Số lượng tác vụ có thể được liên kết tùy thuộc vào khả năng và giới hạn của giấy phép Aspose.Tasks của bạn.