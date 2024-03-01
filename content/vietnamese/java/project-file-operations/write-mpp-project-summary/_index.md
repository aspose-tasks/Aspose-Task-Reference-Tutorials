---
title: Viết tóm tắt dự án MPP trong Aspose.Tasks
linktitle: Viết tóm tắt dự án MPP trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách viết tóm tắt dự án MPP bằng Java bằng Aspose.Tasks. Thiết lập và truy xuất thông tin dự án một cách dễ dàng.
type: docs
weight: 27
url: /vi/java/project-file-operations/write-mpp-project-summary/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng Aspose.Tasks cho Java để viết tóm tắt dự án MPP. Aspose.Tasks là một thư viện Java mạnh mẽ để làm việc với các tệp Microsoft Project. Bằng cách làm theo các bước được nêu bên dưới, bạn sẽ có thể thiết lập và truy xuất các thông tin tóm tắt khác nhau về một dự án bằng thư viện này.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Tasks cho Java: Tải xuống và cài đặt thư viện Aspose.Tasks cho Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).
3. Môi trường phát triển tích hợp (IDE): Chọn IDE ưa thích của bạn để phát triển Java, chẳng hạn như IntelliJ IDEA, Eclipse hoặc NetBeans.

## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết vào lớp Java của bạn:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Bước 1: Thiết lập dự án và xác định thông tin tóm tắt
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Data Directory";
//Khởi tạo một đối tượng Project mới với đường dẫn đến tệp dự án của bạn
Project project = new Project(dataDir + "project.mpp");
// Đặt thông tin tóm tắt về dự án
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Đặt ngày tạo dự án
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Đặt từ khóa cho dự án
project.set(Prj.KEYWORDS, "MPP Aspose");
// Đặt ngày in cuối cùng của dự án
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Bước 2: Lưu thông tin tóm tắt dự án
```java
// Lưu dự án trở lại định dạng MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Hiển thị thông báo thành công
System.out.println("Process completed Successfully");
```
## Bước 3: Đọc thông tin tóm tắt dự án
```java
// Đọc thông tin tóm tắt dự án
project = new Project(dataDir + "MppAspose.xml");
// In tác giả của dự án
System.out.println("Author: " + project.get(Prj.AUTHOR));
// In tác giả cuối cùng của dự án
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// In số sửa đổi của dự án
System.out.println("Revision: " + project.get(Prj.REVISION));
// In từ khóa của dự án
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// In ý kiến của dự án
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// In ngày tạo dự án
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// In từ khóa của dự án (lại)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// In ngày in cuối cùng của dự án
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày cách viết tóm tắt dự án MPP bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn có thể thiết lập và truy xuất các thông tin tóm tắt khác nhau về các tệp dự án của mình một cách hiệu quả. Aspose.Tasks đơn giản hóa quá trình làm việc với các tệp Microsoft Project trong các ứng dụng Java, cung cấp chức năng mạnh mẽ và dễ sử dụng.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho Java với các thư viện Java khác không?
Trả lời: Có, Aspose.Tasks cho Java có thể được tích hợp liền mạch với các thư viện Java khác để nâng cao khả năng quản lý dự án của bạn.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
 Đ: Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Câu hỏi: Aspose.Tasks cho Java được cập nhật thường xuyên như thế nào?
Trả lời: Aspose.Tasks cho Java được cập nhật thường xuyên để đảm bảo khả năng tương thích với các phiên bản mới nhất của tệp Java và Microsoft Project.
### Câu hỏi: Tôi có thể tùy chỉnh thêm thông tin tóm tắt dự án không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks cho Java cung cấp các tùy chọn mở rộng để tùy chỉnh thông tin tóm tắt dự án theo yêu cầu cụ thể của bạn.
### Câu hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?
Trả lời: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).