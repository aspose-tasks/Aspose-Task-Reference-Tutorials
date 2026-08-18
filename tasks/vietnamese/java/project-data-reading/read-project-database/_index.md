---
date: 2026-02-18
description: Học cách lưu dự án dưới dạng PDF và đọc cơ sở dữ liệu Microsoft Project
  bằng Aspose.Tasks cho Java, cùng với việc kết nối tới Project Server, chuyển đổi
  dự án sang HTML và xuất dự án ra XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lưu dự án dưới dạng PDF và đọc cơ sở dữ liệu dự án bằng Aspose.Tasks cho Java
url: /vi/java/project-data-reading/read-project-database/
weight: 12
---

 careful with bullet points.

Also note "step‑by‑step" keep hyphen.

Now produce final.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu dự án dưới dạng PDF và đọc cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá cách **đọc cơ sở dữ liệu Microsoft Project** trực tiếp từ Microsoft Project Server và sau đó **lưu dự án dưới dạng PDF** bằng API Aspose.Tasks cho Java. Cho dù bạn cần tạo báo cáo, di chuyển dữ liệu, hay tích hợp thông tin dự án vào ứng dụng của mình, hướng dẫn này sẽ dẫn bạn qua từng bước — từ thiết lập kết nối cơ sở dữ liệu đến xuất dự án ra PDF, XML hoặc HTML. Khi hoàn thành, bạn sẽ có một giải pháp sẵn sàng cho môi trường sản xuất, hoạt động mà không cần cài đặt Microsoft Project trên máy chủ.

## Câu trả lời nhanh
- **Aspose.Tasks làm gì?** Nó cung cấp một API thuần Java để đọc, ghi và thao tác các tệp và cơ sở dữ liệu Microsoft Project.  
- **Có cần cài đặt Microsoft Project không?** Không, Aspose.Tasks hoạt động độc lập với Microsoft Project.  
- **Loại cơ sở dữ liệu nào được hỗ trợ?** Microsoft SQL Server (backend của Project Server).  
- **Có thể xuất sang các định dạng khác không?** Có, ngoài PDF bạn còn có thể lưu dưới dạng XML, HTML, CSV và nhiều định dạng khác.  
- **Các yêu cầu chính là gì?** JDK, thư viện Aspose.Tasks cho Java, driver JDBC SQL Server, và thông tin **kết nối tới Project Server**.

## “Đọc cơ sở dữ liệu Microsoft Project” là gì?
Đọc một cơ sở dữ liệu Microsoft Project có nghĩa là kết nối tới kho lưu trữ SQL Server của Project Server, trích xuất dữ liệu dự án đã lưu và tải chúng vào một đối tượng `Project` mà Aspose.Tasks có thể thao tác. Cách tiếp cận này lý tưởng cho việc báo cáo tự động, di chuyển dữ liệu hoặc phân tích tùy chỉnh.

## Tại sao nên dùng Aspose.Tasks cho Java?
- **Không phụ thuộc vào Microsoft Project** – chạy trên bất kỳ máy chủ hay môi trường CI nào.  
- **Mô hình đối tượng phong phú** – truy cập các task, resource, assignment, calendar và custom field một cách lập trình.  
- **Nhiều tùy chọn xuất** – PDF, XML, HTML, PNG, v.v., chỉ với một lời gọi API.  
- **Hiệu năng cao** – tối ưu cho các dự án doanh nghiệp lớn.

## Các yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. Môi trường phát triển Java hoạt động (JDK 8 hoặc mới hơn).  
2. Thư viện Aspose.Tasks cho Java đã được thêm vào classpath của dự án.  
3. Thông tin đăng nhập để truy cập cơ sở dữ liệu SQL của Project Server (tên máy chủ, cổng, tên cơ sở dữ liệu, tên người dùng, mật khẩu) **để kết nối tới Project Server**.  
4. Driver JDBC Microsoft cho SQL Server (ví dụ: `sqljdbc4.jar`).  

## Nhập khẩu các gói
Đầu tiên, nhập các lớp cần thiết. Danh sách bao gồm các lớp core của Aspose.Tasks và các tiện ích chuẩn của Java.

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
Thiết lập một kết nối ổn định là nền tảng để đọc dữ liệu dự án. Đảm bảo rằng instance SQL Server có thể truy cập được từ máy Java của bạn và tài khoản đăng nhập bạn dùng có quyền **SELECT** trên schema của Project Server.

## Bước 1: Thiết lập kết nối cơ sở dữ liệu
Tạo một thể hiện `MspDbSettings` chứa chuỗi kết nối JDBC. Thay các giá trị placeholder bằng thông tin thực tế của máy chủ của bạn.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Mẹo:** Lưu chuỗi kết nối trong một tệp cấu hình bảo mật hoặc biến môi trường thay vì mã cứng thông tin đăng nhập.

## Bước 2: Thêm driver JDBC
Tải driver JDBC Microsoft SQL Server tại thời gian chạy để JVM có thể giao tiếp với cơ sở dữ liệu.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Cảnh báo:** Đảm bảo phiên bản driver phù hợp với phiên bản SQL Server của bạn. Sử dụng driver không tương thích có thể gây lỗi kết nối.

## Bước 3: Đọc dữ liệu dự án
Khởi tạo một đối tượng `Project` bằng cách truyền `MspDbSettings`. Aspose.Tasks sẽ tự động lấy dữ liệu dự án từ cơ sở dữ liệu.

```java
Project project = new Project(settings);
```

Tại thời điểm này, bạn có thể khám phá đối tượng `project` — liệt kê các task, resource, hoặc chỉnh sửa các trường theo nhu cầu.

## Bước 4: Lưu dự án dưới dạng PDF
Xuất dự án đã tải lên thành định dạng bạn muốn. Ví dụ dưới đây lưu dự án dưới dạng **PDF**, rất phù hợp cho các báo cáo có thể in. Bạn cũng có thể **xuất dự án sang XML** hoặc **chuyển đổi dự án sang HTML** bằng cách thay đổi enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Nếu muốn lưu dưới dạng XML, chỉ cần thay `SaveFileFormat.Pdf` bằng `SaveFileFormat.Xml`. Đối với đầu ra HTML, dùng `SaveFileFormat.Html`.

## Các vấn đề thường gặp & Giải pháp
| Vấn đề | Nguyên nhân thường gặp | Cách khắc phục |
|-------|------------------------|----------------|
| **Hết thời gian chờ kết nối** | Địa chỉ máy chủ/cổng sai hoặc tường lửa chặn | Kiểm tra lại địa chỉ máy chủ, mở cổng 1433, và thử kết nối bằng một chương trình JDBC đơn giản. |
| **Lỗi xác thực** | Tên người dùng/mật khẩu không hợp lệ hoặc SQL Server chưa cấu hình cho xác thực SQL | Sử dụng tài khoản SQL hợp lệ hoặc bật chế độ xác thực hỗn hợp trên server. |
| **Không tìm thấy driver** | Jar JDBC không có trong classpath | Đảm bảo `addJDBCDriver` trỏ tới file `.jar` đúng và đường dẫn sử dụng dấu gạch chéo ngược kép (`\\`). |
| **Dự án trống sau khi tải** | Quyền không đủ để đọc các bảng của Project Server | Cấp quyền SELECT cho tài khoản trên schema của cơ sở dữ liệu Project Server. |

## Câu hỏi thường gặp

**H: Aspose.Tasks có thể dùng để đọc dữ liệu dự án từ các cơ sở dữ liệu khác ngoài Microsoft Project không?**  
Đ: Có, Aspose.Tasks hỗ trợ đọc dữ liệu dự án từ nhiều nguồn, bao gồm tệp XML, Primavera và các cơ sở dữ liệu Microsoft Project.

**H: Aspose.Tasks có tương thích với các phiên bản khác nhau của Microsoft Project không?**  
Đ: Có, Aspose.Tasks được thiết kế để làm việc với nhiều phiên bản Microsoft Project, đảm bảo tích hợp liền mạch.

**H: Tôi có thể thao tác dữ liệu dự án trước khi lưu không?**  
Đ: Chắc chắn, Aspose.Tasks cung cấp API phong phú để thêm task, cập nhật resource và thiết lập thuộc tính dự án trước khi xuất.

**H: Aspose.Tasks hỗ trợ nhiều định dạng đầu ra không?**  
Đ: Có, bạn có thể lưu dự án dưới dạng PDF, XML, HTML, CSV, PNG, JPEG và nhiều định dạng khác.

**H: Tôi có thể tìm hỗ trợ hoặc trợ giúp thêm về Aspose.Tasks ở đâu?**  
Đ: Để được hỗ trợ thêm, hãy truy cập diễn đàn Aspose.Tasks hoặc khám phá tài liệu trên website [here](https://forum.aspose.com/c/tasks/15).

## Kết luận
Bằng cách làm theo hướng dẫn chi tiết này, bạn đã biết cách **đọc cơ sở dữ liệu Microsoft Project**, **lưu dự án dưới dạng PDF**, và xuất sang các định dạng khác bằng Aspose.Tasks cho Java. Cách tiếp cận này loại bỏ phụ thuộc vào Microsoft Project, tối ưu hoá báo cáo tự động và mở ra cơ hội tích hợp tùy chỉnh mạnh mẽ.

---

**Cập nhật lần cuối:** 2026-02-18  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.5 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}