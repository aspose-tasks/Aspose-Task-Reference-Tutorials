---
title: Đọc dữ liệu dự án từ cơ sở dữ liệu dự án MS trong Aspose.Tasks
linktitle: Đọc dữ liệu dự án từ cơ sở dữ liệu dự án Microsoft trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách đọc dữ liệu dự án từ Cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho Java. Hướng dẫn từng bước với các ví dụ về mã.
weight: 12
url: /vi/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc dữ liệu dự án từ cơ sở dữ liệu dự án MS trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách đọc dữ liệu dự án từ Cơ sở dữ liệu dự án Microsoft bằng Aspose.Tasks cho Java. Aspose.Tasks là một API Java mạnh mẽ cho phép các nhà phát triển thao tác với các tài liệu Microsoft Project mà không cần cài đặt Microsoft Project. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn sẽ tìm hiểu cách trích xuất dữ liệu dự án từ cơ sở dữ liệu một cách hiệu quả và lưu nó ở định dạng mong muốn.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Kiến thức cơ bản về lập trình Java.
2. Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
3. Thư viện Aspose.Tasks dành cho Java được tải xuống và định cấu hình trong dự án của bạn.

## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói cần thiết:
```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```
## Bước 1: Thiết lập kết nối cơ sở dữ liệu
Trước tiên, bạn cần thiết lập kết nối tới Cơ sở dữ liệu Microsoft Project. Điều này bao gồm việc chỉ định URL cơ sở dữ liệu, tên máy chủ, số cổng, tên cơ sở dữ liệu, tên người dùng và mật khẩu.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Bước 2: Thêm trình điều khiển JDBC
Tiếp theo, bạn cần thêm trình điều khiển JDBC vào dự án của mình. Trình điều khiển này tạo điều kiện giao tiếp giữa các ứng dụng Java và cơ sở dữ liệu Microsoft SQL Server.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Bước 3: Đọc dữ liệu dự án
 Bây giờ, hãy tạo một`Project` đối tượng và tải dữ liệu dự án từ cơ sở dữ liệu bằng cách sử dụng các cài đặt đã xác định trước đó.
```java
Project project = new Project(settings);
```
## Bước 4: Lưu dữ liệu dự án
Cuối cùng, lưu dữ liệu dự án sang định dạng mong muốn. Trong ví dụ này, chúng tôi lưu nó dưới dạng tệp XML.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Chúc mừng! Bạn đã đọc thành công dữ liệu dự án từ Cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho Java.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã đề cập đến quá trình đọc dữ liệu dự án từ Cơ sở dữ liệu Microsoft Project bằng cách sử dụng Aspose.Tasks cho Java. Bằng cách làm theo các bước đã nêu, bạn có thể trích xuất thông tin dự án một cách liền mạch và thao tác thông tin đó theo yêu cầu của mình. Aspose.Tasks đơn giản hóa việc xử lý tài liệu Microsoft Project, cho phép trích xuất và thao tác dữ liệu hiệu quả.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có thể được sử dụng để đọc dữ liệu dự án từ các cơ sở dữ liệu khác ngoài Microsoft Project không?
Trả lời: Có, Aspose.Tasks hỗ trợ đọc dữ liệu dự án từ nhiều nguồn khác nhau, bao gồm các tệp XML, cơ sở dữ liệu Primavera và Microsoft Project.
### Câu hỏi: Aspose.Tasks có tương thích với các phiên bản khác nhau của Microsoft Project không?
Trả lời: Có, Aspose.Tasks được thiết kế để hoạt động với các phiên bản khác nhau của Microsoft Project, đảm bảo khả năng tương thích và tích hợp liền mạch.
### Câu hỏi: Tôi có thể thao tác dữ liệu dự án trước khi lưu không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks cung cấp nhiều tính năng để thao tác dữ liệu dự án, chẳng hạn như thêm nhiệm vụ, cập nhật tài nguyên và đặt thuộc tính dự án.
### Câu hỏi: Aspose.Tasks có hỗ trợ nhiều định dạng đầu ra không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều định dạng đầu ra khác nhau, bao gồm XML, PDF, HTML và các định dạng hình ảnh như PNG và JPEG.
### Câu hỏi: Tôi có thể tìm thêm hỗ trợ hoặc trợ giúp với Aspose.Tasks ở đâu?
 Trả lời: Để được hỗ trợ hoặc trợ giúp thêm, bạn có thể truy cập diễn đàn Aspose.Tasks hoặc khám phá tài liệu có sẵn trên trang web[đây](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
