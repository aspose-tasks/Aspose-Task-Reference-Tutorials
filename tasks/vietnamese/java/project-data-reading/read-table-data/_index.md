---
date: 2025-12-18
description: Tìm hiểu cách lấy các trường bảng và đọc dữ liệu bảng trong Java bằng
  Aspose.Tasks. Hướng dẫn này chỉ cho bạn cách truy xuất thông tin bảng từ các tệp
  Project.
linktitle: Read Table Data from File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách lấy các trường bảng và đọc dữ liệu bảng trong Aspose.Tasks
url: /vi/java/project-data-reading/read-table-data/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lấy các trường bảng và đọc dữ liệu bảng trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách lấy các trường bảng** từ tệp Microsoft Project và đọc dữ liệu bảng bằng Aspose.Tasks cho Java. Dù bạn đang xây dựng công cụ báo cáo, di chuyển dữ liệu, hay tự động hoá phân tích dự án, việc trích xuất thông tin bảng một cách lập trình sẽ tiết kiệm hàng giờ công việc thủ công. Chúng tôi sẽ hướng dẫn toàn bộ quy trình — từ thiết lập môi trường đến in chi tiết từng trường — để bạn có thể tích hợp khả năng này vào ứng dụng của mình ngay lập tức.

## Trả lời nhanh
- **“Lấy các trường bảng” có nghĩa là gì?** Nó đề cập tới việc truy xuất định nghĩa (độ rộng, tiêu đề, căn chỉnh, v.v.) của mỗi cột hiển thị trong bảng của một chế độ xem Project.  
- **Thư viện nào cần thiết?** Aspose.Tasks cho Java.  
- **Có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Có thể đọc bảng từ bất kỳ phiên bản Project nào không?** Có, Aspose.Tasks hỗ trợ các định dạng Project 2003‑2016 và mới hơn.  
- **Cần thiết lập gì thêm không?** Chỉ cần JDK 8+ và file JAR Aspose.Tasks nằm trong classpath.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy chắc chắn bạn đã có:

1. **Java Development Kit (JDK)** – JDK 8 hoặc mới hơn đã được cài đặt. Bạn có thể tải từ trang web của Oracle.  
2. **Aspose.Tasks cho Java JAR** – Tải thư viện mới nhất từ [liên kết tải xuống](https://releases.aspose.com/tasks/java/) và thêm vào đường dẫn xây dựng của dự án.

## Nhập gói
Nhập các lớp Aspose.Tasks cần thiết:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```

## Bước 1: Thiết lập thư mục dữ liệu
Xác định thư mục chứa tệp *.mpp* của bạn:

```java
String dataDir = "Your Data Directory";
```

Thay `"Your Data Directory"` bằng đường dẫn tuyệt đối trên máy của bạn (ví dụ: `C:/Projects/Data/`).

## Bước 2: Tải tệp Project
Tạo một thể hiện `Project` bằng cách chỉ đến tệp Project bạn muốn kiểm tra:

```java
Project project = new Project(dataDir + "Project2003.mpp");
```

Nếu tệp của bạn có tên hoặc phần mở rộng khác, hãy điều chỉnh chuỗi cho phù hợp.

## Bước 3: Truy xuất thông tin bảng
Bây giờ chúng ta sẽ **lấy các trường bảng** và hiển thị các thuộc tính của từng trường:

```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```

Đoạn mã in ra độ rộng, tiêu đề và căn chỉnh cho mỗi cột trong bảng mặc định, cung cấp cho bạn toàn cảnh về **các trường bảng** được định nghĩa trong dự án.

## Tại sao cần truy xuất thông tin bảng?
- **Tự động hoá** – Tạo báo cáo tùy chỉnh mà không cần sao chép‑dán thủ công.  
- **Di chuyển** – Chuyển dữ liệu từ các tệp Project cũ sang cơ sở dữ liệu hiện đại.  
- **Xác thực** – Đảm bảo các mẫu dự án tuân thủ tiêu chuẩn tổ chức.

## Những lỗi thường gặp & Mẹo
- **Bảng null** – Nếu một dự án không có bảng, `project.getTables()` có thể rỗng. Luôn kiểm tra kích thước danh sách trước khi truy cập chỉ mục `0`.  
- **Vấn đề mã hoá** – Các ký tự không phải ASCII trong tiêu đề sẽ hiển thị đúng khi bạn sử dụng phiên bản Aspose.Tasks mới nhất.  
- **Hiệu năng** – Tải các tệp *.mpp* rất lớn có thể tốn nhiều bộ nhớ; cân nhắc sử dụng API streaming cho các bộ dữ liệu khổng lồ.

## Kết luận
Sau khi thực hiện các bước trên, bạn đã biết **cách lấy các trường bảng** và đọc dữ liệu bảng từ tệp Microsoft Project bằng Aspose.Tasks cho Java. Khả năng này mở ra cánh cửa cho các kịch bản tự động hoá mạnh mẽ, quy trình di chuyển dữ liệu và giải pháp báo cáo tùy chỉnh trong các ứng dụng Java của bạn.

## Câu hỏi thường gặp
### H: Aspose.Tasks có tương thích với tất cả các phiên bản của Microsoft Project không?
A: Aspose.Tasks hỗ trợ nhiều phiên bản Microsoft Project, bao gồm Project 2003, 2007, 2010, 2013 và 2016.  
### H: Tôi có thể sửa đổi dữ liệu bảng và lưu lại vào tệp Project không?
A: Có, bạn có thể dùng Aspose.Tasks để chỉnh sửa dữ liệu bảng một cách lập trình và lưu các thay đổi trở lại tệp Project gốc.  
### H: Aspose.Tasks có yêu cầu giấy phép riêng cho việc sử dụng thương mại không?
A: Có, bạn cần mua giấy phép cho Aspose.Tasks nếu muốn sử dụng trong môi trường thương mại. Bạn có thể mua giấy phép tại [trang mua hàng](https://purchase.aspose.com/buy).  
### H: Có bản dùng thử miễn phí cho Aspose.Tasks không?
A: Có, bạn có thể tải bản dùng thử miễn phí của Aspose.Tasks từ [trang phát hành](https://releases.aspose.com/).  
### H: Tôi có thể tìm trợ giúp và hỗ trợ cho Aspose.Tasks ở đâu?
A: Bạn có thể truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận sự hỗ trợ từ cộng đồng và đội ngũ Aspose.

## Các câu hỏi thường gặp bổ sung

**H: Làm sao để đọc dữ liệu bảng trong môi trường đa‑dự án?**  
A: Tải mỗi dự án riêng biệt bằng `new Project(path)` và lặp lại vòng lặp trích xuất trường bảng cho từng thể hiện.

**H: Tôi có thể xuất các trường bảng đã lấy ra thành CSV không?**  
A: Có, sau khi in chi tiết trường, bạn có thể ghi chúng vào `FileWriter` hoặc dùng thư viện CSV như OpenCSV.

**H: Aspose.Tasks có xử lý các bảng tùy chỉnh do người dùng tạo không?**  
A: Chắc chắn. Bộ sưu tập `project.getTables()` bao gồm cả bảng mặc định và bảng do người dùng định nghĩa, vì vậy bạn có thể duyệt qua chúng theo nhu cầu.

**H: Nếu tệp Project được bảo vệ bằng mật khẩu thì sao?**  
A: Sử dụng hàm khởi tạo `Project` có tham số `LoadOptions` để chỉ định mật khẩu.

**H: Có cách nào để lọc chỉ các cột hiển thị không?**  
A: Kiểm tra phương thức `getVisible()` của mỗi `TableField` (có trong các phiên bản mới) để xác định cột có được hiển thị trong giao diện người dùng hay không.

---

**Cập nhật lần cuối:** 2025-12-18  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}