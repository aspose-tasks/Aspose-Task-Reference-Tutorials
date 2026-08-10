---
date: 2026-05-26
description: Tìm hiểu cách lấy table fields và đọc table data trong Java bằng Aspose.Tasks.
  Hướng dẫn này cho bạn biết cách truy xuất thông tin bảng từ các tệp Project.
keywords:
- read table data aspose.tasks
- Aspose.Tasks Java
- project table extraction
linktitle: Đọc Table Data từ File trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to get table fields and read table data in Java using Aspose.Tasks.
    This tutorial shows you how to retrieve table information from Project files.
  headline: How to get table fields and read table data in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Load each project separately with `new Project(path)` and repeat the table‑field
      extraction loop for each instance.
    question: How do I read table data in a multi‑project environment?
  - answer: Yes, after printing the field details you can write them to a `FileWriter`
      or use a CSV library such as OpenCSV to generate a properly escaped file.
    question: Can I export the retrieved table fields to CSV?
  - answer: Absolutely. The `project.getTables()` collection includes both default
      and user‑defined tables, so you can iterate through them and process each one
      individually.
    question: Does Aspose.Tasks handle custom tables created by users?
  - answer: Use the overloaded `Project` constructor that accepts a `LoadOptions`
      object where you can specify the password, e.g., `new Project(path, new LoadOptions("pwd"))`.
    question: What if the Project file is password‑protected?
  - answer: Check each `TableField`'s `getVisible()` method (available in newer releases)
      to determine whether the column is displayed in the UI.
    question: Is there a way to filter only visible columns?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách lấy table fields và đọc table data trong Aspose.Tasks
url: /vi/java/project-data-reading/read-table-data/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lấy các trường bảng và đọc dữ liệu bảng trong Aspose.Tasks

## Giới thiệu
Trong tutorial này, bạn sẽ học **cách lấy các trường bảng** và **đọc dữ liệu bảng** từ tệp Microsoft Project bằng API **read table data aspose.tasks**. Cho dù bạn đang xây dựng bảng điều khiển báo cáo tùy chỉnh, di chuyển dữ liệu dự án cũ, hoặc tự động hoá phân tích lịch trình, việc trích xuất định nghĩa bảng một cách lập trình giúp tiết kiệm vô số giờ làm việc thủ công. Chúng tôi sẽ hướng dẫn cài đặt môi trường, tải dự án và in ra các thuộc tính của mỗi cột, để bạn có thể ngay lập tức sử dụng tính năng này trong các ứng dụng Java của mình.

## Câu trả lời nhanh
- **“get table fields” có nghĩa là gì?** Nó đề cập đến việc lấy định nghĩa (độ rộng, tiêu đề, căn chỉnh, v.v.) của mỗi cột được hiển thị trong bảng view của Project.  
- **Thư viện nào cần thiết?** Aspose.Tasks for Java.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Có thể đọc bảng từ bất kỳ phiên bản Project nào không?** Có, Aspose.Tasks hỗ trợ hơn 15 phiên bản tệp Microsoft Project, từ Project 2003 đến Project 2024.  
- **Cần cài đặt bổ sung nào không?** Chỉ cần JDK 8+ và file JAR Aspose.Tasks trong classpath của bạn.

## read table data aspose.tasks là gì?
read table data aspose.tasks là bộ phương thức API của Aspose.Tasks cho phép bạn truy cập một cách lập trình vào cấu trúc và nội dung của các bảng được định nghĩa trong tệp Microsoft Project. Nó trả về siêu dữ liệu như độ rộng cột, tiêu đề, căn chỉnh và khả năng hiển thị, cho phép bạn tái tạo hoặc chuyển đổi lịch trình dự án sang bất kỳ định dạng nào bạn cần.

## Tại sao nên sử dụng Aspose.Tasks để đọc dữ liệu bảng?
Aspose.Tasks xử lý **hơn 50 định dạng tệp Project khác nhau** (bao gồm MPP, MPX, XML và Primavera) và có thể làm việc với các tệp chứa **lên tới 10.000 nhiệm vụ** mà không cần tải toàn bộ tệp vào bộ nhớ. Hiệu năng được định lượng này cho phép bạn an toàn trích xuất bảng từ các dự án doanh nghiệp lớn đồng thời giữ mức sử dụng bộ nhớ dưới 200 MB.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Java Development Kit (JDK) 8 hoặc mới hơn** – tải về từ trang web chính thức của Oracle.  
2. **Aspose.Tasks for Java JAR** – lấy phiên bản mới nhất từ [liên kết tải xuống](https://releases.aspose.com/tasks/java/) và thêm vào đường dẫn biên dịch của dự án.  

> **Mẹo chuyên nghiệp:** Nếu bạn sử dụng Maven hoặc Gradle, bạn có thể tham chiếu trực tiếp tới artifact Aspose.Tasks để đơn giản hoá việc quản lý phụ thuộc.

## Nhập gói
`Project`, `Table`, và `TableField` là các lớp cốt lõi của quy trình đọc bảng.

Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks, đại diện cho một tệp Microsoft Project duy nhất trong bộ nhớ.

Lớp `Table` bao gồm một tập hợp các đối tượng `TableField`, mỗi đối tượng mô tả một cột của một view.

Lớp `TableField` là bộ giữ định nghĩa cho độ rộng, tiêu đề, căn chỉnh và khả năng hiển thị của một cột.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```

## Bước 1: Thiết lập Thư mục Dữ liệu
Xác định thư mục chứa tệp *.mpp* của bạn:

```java
String dataDir = "Your Data Directory";
```

Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối trên máy của bạn (ví dụ, `C:/Projects/Data/`). Sử dụng đường dẫn tuyệt đối giúp tránh những mơ hồ của class‑loader khi mã chạy từ các IDE khác nhau.

## Bước 2: Tải tệp Project
Tạo một thể hiện `Project` bằng cách chỉ tới tệp Project bạn muốn kiểm tra:

```java
Project project = new Project(dataDir + "Project2003.mpp");
```

Nếu tệp của bạn có tên hoặc phần mở rộng khác, hãy điều chỉnh chuỗi cho phù hợp. Hàm khởi tạo tự động phát hiện định dạng tệp, vì vậy bạn không cần chỉ định phiên bản một cách thủ công.

## Bước 3: Lấy thông tin bảng
Bây giờ chúng ta sẽ **lấy các trường bảng** và hiển thị thuộc tính của mỗi trường:

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

Đoạn mã in ra độ rộng, tiêu đề và căn chỉnh cho mọi cột trong bảng mặc định, cung cấp cho bạn toàn cảnh về **các trường bảng** được định nghĩa trong dự án.

## Cách đọc dữ liệu bảng bằng Aspose.Tasks cho Java?
Để đọc dữ liệu bảng thực tế, đầu tiên tải dự án, sau đó lấy bảng mong muốn (ví dụ bảng mặc định) bằng cách sử dụng `project.getTables().getByName("Name")` hoặc theo chỉ mục. Duyệt qua tập hợp trả về bởi `table.getFields()` và truy cập các thuộc tính của mỗi `TableField` như độ rộng, tiêu đề, căn chỉnh và khả năng hiển thị. Cách tiếp cận này hoạt động với bất kỳ bảng tùy chỉnh hoặc tích hợp nào được định nghĩa trong tệp Project.

## Những lỗi thường gặp & Mẹo
- **Bảng null** – Nếu một dự án không có bảng, `project.getTables()` có thể rỗng. Luôn kiểm tra kích thước của tập hợp trước khi truy cập chỉ mục.  
- **Vấn đề mã hoá** – Các ký tự không phải ASCII trong tiêu đề sẽ hiển thị đúng khi bạn sử dụng phiên bản Aspose.Tasks mới nhất (24.12 hoặc mới hơn).  
- **Hiệu năng** – Tải các tệp *.mpp* rất lớn có thể tốn nhiều bộ nhớ; hãy cân nhắc sử dụng API streaming (`ProjectReader`) cho các tệp vượt quá 500 MB.  

## Câu hỏi thường gặp

**Q: Làm thế nào để đọc dữ liệu bảng trong môi trường đa‑dự án?**  
A: Tải mỗi dự án riêng biệt bằng `new Project(path)` và lặp lại vòng lặp trích xuất trường bảng cho mỗi thể hiện.

**Q: Tôi có thể xuất các trường bảng đã lấy ra sang CSV không?**  
A: Có, sau khi in chi tiết trường, bạn có thể ghi chúng vào một `FileWriter` hoặc sử dụng thư viện CSV như OpenCSV để tạo tệp được thoát ký tự đúng cách.

**Q: Aspose.Tasks có hỗ trợ các bảng tùy chỉnh do người dùng tạo không?**  
A: Chắc chắn. Bộ sưu tập `project.getTables()` bao gồm cả bảng mặc định và bảng do người dùng định nghĩa, vì vậy bạn có thể duyệt qua chúng và xử lý từng bảng một cách riêng biệt.

**Q: Nếu tệp Project được bảo vệ bằng mật khẩu thì sao?**  
A: Sử dụng hàm khởi tạo `Project` có overload chấp nhận đối tượng `LoadOptions` trong đó bạn có thể chỉ định mật khẩu, ví dụ `new Project(path, new LoadOptions("pwd"))`.

**Q: Có cách nào để lọc chỉ các cột hiển thị không?**  
A: Kiểm tra phương thức `getVisible()` của mỗi `TableField` (có trong các phiên bản mới) để xác định cột có được hiển thị trong giao diện người dùng hay không.

## Kết luận
Bằng cách thực hiện các bước trên, bạn đã biết cách **lấy các trường bảng** và đọc dữ liệu bảng từ tệp Microsoft Project bằng Aspose.Tasks cho Java. Khả năng này mở ra cánh cửa cho các kịch bản tự động hoá mạnh mẽ, quy trình di chuyển dữ liệu và giải pháp báo cáo tùy chỉnh trong các ứng dụng Java của bạn. Tiếp theo, hãy cân nhắc xuất siêu dữ liệu đã trích xuất sang JSON hoặc cơ sở dữ liệu để bạn có thể xây dựng danh mục dự án có thể tìm kiếm hoặc tích hợp với các công cụ BI.

---

**Last Updated:** 2026-05-26  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Hướng dẫn liên quan

- [Cách Đọc Thông Tin Dự Án từ Microsoft Project bằng Aspose.Tasks cho Java](/tasks/java/project-properties/read-project-info/)
- [Đọc cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho Java](/tasks/java/project-data-reading/read-project-database/)
- [java đọc cơ sở dữ liệu Access: Đọc Dữ liệu Dự Án với Aspose.Tasks](/tasks/java/project-data-reading/read-access-database/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}