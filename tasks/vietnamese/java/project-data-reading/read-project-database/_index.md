---
date: 2025-12-13
description: Tìm hiểu cách đọc cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho
  Java. Hướng dẫn từng bước với các ví dụ mã và các thực tiễn tốt nhất.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Đọc cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho Java
url: /vi/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá cách **đọc cơ sở dữ liệu Microsoft Project** trực tiếp từ một Microsoft Project Server bằng cách sử dụng Aspose.Tasks Java API. Dù bạn cần tạo báo cáo, di chuyển dữ liệu, hay tích hợp thông tin dự án vào các ứng dụng của riêng mình, tài liệu này sẽ hướng dẫn bạn qua mọi bước — từ thiết lập kết nối cơ sở dữ liệu đến xuất dự án ra XML. Khi hoàn thành, bạn sẽ có một giải pháp sẵn sàng cho môi trường sản xuất, hoạt động mà không cần cài đặt Microsoft Project trên máy chủ.

## Câu trả lời nhanh
- **Aspose.Tasks làm gì?** Nó cung cấp một API thuần Java để đọc, ghi và thao tác các tệp và cơ sở dữ liệu Microsoft Project.  
- **Tôi có cần cài đặt Microsoft Project không?** Không, Aspose.Tasks hoạt động độc lập với Microsoft Project.  
- **Loại cơ sở dữ liệu nào được hỗ trợ?** Microsoft SQL Server (backend của Project Server).  
- **Tôi có thể xuất sang các định dạng khác không?** Có, ngoài XML bạn có thể lưu dưới dạng PDF, HTML, CSV và nhiều hơn nữa.  
- **Các yêu cầu trước chính là gì?** JDK, thư viện Aspose.Tasks cho Java, và driver JDBC cho SQL Server.

## Đọc cơ sở dữ liệu Microsoft Project là gì?
Đọc một cơ sở dữ liệu Microsoft Project có nghĩa là kết nối tới kho lưu trữ SQL Server của Project Server, trích xuất dữ liệu dự án đã lưu và nạp chúng vào một đối tượng `Project` mà Aspose.Tasks có thể thao tác. Cách tiếp cận này lý tưởng cho việc báo cáo tự động, di chuyển dữ liệu hoặc phân tích tùy chỉnh.

## Tại sao nên dùng Aspose.Tasks cho Java?
- **Không phụ thuộc vào Microsoft Project** – chạy trên bất kỳ máy chủ hoặc môi trường CI nào.  
- **Mô hình đối tượng phong phú** – truy cập các nhiệm vụ, nguồn lực, phân công, lịch và trường tùy chỉnh bằng chương trình.  
- **Nhiều tùy chọn xuất** – XML, PDF, HTML, PNG, v chỉ với một lời gọi API.  
- **Hiệu năng cao** – tối ưu cho các dự án doanh nghiệp lớn.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. Môi trường phát triển Java hoạt động (JDK 8 hoặc mới hơn).  
2. Thư viện Aspose.Tasks cho Java đã được thêm vào classpath của dự án.  
3. Thông tin đăng nhập truy cập cơ sở dữ liệu SQL của Project Server (tên máy chủ, cổng, tên cơ sở dữ liệu, tên người dùng, mật khẩu).  
4. Driver JDBC của Microsoft cho SQL Server (ví dụ, `sqljdbc4.jar`).  

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

## Bước 1: Thiết lập kết nối cơ sở dữ liệu
Tạo một thể hiện `MspDbSettings` chứa chuỗi kết nối JDBC. Thay thế các giá trị placeholder bằng chi tiết máy chủ thực tế của bạn.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Mẹo chuyên nghiệp:** Lưu chuỗi kết nối trong một tệp cấu hình bảo mật hoặc biến môi trường thay vì mã hoá cứng thông tin đăng nhập.

## Bước 2: Thêm driver JDBC
Tải driver JDBC của Microsoft SQL Server tại thời gian chạy để JVM có thể giao tiếp với cơ sở dữ liệu.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Cảnh báo:** Đảm bảo phiên bản driver phù hợp với phiên bản SQL Server của bạn. Sử dụng driver không tương thích có thể gây lỗi kết nối.

## Bước 3: Đọc dữ liệu dự án
Khởi tạo một đối tượng `Project` bằng cách truyền `MspDbSettings`. Aspose.Tasks sẽ tự động lấy dữ liệu dự án từ cơ sở dữ liệu.

```java
Project project = new Project(settings);
```

Tại thời điểm này, bạn có thể khám phá đối tượng `project` — liệt kê các nhiệm vụ, nguồn lực, hoặc sửa đổi các trường theo nhu cầu.

## Bước 4: Lưu dữ liệu dự án
Xuất dự án đã nạp ra định dạng tệp mà bạn chọn. Ví dụ dưới đây lưu dự án dưới dạng XML, sau này có thể nhập lại vào Microsoft Project hoặc xử lý tiếp.

```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

Bạn có thể thay `SaveFileFormat.Xml` bằng `Pdf`, `Html`, `Csv`, v.v., tùy theo nhu cầu báo cáo của mình.

## Các vấn đề thường gặp & Giải pháp
| Vấn đề | Nguyên nhân thường gặp | Giải pháp |
|-------|------------------------|----------|
| **Connection timeout** | Sai địa chỉ máy chủ/cổng hoặc tường lửa chặn | Xác minh địa chỉ máy chủ, mở cổng 1433, và kiểm tra kết nối bằng một chương trình JDBC đơn giản. |
| **Authentication error** | Tên người dùng/mật khẩu không hợp lệ hoặc SQL Server chưa cấu hình cho xác thực SQL | Sử dụng tài khoản SQL hợp lệ hoặc bật xác thực mixed‑mode trên máy chủ. |
| **Driver** | Tệp JDBC jar không có trong classpath | Đảm bảo `addJDBCDriver` trỏ tới tệp `.jar` đúng và đường dẫn sử dụng dấu gạch chéo ngược kép (`\\`). |
| **Empty project after load** | Quyền hạn không đủ để đọc các bảng của Project Server | Cấp cho tài khoản đăng nhập quyền SELECT trên schema của cơ sở dữ liệu Project Server. |

## Câu hỏi thường gặp

**Q: Aspose.Tasks có thể được dùng để đọc dữ liệu dự án từ các cơ sở dữ liệu khác ngoài Microsoft Project không?**  
A: Có, Aspose.Tasks hỗ trợ đọc dữ liệu dự án từ nhiều nguồn, bao gồm tệp XML, Primavera và các cơ sở dữ liệu Microsoft Project.

**Q: Aspose.Tasks có tương thích với các phiên bản khác nhau của Microsoft Project không?**  
A: Có, Aspose.Tasks được thiết kế để làm việc với nhiều phiên bản Microsoft Project, đảm bảo tích hợp liền mạch.

**Q: Tôi có thể thao tác dữ liệu dự án trước khi lưu không?**  
A: Chắc chắn, Aspose.Tasks cung cấp một API phong phú để thêm nhiệm vụ, cập nhật nguồn lực và thiết lập thuộc tính dự án trước khi xuất.

**Q: Aspose.Tasks có hỗ trợ nhiều định dạng đầu ra không?**  
A: Có, bạn có thể lưu dự án dưới dạng XML, PDF, HTML, CSV, PNG, JPEG và nhiều định dạng khác.

**Q: Tôi có thể tìm hỗ trợ hoặc trợ giúp thêm về Aspose.Tasks ở đâu?**  
A: Để được hỗ trợ thêm, hãy truy cập diễn đàn Aspose.Tasks hoặc khám phá tài liệu trên trang web [here](https://forum.aspose.com/c/tasks/15).

## Kết luận
Bằng cách làm theo hướng dẫn chi tiết này, bạn đã biết cách **đọc cơ sở dữ liệu Microsoft Project** bằng Aspose.Tasks cho Java, thao tác dữ liệu một cách lập trình và xuất ra định dạng bạn cần. Cách tiếp cận này loại bỏ phụ thuộc vào Microsoft Project, tối ưu hoá quy trình báo cáo tự động và mở ra cơ hội tích hợp tùy chỉnh mạnh mẽ.

---

**Cập nhật lần cuối:** 2025-12-13  
**Kiểm tra với:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Tác giả:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
