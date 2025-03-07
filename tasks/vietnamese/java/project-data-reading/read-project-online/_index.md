---
title: Đọc dữ liệu trực tuyến MS Project dễ dàng với Aspose.Tasks
linktitle: Đọc dữ liệu trực tuyến của dự án trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách đọc dữ liệu Microsoft Project Online một cách dễ dàng bằng cách sử dụng Aspose.Tasks cho Java. Nâng cao khả năng quản lý dự án của bạn.
weight: 13
url: /vi/java/project-data-reading/read-project-online/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc dữ liệu trực tuyến MS Project dễ dàng với Aspose.Tasks

## Giới thiệu
Trong lĩnh vực quản lý dự án, việc xử lý dữ liệu Microsoft Project Online một cách hiệu quả là rất quan trọng để hợp lý hóa các hoạt động. Aspose.Tasks for Java cung cấp một giải pháp mạnh mẽ để đọc những dữ liệu đó một cách dễ dàng. Hướng dẫn này đi sâu vào việc tận dụng Aspose.Tasks để truy cập và thao tác dữ liệu MS Project Online một cách liền mạch.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK): Cài đặt JDK để biên dịch và chạy các chương trình Java.
2.  Aspose.Tasks cho Thư viện Java: Tải xuống và đưa thư viện Aspose.Tasks vào dự án Java của bạn. Bạn có thể có được nó từ[đây](https://releases.aspose.com/tasks/java/).
3. Tài khoản Microsoft Project Online: Nhận thông tin xác thực hợp lệ để truy cập dữ liệu MS Project Online.
4. Địa chỉ miền SharePoint: Địa chỉ miền SharePoint nơi chứa dữ liệu MS Project Online của bạn.
5. Tên người dùng và mật khẩu: Thông tin xác thực để xác thực quyền truy cập vào MS Project Online.
## Gói nhập khẩu
Trong dự án Java của bạn, hãy nhập các gói Aspose.Tasks cần thiết để tích hợp liền mạch:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Bước 1: Đặt địa chỉ miền, tên người dùng và mật khẩu SharePoint
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Thay thế`"https://contoso.sharepoint.com"` bằng địa chỉ miền SharePoint của bạn,`"admin@contoso.onmicrosoft.com"` với tên người dùng của bạn và`"MyPassword"` với mật khẩu của bạn.
## Bước 2: Xác thực bằng thông tin xác thực của máy chủ dự án
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Tạo nên`ProjectServerCredentials` đối tượng bằng địa chỉ miền SharePoint, tên người dùng và mật khẩu. Sau đó khởi tạo`ProjectServerManager` với những thông tin xác thực này.
## Bước 3: Truy xuất danh sách dự án và thông tin hiển thị
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Lặp lại thông qua danh sách dự án thu được từ`reader.getProjectList()` và hiển thị chi tiết dự án như tên, ngày tạo và ngày lưu cuối cùng.
## Bước 4: Tải các dự án riêng lẻ và đếm tài nguyên đầu ra
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 Đối với mỗi dự án, hãy tải nó bằng cách sử dụng`reader.getProject(p.getId())` và xuất tên dự án cùng với số lượng tài nguyên liên quan.

## Phần kết luận
Aspose.Tasks dành cho Java đơn giản hóa quá trình đọc dữ liệu MS Project Online, cung cấp cho các nhà phát triển một bộ công cụ mạnh mẽ để hợp lý hóa các tác vụ quản lý dự án. Bằng cách làm theo hướng dẫn này, bạn có thể tích hợp Aspose.Tasks một cách hiệu quả vào các ứng dụng Java của mình để truy cập và thao tác dữ liệu dự án một cách dễ dàng.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho Java để sửa đổi dữ liệu MS Project Online không?
Trả lời: Có, Aspose.Tasks cung cấp các khả năng mở rộng không chỉ để đọc mà còn sửa đổi dữ liệu MS Project Online theo chương trình.
### Câu hỏi: Aspose.Tasks có hỗ trợ các định dạng tệp quản lý dự án khác không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks hỗ trợ nhiều định dạng tệp khác nhau bao gồm MPP, XML, v.v., đảm bảo khả năng tương thích với các hệ thống quản lý dự án đa dạng.
### Câu hỏi: Có bản dùng thử miễn phí dành cho Aspose.Tasks dành cho Java không?
 Đ: Có, bạn có thể tận dụng bản dùng thử miễn phí từ[đây](https://releases.aspose.com/) để khám phá các tính năng và chức năng của Aspose.Tasks.
### Câu hỏi: Tôi có thể tìm tài liệu toàn diện về Aspose.Tasks cho Java ở đâu?
 A: Bạn có thể tham khảo tài liệu chi tiết[đây](https://reference.aspose.com/tasks/java/)để được hướng dẫn toàn diện về cách sử dụng Aspose.Tasks trong các dự án Java của bạn.
### Câu hỏi: Aspose.Tasks for Java có những tùy chọn hỗ trợ nào?
 Trả lời: Nếu gặp bất kỳ vấn đề nào hoặc có thắc mắc, bạn có thể tìm kiếm sự trợ giúp từ diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
