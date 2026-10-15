---
date: 2026-10-15
description: Tìm hiểu cách tạo activity, thiết lập thư mục dữ liệu, tùy chỉnh các
  trường bảng và lưu dự án dưới dạng MPP với Aspose.Tasks for Java. Hướng dẫn chi
  tiết từng bước cho các nhà phát triển Java.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Cách tạo activity và thiết lập thư mục dữ liệu bằng Aspose.Tasks for Java
og_description: Cách tạo activity, tùy chỉnh các trường bảng và lưu dự án dưới dạng
  MPP bằng Aspose.Tasks for Java. Thực hiện theo hướng dẫn chi tiết này để triển khai
  nhanh chóng.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Cách tạo activity và thiết lập thư mục dữ liệu trong Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Cách tạo activity và thiết lập thư mục dữ liệu bằng Aspose.Tasks for Java
url: /vi/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hoạt động và thiết lập thư mục dữ liệu bằng Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách tạo hoạt động** một cách lập trình, cấu hình **thư mục dữ liệu**, và **lưu dự án dưới dạng MPP** đồng thời **tùy chỉnh các trường bảng** trong chế độ xem biểu đồ Gantt. Aspose.Tasks cho Java là một API mạnh mẽ hỗ trợ hơn 30 định dạng nhập và xuất và có thể xử lý các dự án lên tới 10 000 nhiệm vụ mà không cần tải toàn bộ tệp vào bộ nhớ. Khi kết thúc hướng dẫn, bạn sẽ có thể tự động tạo dự án, làm phong phú các nhiệm vụ bằng các thuộc tính tùy chỉnh, và tạo ra một tệp MPP sẵn sàng mở cho Microsoft Project.

## Câu trả lời nhanh
- **Câu hỏi đầu tiên là gì?** Đặt đường dẫn thư mục dữ liệu nơi các tệp dự án của bạn nằm.  
- **Thư viện nào được yêu cầu?** Aspose.Tasks cho Java (có thể tải xuống từ trang chính thức).  
- **Tôi có thể thêm thuộc tính tùy chỉnh không?** Có – bạn có thể định nghĩa các thuộc tính mở rộng và hiển thị chúng trong biểu đồ Gantt.  
- **Tôi có cần giấy phép để thử nghiệm không?** Một giấy phép tạm thời có sẵn cho mục đích đánh giá.  
- **IDE nào hoạt động tốt nhất?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, NetBeans) đều hoạt động.

## “Thiết lập thư mục dữ liệu” là gì và tại sao nó quan trọng?
Thiết lập thư mục dữ liệu cho Aspose.Tasks biết nơi đọc và ghi các tệp dự án. Nếu đường dẫn không đúng, API sẽ không thể tìm thấy các tệp `.mpp` của bạn, dẫn đến lỗi `FileNotFoundException`. Định nghĩa thư mục này ngay từ đầu mã giúp quy trình lặp lại được và tách biệt các vấn đề về hệ thống tệp khỏi logic nghiệp vụ.

## Tại sao tùy chỉnh các trường bảng trong biểu đồ Gantt?
Các trường bảng tùy chỉnh cho phép bạn hiển thị thông tin bổ sung—như thuộc tính tùy chỉnh, dữ liệu nguồn lực, hoặc ghi chú dự án—trực tiếp trong chế độ xem Gantt. Điều này giảm nhu cầu tạo báo cáo riêng biệt và cung cấp cho các bên liên quan một hình ảnh dữ liệu phong phú có thể cải thiện tốc độ ra quyết định lên tới 30 %.

## Cách tạo hoạt động mới?
Bạn tạo một hoạt động (nhiệm vụ) mới bằng cách khởi tạo một đối tượng `Task` và thêm nó vào bộ sưu tập nhiệm vụ gốc của dự án. Cách tiếp cận này cho phép bạn tự động tạo lịch trình lớn, kéo dữ liệu nhiệm vụ từ các hệ thống bên ngoài, hoặc áp dụng các cập nhật hàng loạt mà không cần chỉnh sửa thủ công.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

1. **Bộ công cụ phát triển Java (JDK)** – phiên bản 8 hoặc mới hơn.  
2. **Aspose.Tasks cho Java** – tải xuống từ **trang phát hành Aspose.Tasks Java**.  
3. **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình chỉnh sửa nào tương thích Java mà bạn thích.  

## Nhập các gói
Không gian tên `com.aspose.tasks` chứa tất cả các lớp bạn sẽ cần để thao tác dự án. Việc nhập nó sẽ cho phép bạn truy cập `Project`, `Task`, `ExtendedAttributeDefinition`, và các kiểu cốt lõi khác.

```java
import com.aspose.tasks.*;
```

## Phụ thuộc Maven (tùy chọn)
Nếu bạn quản lý dự án bằng Maven, hãy thêm phụ thuộc Aspose.Tasks vào `pom.xml`. Điều này sẽ tự động giải quyết thư viện trong quá trình biên dịch.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Hướng dẫn từng bước

### Bước 1: thiết lập thư mục dữ liệu
Xác định thư mục chứa các tệp dự án của bạn. Biến `dataDir` giữ đường dẫn tuyệt đối và sẽ được tái sử dụng trong toàn bộ hướng dẫn.

```java
String dataDir = "Your Data Directory";
```

Thay `"Your Data Directory"` bằng đường dẫn đầy đủ tới thư mục chứa `project.mpp`, ví dụ `C:/Projects/MyGantt`.

### Bước 2: tải tệp dự án
`Project` là đối tượng cấp cao nhất của Aspose.Tasks đại diện cho một tệp Microsoft Project duy nhất trong bộ nhớ. Tải một tệp hiện có cho phép bạn truy cập các nhiệm vụ, nguồn lực và bảng của nó.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Bước 3: thêm hoạt động mới
`Task` đại diện cho một hoạt động cá nhân trong lịch trình. Thêm một nhiệm vụ vào bộ sưu tập nhiệm vụ gốc sẽ chèn nó vào cấp độ cao nhất của cấu trúc dự án.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Bước 4: định nghĩa thuộc tính tùy chỉnh
`ExtendedAttributeDefinition` cho phép bạn tạo một trường tùy chỉnh có thể tái sử dụng và gắn vào bất kỳ nhiệm vụ, nguồn lực hoặc phân công nào.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Bước 5: thêm thuộc tính tùy chỉnh vào nhiệm vụ
`ExtendedAttribute` là thể hiện cụ thể của một thuộc tính tùy chỉnh mà bạn gán cho một nhiệm vụ cụ thể.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Bước 6: tùy chỉnh bảng – thêm thuộc tính tùy chỉnh làm cột
`TableField` mô tả một cột trong bảng biểu đồ Gantt. Bằng cách thêm một `TableField` tham chiếu đến thuộc tính tùy chỉnh, bạn làm cho thuộc tính này hiển thị trong chế độ xem biểu đồ.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Bước 7: lưu dự án
Gọi `project.save` sẽ ghi lại tất cả các thay đổi vào một tệp mới. Hằng số `SaveFileFormat.MPP` thông báo cho Aspose.Tasks ghi tệp dưới định dạng nhị phân gốc của Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **FileNotFoundException** khi tải dự án | Đường dẫn **thiết lập thư mục dữ liệu** không đúng hoặc thiếu dấu gạch chéo cuối. | Xác minh `dataDir` trỏ tới đúng thư mục và bao gồm ký tự phân tách tệp thích hợp (`/` hoặc `\\`). |
| Thuộc tính tùy chỉnh không hiển thị trong chế độ xem Gantt | Trường bảng được thêm ở chỉ mục sai hoặc độ rộng cột quá nhỏ. | Đảm bảo `table.getTableFields().add(3, attrField);` sử dụng chỉ mục hợp lệ và điều chỉnh `setWidth` nếu cần. |
| LicenseException khi lưu | Không có giấy phép hợp lệ được áp dụng cho môi trường sản xuất. | Áp dụng giấy phép tạm thời hoặc vĩnh viễn trước khi gọi `project.save()`. |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
A: Có, Aspose.Tasks có sẵn cho .NET, Java và C++.

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks không?**  
A: Có, bạn có thể tải bản dùng thử miễn phí từ **trang tải bản dùng thử miễn phí Aspose.Tasks**.

**Q: Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?**  
A: Bạn có thể tìm hỗ trợ và đặt câu hỏi trên [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Làm thế nào để mua giấy phép cho Aspose.Tasks?**  
A: Bạn có thể mua giấy phép từ **trang mua Aspose.Tasks**.

**Q: Tôi có cần giấy phép tạm thời cho mục đích thử nghiệm không?**  
A: Có, bạn có thể nhận giấy phép tạm thời từ **trang yêu cầu giấy phép tạm thời**.

## Kết luận
Bạn đã biết **cách tạo hoạt động**, thiết lập thư mục dữ liệu, định nghĩa và gắn một thuộc tính tùy chỉnh, và **lưu dự án dưới dạng MPP** đồng thời **tùy chỉnh các trường bảng** trong chế độ xem biểu đồ Gantt bằng Aspose.Tasks cho Java. Những khả năng này cho phép bạn kiểm soát hoàn toàn dữ liệu dự án bằng lập trình, hỗ trợ tạo lịch trình tự động và báo cáo trực quan phong phú cho các bên liên quan.

---

**Cập nhật lần cuối:** 2026-10-15  
**Được kiểm tra với:** Aspose.Tasks Java 24.12 (mới nhất)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tạo tệp dự án trống trong Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Cách tạo tệp MPP – Tạo & Lưu dự án trống ở định dạng MPP với Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Cách tạo dự án Aspose.Tasks – Đặt thuộc tính nhiệm vụ mới](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}