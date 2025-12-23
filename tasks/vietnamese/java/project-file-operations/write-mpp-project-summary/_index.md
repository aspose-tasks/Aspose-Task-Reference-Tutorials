---
date: 2025-12-23
description: Tìm hiểu cách tạo bản tóm tắt MPP và cập nhật tác giả dự án bằng Aspose.Tasks
  cho Java. Thiết lập và truy xuất thông tin dự án một cách dễ dàng.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách tạo tóm tắt MPP và cập nhật tác giả dự án bằng Aspose.Tasks
url: /vi/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Viết Tóm tắt Dự án MPP trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **tạo thông tin tóm tắt MPP** cho một tệp Microsoft Project và học cách **cập nhật thông tin tác giả dự án** bằng thư viện Aspose.Tasks cho Java. Dù bạn đang xây dựng một công cụ quản lý dự án hay tự động hoá báo cáo, việc điều khiển các thuộc tính tóm tắt một cách lập trình sẽ tiết kiệm thời gian và đảm bảo tính nhất quán trong các dự án của bạn.

## Câu trả lời nhanh
- **“tạo tóm tắt MPP” có nghĩa là gì?** Nó có nghĩa là thiết lập các thuộc tính dự án cấp cao (tác giả, phiên bản, từ khóa, v.v.) xuất hiện trong hộp thoại Project Summary Information của Microsoft Project.  
- **Thư viện nào xử lý việc này?** Aspose.Tasks cho Java cung cấp một API fluent để đọc và ghi các thuộc tính đó.  
- **Tôi có cần giấy phép không?** Có phiên bản dùng thử miễn phí, nhưng giấy phép thương mại là bắt buộc cho việc sử dụng trong môi trường sản xuất.  
- **Tôi có thể thay đổi tác giả sau khi tệp đã được lưu không?** Có – bạn có thể **cập nhật tác giả dự án** bằng cách gọi `project.set(Prj.AUTH, "New Author")` và sau đó lưu lại tệp.  
- **Các định dạng tệp nào được hỗ trợ?** Cả MPP và XML (SaveFileFormat.Xml) đều được hỗ trợ đầy đủ.

## “tạo tóm tắt MPP” là gì?
Việc tạo tóm tắt MPP liên quan đến việc điền các siêu dữ liệu của dự án — tác giả, số phiên bản, từ khóa, nhận xét, ngày tạo và ngày in. Các siêu dữ liệu này được lưu trong bản ghi Project Summary Information và được hiển thị trong phần **File → Info** của Microsoft Project.

## Tại sao cần cập nhật tác giả dự án?
Giữ thông tin **tác giả dự án** chính xác là rất quan trọng cho việc truy vết, hợp tác và báo cáo. Khi có nhiều thành viên trong nhóm đóng góp, bạn có thể cần **cập nhật tác giả dự án** để phản ánh các thay đổi mới nhất hoặc ghi nhận công việc đúng người.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã có các điều kiện sau:
1. Java Development Kit (JDK) đã được cài đặt trên máy tính của bạn.  
2. Aspose.Tasks cho Java – tải về từ [here](https://releases.aspose.com/tasks/java/).  
3. Một IDE như IntelliJ IDEA, Eclipse hoặc NetBeans.

## Nhập khẩu các gói
Đầu tiên, nhập các gói cần thiết vào lớp Java của bạn:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Bước 1: Thiết lập Dự án và Định nghĩa Thông tin Tóm tắt
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
Trong đoạn mã trên, chúng ta **tạo các trường tóm tắt MPP** như tác giả, phiên bản và từ khóa. Bạn cũng có thể **cập nhật tác giả dự án** sau này bằng cách gọi `project.set(Prj.AUTHOR, "New Name")`.

## Bước 2: Lưu Thông tin Tóm tắt Dự án
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Việc lưu dự án sẽ ghi lại tất cả dữ liệu tóm tắt mà bạn vừa định nghĩa.

## Bước 3: Đọc Thông tin Tóm tắt Dự án
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Đoạn mã này minh họa cách **đọc lại** thông tin tóm tắt, xác nhận rằng thao tác **tạo tóm tắt MPP** đã thành công.

## Các vấn đề thường gặp và giải pháp
- **Giá trị null sau khi đọc:** Đảm bảo dự án đã được lưu thành công trước khi tải lại. Kiểm tra đường dẫn tệp và quyền truy cập.  
- **Khác biệt định dạng ngày:** `project.get(Prj.CREATION_DATE)` trả về một `java.util.Date`. Sử dụng `SimpleDateFormat` nếu bạn cần định dạng hiển thị tùy chỉnh.  
- **Chưa đặt giấy phép:** Nếu không có giấy phép hợp lệ, Aspose.Tasks sẽ chạy ở chế độ đánh giá và có thể chèn watermark. Đăng ký giấy phép ngay trong mã của bạn.

## Câu hỏi thường gặp
**H: Tôi có thể dùng Aspose.Tasks cho Java cùng với các thư viện Java khác không?**  
Đ: Có, Aspose.Tasks cho Java có thể tích hợp liền mạch với các thư viện Java khác để nâng cao khả năng quản lý dự án của bạn.

**H: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?**  
Đ: Có, bạn có thể tải phiên bản dùng thử miễn phí từ [here](https://releases.aspose.com/).

**H: Aspose.Tasks cho Java được cập nhật bao lâu một lần?**  
Đ: Aspose.Tasks cho Java được cập nhật thường xuyên để đảm bảo tương thích với các phiên bản mới nhất của Java và các tệp Microsoft Project.

**H: Tôi có thể tùy chỉnh thêm thông tin tóm tắt dự án không?**  
Đ: Chắc chắn, Aspose.Tasks cho Java cung cấp nhiều tùy chọn để tùy chỉnh thông tin tóm tắt dự án theo yêu cầu cụ thể của bạn.

**H: Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?**  
Đ: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Kết luận
Trong hướng dẫn này, chúng tôi đã chỉ cho bạn cách **tạo dữ liệu tóm tắt MPP**, **cập nhật tác giả dự án**, và xác minh các thay đổi đó bằng Aspose.Tasks cho Java. Bằng cách tự động hoá các bước này, bạn sẽ có toàn quyền kiểm soát siêu dữ liệu dự án, làm cho ứng dụng của mình mạnh mẽ hơn và các báo cáo dự án chính xác hơn.

---

**Cập nhật lần cuối:** 2025-12-23  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.10  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}