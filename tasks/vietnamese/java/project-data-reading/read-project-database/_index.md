---
date: 2026-10-31
description: Tìm hiểu cách lưu dự án dưới dạng PDF và đọc cơ sở dữ liệu Microsoft
  Project bằng Aspose.Tasks for Java, cùng với việc kết nối tới Project Server, chuyển
  đổi dự án sang HTML và xuất dự án ra XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Đọc dữ liệu dự án từ cơ sở dữ liệu Microsoft Project trong Aspose.Tasks
og_description: Lưu dự án dưới dạng PDF và đọc cơ sở dữ liệu Microsoft Project bằng
  Aspose.Tasks for Java. Tìm hiểu cách kết nối tới Project Server, xuất ra HTML, XML
  và CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Lưu dự án dưới dạng PDF và đọc cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks
  for Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Lưu dự án dưới dạng PDF và đọc cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks
  for Java
url: /vi/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu dự án dưới dạng PDF và đọc cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho Java

## Giới thiệu
Trong tutorial này, bạn sẽ khám phá cách **đọc cơ sở dữ liệu Microsoft Project** trực tiếp từ Microsoft Project Server và sau đó **lưu dự án dưới dạng PDF** bằng API Aspose.Tasks Java. Cho dù bạn cần tạo báo cáo có thể in, di chuyển dữ liệu cũ, hoặc nhúng thông tin dự án vào cổng thông tin tùy chỉnh, hướng dẫn này sẽ dẫn bạn qua mọi bước—từ cấu hình kết nối JDBC đến xuất dự án ra PDF, XML hoặc HTML. Khi hoàn thành, bạn sẽ có một giải pháp sẵn sàng cho môi trường production chạy trên bất kỳ máy chủ Java nào mà không cần cài đặt Microsoft Project.

## Câu trả lời nhanh
- **What does Aspose.Tasks do?** Nó cung cấp một API thuần Java để đọc, ghi và thao tác các tệp và cơ sở dữ liệu Microsoft Project.  
- **Do I need Microsoft Project installed?** Không, Aspose.Tasks hoạt động độc lập với Microsoft Project.  
- **Which database type is supported?** Microsoft SQL Server, backend của Project Server.  
- **Can I export to other formats?** Có — PDF, XML, HTML, CSV, PNG, JPEG và hơn nữa.  
- **What are the main prerequisites?** JDK 8 hoặc mới hơn, thư viện Aspose.Tasks cho Java, driver JDBC cho SQL Server, và thông tin đăng nhập hợp lệ cho Project Server.

## “Đọc cơ sở dữ liệu Microsoft Project” là gì?
Đọc một cơ sở dữ liệu Microsoft Project có nghĩa là kết nối tới kho lưu trữ SQL Server của Project Server, trích xuất dữ liệu dự án đã lưu và tải nó vào một đối tượng `Project` mà Aspose.Tasks có thể thao tác. Cách tiếp cận này lý tưởng cho báo cáo tự động, di chuyển dữ liệu hoặc phân tích tùy chỉnh.

## Tại sao nên sử dụng Aspose.Tasks cho Java?
Aspose.Tasks cho Java cho phép bạn làm việc với dữ liệu Microsoft Project mà không cần ứng dụng desktop, cung cấp một giải pháp thuần Java chạy trên bất kỳ nền tảng nào. Nó cung cấp một mô hình đối tượng toàn diện cho các tác vụ, nguồn lực, lịch và trường tùy chỉnh, và có thể xử lý các dự án doanh nghiệp lớn một cách hiệu quả, làm cho nó trở thành lựa chọn lý tưởng cho báo cáo tự động, di chuyển và các kịch bản tích hợp.

- **No Microsoft Project dependency** – chạy trên bất kỳ máy chủ hoặc môi trường CI nào.  
- **Rich object model** – truy cập các tác vụ, nguồn lực, phân công, lịch và trường tùy chỉnh thông qua lập trình.  
- **Multiple export options** – Aspose.Tasks hỗ trợ xuất ra **hơn 20 định dạng tệp**, bao gồm PDF, XML, HTML, CSV, PNG và JPEG, chỉ với một lời gọi API.  
- **High performance** – thư viện có thể xử lý các dự án chứa **tối đa 10.000 tác vụ** trong vòng chưa đầy một phút, và nó truyền dữ liệu để tránh tải toàn bộ tệp vào bộ nhớ.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. Môi trường phát triển Java hoạt động (JDK 8 hoặc mới hơn).  
2. Thư viện Aspose.Tasks cho Java đã được thêm vào classpath của dự án.  
3. Thông tin đăng nhập để truy cập cơ sở dữ liệu SQL của Project Server (tên máy chủ, cổng, tên cơ sở dữ liệu, tên người dùng, mật khẩu) để kết nối tới Project Server.  
4. Microsoft JDBC Driver cho SQL Server (ví dụ: `sqljdbc4.jar`).  

## Nhập các gói
Đầu tiên, nhập các lớp bạn sẽ cần. Danh sách bao gồm các lớp cốt lõi của Aspose.Tasks và các tiện ích chuẩn của Java.

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

## Cách kết nối tới Project Server
Thiết lập một kết nối đáng tin cậy là nền tảng để đọc dữ liệu dự án. Đảm bảo rằng instance SQL Server có thể truy cập được từ máy chủ Java của bạn và tài khoản đăng nhập bạn sử dụng có quyền **SELECT** trên schema của Project Server. Bạn cũng nên kiểm tra độ trễ mạng và cấu hình bất kỳ cài đặt SSL nào cần thiết để đảm bảo giao tiếp an toàn.

## Bước 1: thiết lập kết nối cơ sở dữ liệu
Lớp `MspDbSettings` đóng gói các chi tiết kết nối JDBC cần thiết để truy cập cơ sở dữ liệu Microsoft Project Server. Tạo một thể hiện `MspDbSettings` chứa chuỗi kết nối JDBC. Thay thế các giá trị placeholder bằng chi tiết máy chủ thực tế của bạn.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Lưu chuỗi kết nối trong một tệp cấu hình bảo mật hoặc biến môi trường thay vì mã cứng thông tin đăng nhập.

## Bước 2: thêm driver JDBC
Tải driver JDBC của Microsoft SQL Server tại thời gian chạy để JVM có thể giao tiếp với cơ sở dữ liệu.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Đảm bảo phiên bản driver phù hợp với phiên bản SQL Server của bạn. Sử dụng driver không tương thích có thể gây lỗi kết nối.

## Bước 3: đọc dữ liệu dự án
Lớp `Project` đại diện cho một tệp Microsoft Project được tải vào bộ nhớ, cung cấp các tác vụ, nguồn lực và phân công. Khởi tạo một đối tượng `Project` bằng cách truyền `MspDbSettings`. Aspose.Tasks sẽ tự động lấy dữ liệu dự án từ cơ sở dữ liệu.

```java
Project project = new Project(settings);
```

Tại thời điểm này bạn có thể khám phá đối tượng `project`—liệt kê các tác vụ, nguồn lực, hoặc sửa đổi các trường theo nhu cầu.

## Bước 4: lưu dự án dưới dạng PDF
Enum `SaveFileFormat` xác định định dạng đầu ra cho phương thức `Project.save`, chẳng hạn PDF, XML hoặc HTML. Xuất dự án đã tải ra định dạng bạn chọn. Ví dụ dưới đây lưu dự án dưới dạng **PDF**, rất phù hợp cho các báo cáo có thể in. Bạn cũng có thể **xuất dự án ra XML** hoặc **chuyển đổi dự án sang HTML** bằng cách thay đổi enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Nếu bạn muốn XML, chỉ cần thay `SaveFileFormat.Pdf` bằng `SaveFileFormat.Xml`. Đối với đầu ra HTML, sử dụng `SaveFileFormat.Html`.

## Các vấn đề thường gặp & giải pháp
| Issue | Typical cause | Fix |
|-------|---------------|-----|
| **Connection timeout** | Sai địa chỉ máy chủ/cổng hoặc tường lửa chặn | Xác minh địa chỉ máy chủ, mở cổng 1433 và kiểm tra kết nối bằng một chương trình kiểm tra JDBC đơn giản. |
| **Authentication error** | Tên người dùng/mật khẩu không hợp lệ hoặc SQL Server chưa được cấu hình cho xác thực SQL | Sử dụng tài khoản SQL hợp lệ hoặc bật xác thực hỗn hợp trên máy chủ. |
| **Driver not found** | JAR JDBC không có trong classpath | Đảm bảo `addJDBCDriver` trỏ tới tệp `.jar` đúng và đường dẫn sử dụng dấu gạch chéo ngược đôi (`\\`). |
| **Empty project after load** | Quyền không đủ để đọc các bảng Project Server | Cấp quyền SELECT cho tài khoản đăng nhập trên schema của cơ sở dữ liệu Project Server. |

## Câu hỏi thường gặp

**Q: Aspose.Tasks có thể được sử dụng để đọc dữ liệu dự án từ các cơ sở dữ liệu khác ngoài Microsoft Project không?**  
A: Có, Aspose.Tasks hỗ trợ đọc dữ liệu dự án từ các tệp XML, cơ sở dữ liệu Primavera và các định dạng dự án tiêu chuẩn khác.

**Q: Aspose.Tasks có tương thích với các phiên bản khác nhau của Microsoft Project không?**  
A: Có, thư viện hoạt động với Microsoft Project 2007 đến các phiên bản mới nhất 2024, đảm bảo tích hợp liền mạch trên mọi phiên bản.

**Q: Tôi có thể thao tác dữ liệu dự án trước khi lưu không?**  
A: Chắc chắn, bạn có thể thêm, cập nhật hoặc xóa các tác vụ, nguồn lực và trường tùy chỉnh bằng API phong phú trước khi xuất.

**Q: Aspose.Tasks có hỗ trợ nhiều định dạng đầu ra không?**  
A: Có, bạn có thể lưu dự án dưới dạng PDF, XML, HTML, CSV, PNG, JPEG và hơn nữa — tổng cộng hơn 20 định dạng.

**Q: Tôi có thể tìm hỗ trợ hoặc trợ giúp thêm về Aspose.Tasks ở đâu?**  
A: Để được hỗ trợ thêm, hãy truy cập diễn đàn Aspose.Tasks hoặc khám phá tài liệu trên trang web [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Kết luận
Bằng cách làm theo hướng dẫn từng bước này, bạn đã biết cách **đọc cơ sở dữ liệu Microsoft Project**, **lưu dự án dưới dạng PDF**, và xuất ra các định dạng khác bằng Aspose.Tasks cho Java. Cách tiếp cận này loại bỏ phụ thuộc vào Microsoft Project, tối ưu hoá báo cáo tự động và mở ra cánh cửa cho các tích hợp tùy chỉnh mạnh mẽ.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose

## Hướng dẫn liên quan

- [Cách lưu dự án dưới dạng PDF với Aspose.Tasks – Hướng dẫn xuất](/tasks/java/project-file-operations/save-as-pdf/)
- [Lưu dự án dưới dạng PDF – Render Task Sheet với Aspose.Tasks cho Java](/tasks/java/task-properties/render-task-sheet/)
- [Xuất dự án ra PDF và giảm khoảng cách giữa danh sách tác vụ và chân trang trong Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}