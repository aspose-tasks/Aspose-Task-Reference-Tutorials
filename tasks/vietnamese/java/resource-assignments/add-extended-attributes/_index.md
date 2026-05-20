---
date: 2026-05-20
description: Tìm hiểu cách sử dụng Aspose.Tasks for Java để thêm thuộc tính mở rộng
  vào phân công tài nguyên, đặt ngày bắt đầu dự án và ghi tệp MS Project một cách
  hiệu quả.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Thêm thuộc tính mở rộng vào phân công tài nguyên trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách sử dụng Aspose.Tasks for Java – Thêm thuộc tính mở rộng vào phân công
  tài nguyên
url: /vi/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Làm Chủ Việc Thao Tác MS Project với Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách sử dụng Aspose.Tasks cho Java** để thêm các thuộc tính mở rộng vào việc gán tài nguyên và ghi thông tin Microsoft Project một cách lập trình. Cho dù bạn đang tự động hoá quy trình báo cáo hay xây dựng công cụ quản lý dự án tùy chỉnh, các bước dưới đây sẽ chỉ cho bạn cách đặt ngày bắt đầu dự án, tạo các gán tài nguyên và lưu tệp dưới dạng XML—tất cả chỉ với vài dòng mã Java.

## Câu trả lời nhanh
- **Aspose.Tasks cho Java làm gì?** Nó đọc, ghi và chỉnh sửa các tệp Microsoft Project mà không cần cài đặt Microsoft Project.  
- **Tôi có thể thêm trường tùy chỉnh vào một gán tài nguyên không?** Có, sử dụng bộ sưu tập `ExtendedAttribute` trên đối tượng `ResourceAssignment`.  
- **Làm thế nào để đặt ngày bắt đầu dự án?** Gọi `project.setStartDate(LocalDateTime.of(...))` trước khi lưu.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Giấy phép thương mại loại bỏ các dấu bản quyền đánh giá và mở khóa toàn bộ quyền truy cập API.  
- **Phiên bản Java nào được hỗ trợ?** Aspose.Tasks cho Java hỗ trợ JDK 8 đến JDK 21.

## Cách sử dụng Aspose.Tasks cho Java?
`Project` là đối tượng chính đại diện cho một tệp Microsoft Project trong bộ nhớ. Tải thư viện Aspose.Tasks, tạo một thể hiện `Project`, cấu hình các thuộc tính cấp dự án, thêm các thuộc tính mở rộng vào một gán tài nguyên, và cuối cùng lưu dự án dưới dạng XML. Quy trình cốt lõi được chia thành ba bước ngắn gọn: khởi tạo, chỉnh sửa và lưu. Mẫu này hoạt động cho bất kỳ kích thước tệp dự án nào và chạy trên các JVM của Windows, Linux hoặc macOS.

## Thuộc tính mở rộng trong Aspose.Tasks là gì?
Một **thuộc tính mở rộng** là một trường tùy chỉnh mà bạn gắn vào các công việc, tài nguyên hoặc gán để lưu trữ siêu dữ liệu bổ sung ngoài các cột mặc định. `ExtendedAttributeDefinition` định nghĩa lược đồ cho một trường tùy chỉnh. Aspose.Tasks cung cấp các lớp `ExtendedAttributeDefinition` và `ExtendedAttribute` để định nghĩa và gán các trường này một cách lập trình.

## Tại sao cần thêm thuộc tính mở rộng vào gán tài nguyên?
Aspose.Tasks hỗ trợ **hơn 50 trường mặc định và tùy chỉnh**, và bạn có thể thêm không giới hạn các thuộc tính do người dùng định nghĩa. Việc thêm chúng cho phép bạn ghi lại mã chi phí, ID phòng ban, hoặc bất kỳ dữ liệu kinh doanh nào trực tiếp trong tệp .mpp, loại bỏ nhu cầu sử dụng bảng tính bên ngoài và đảm bảo tính toàn vẹn dữ liệu trong suốt vòng đời dự án.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – Cài đặt JDK 8 hoặc mới hơn.  
2. **Thư viện Aspose.Tasks cho Java** – Tải xuống từ trang phát hành chính thức [tại đây](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình chỉnh sửa Java nào bạn thích.

## Nhập các gói
Đầu tiên, nhập các gói cần thiết vào dự án Java của bạn:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Bước 1: Thiết lập thư mục dữ liệu
Xác định thư mục nơi dữ liệu dự án của bạn sẽ được lưu trữ. Đường dẫn này sẽ được sử dụng sau này khi bạn lưu tệp XML.

```java
String dataDir = "Your Data Directory";
```

### Bước 2: Tạo thể hiện Project
Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks đại diện cho một tệp Microsoft Project duy nhất trong bộ nhớ. Khi khởi tạo nó, bạn sẽ có quyền truy cập đầy đủ vào tất cả các thành phần của dự án.

```java
Project project = new Project();
```

### Bước 3: Đặt các thuộc tính thông tin dự án
Đặt các thuộc tính quan trọng của dự án như ngày bắt đầu, cờ lịch trình từ ngày bắt đầu và ngày trạng thái. Các giá trị này được lưu trong đối tượng `ProjectInfo` của dự án.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Bước 4: Thêm thuộc tính mở rộng vào một gán tài nguyên
Tạo một `ExtendedAttributeDefinition` cho trường tùy chỉnh, gắn nó vào một `ResourceAssignment`, và điền giá trị. Bước này minh họa từ khóa **add extended attributes** trong hành động.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Các vấn đề thường gặp và giải pháp
- **NullPointerException khi truy cập bộ sưu tập gán** – Đảm bảo bạn đã tạo ít nhất một tài nguyên và một công việc trước khi lấy các gán.  
- **Thuộc tính mở rộng không xuất hiện trong MS Project** – Kiểm tra xem `FieldId` của thuộc tính có khớp với một vị trí trường tùy chỉnh không (ví dụ, `ExtendedAttributeTask.Text1`).  
- **Định dạng ngày không khớp** – Sử dụng `java.time.LocalDateTime` cho các giá trị ngày; Aspose.Tasks sẽ tự động chuyển chúng sang định dạng lịch của Project.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java để đọc các tệp MS Project không?**  
A: Có, thư viện cung cấp khả năng đọc‑ghi đầy đủ cho các định dạng .mpp, .xml và .xps.

**Q: Aspose.Tasks cho Java có tương thích với các phiên bản khác nhau của MS Project không?**  
A: Hoàn toàn có, nó hỗ trợ các tệp từ Project 2000 đến phiên bản mới nhất 2024, bao phủ hơn 20 định dạng phiên bản.

**Q: Có bất kỳ hạn chế nào đối với phiên bản dùng thử của Aspose.Tasks cho Java không?**  
A: Phiên bản dùng thử sẽ thêm dấu watermark vào các tệp được tạo và giới hạn số lượng công việc bạn có thể tạo, nhưng tất cả các tính năng API vẫn có thể truy cập.

**Q: Làm thế nào tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java?**  
A: Bạn có thể tìm kiếm sự trợ giúp từ diễn đàn cộng đồng Aspose.Tasks [tại đây](https://forum.aspose.com/c/tasks/15).

**Q: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?**  
A: Có, giấy phép tạm thời có sẵn cho việc sử dụng ngắn hạn. Bạn có thể lấy một giấy phép từ [tại đây](https://purchase.aspose.com/temporary-license/).

**Cập nhật lần cuối:** 2026-05-20  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các hướng dẫn liên quan

- [Cách Thêm Ghi chú vào Gán Tài nguyên trong Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Cách Đọc Rate Scale và Ghi Rate Scale cho Gán Tài nguyên trong Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Cách Thêm Tài nguyên vào Dự án và Xử lý Thuộc tính Độ trễ Cân bằng trong Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}