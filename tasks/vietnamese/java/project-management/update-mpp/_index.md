---
title: Cập nhật tệp MPP trong Aspose.Tasks
linktitle: Cập nhật tệp MPP trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách cập nhật các tệp MPP một cách liền mạch bằng Aspose.Tasks cho Java. Hãy làm theo hướng dẫn từng bước của chúng tôi để thao tác hiệu quả với tệp dự án.
weight: 19
url: /vi/java/project-management/update-mpp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cập nhật tệp MPP trong Aspose.Tasks

## Giới thiệu
Trong lĩnh vực quản lý dự án, việc xử lý và cập nhật hồ sơ dự án là một nhiệm vụ quan trọng. Aspose.Tasks for Java cung cấp một giải pháp mạnh mẽ cho các nhà phát triển Java để thao tác các tệp Microsoft Project một cách liền mạch. Trong hướng dẫn này, chúng tôi sẽ đi sâu vào việc cập nhật các tệp MPP bằng Aspose.Tasks cho Java.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có những điều sau:
1. Môi trường phát triển Java: Đảm bảo bạn đã cài đặt Java trên hệ thống của mình.
2.  Aspose.Tasks cho Java: Tải xuống và cài đặt Aspose.Tasks cho Java từ[trang tải xuống](https://releases.aspose.com/tasks/java/).
3. Kiến thức cơ bản về Java: Cần phải làm quen với ngôn ngữ lập trình Java để làm theo các ví dụ.

## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết vào dự án Java của mình để sử dụng các chức năng của Aspose.Tasks một cách hiệu quả.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Dòng mã này nhập tất cả các lớp và phương thức thiết yếu từ thư viện Aspose.Tasks, cho phép bạn làm việc với các tệp Microsoft Project một cách dễ dàng.

Bây giờ, hãy chia nhỏ quá trình cập nhật tệp MPP bằng Aspose.Tasks cho Java thành các bước có thể quản lý được.
## Bước 2: Xác định thư mục dữ liệu
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"` với đường dẫn thực tế nơi chứa tệp MPP của bạn.
## Bước 3: Đọc dự án hiện có
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Mã này đọc tệp dự án MPP hiện có có tên`SampleMSP2010.mpp` từ thư mục dữ liệu được chỉ định.
## Bước 4: Tạo một tác vụ mới
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Ở đây, chúng tôi thêm một tác vụ mới có tên "Task1" vào tác vụ gốc của dự án.
## Bước 5: Đặt ngày bắt đầu và ngày kết thúc
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Những dòng mã này đặt ngày bắt đầu và ngày kết thúc cho tác vụ mới được tạo.
## Bước 6: Lưu dự án
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Cuối cùng, bước này lưu dự án đã cập nhật với tác vụ mới được thêm vào tệp MPP mới có tên`AfterLinking.mpp`.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách cập nhật tệp MPP bằng Aspose.Tasks cho Java. Bằng cách làm theo hướng dẫn từng bước, bạn có thể thao tác hiệu quả các tệp Microsoft Project trong ứng dụng Java của mình.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks cho Java có thể xử lý các cấu trúc dự án phức tạp không?
Trả lời: Có, Aspose.Tasks cho Java cung cấp các tính năng mạnh mẽ để xử lý các cấu trúc dự án phức tạp một cách hiệu quả.
### Câu hỏi: Có bản dùng thử miễn phí dành cho Aspose.Tasks dành cho Java không?
 Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ[trang mạng](https://releases.aspose.com/).
### Câu hỏi: Aspose.Tasks cho Java có hỗ trợ các phiên bản khác nhau của tệp Microsoft Project không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks dành cho Java hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.
### Câu hỏi: Tôi có thể nhận giấy phép tạm thời cho Aspose.Tasks cho Java không?
 Đáp: Có, giấy phép tạm thời được cung cấp cho mục đích thử nghiệm. Bạn có thể lấy chúng từ[trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Tôi có thể tìm trợ giúp hoặc hỗ trợ về Aspose.Tasks cho Java ở đâu?
 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) cho bất kỳ sự trợ giúp hoặc thắc mắc.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
