---
date: 2026-09-30
description: Tìm hiểu cách tạo task extended attribute bằng Aspose.Tasks cho Java,
  thư viện project management library Java hàng đầu để thêm custom task fields.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Cách tạo task extended attribute bằng Aspose.Tasks Java
og_description: Tìm hiểu cách tạo task extended attribute bằng Aspose.Tasks cho Java,
  thư viện project management library Java hàng đầu để thêm custom task fields.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Cách tạo task extended attribute bằng Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Cách tạo task extended attribute bằng Aspose.Tasks Java
url: /vi/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo thuộc tính mở rộng cho tác vụ với Aspose.Tasks Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **tạo thuộc tính mở rộng cho tác vụ** trong một tệp Microsoft Project bằng cách sử dụng Aspose.Tasks cho Java. Thêm các trường tùy chỉnh cho phép bạn ghi lại dữ liệu dự án‑cụ thể mà các cột tích hợp sẵn không bao phủ, mang lại khả năng kiểm soát chi tiết hơn đối với báo cáo và lập kế hoạch nguồn lực. Khi kết thúc hướng dẫn, bạn sẽ có thể thêm các thuộc tính dạng văn bản thuần, hỗ trợ tra cứu và thời lượng cho bất kỳ tác vụ nào.

## Câu trả lời nhanh
- **“Thuộc tính mở rộng” có nghĩa là gì?** Đó là một trường tùy chỉnh mà bạn định nghĩa và gắn vào tác vụ, nguồn lực hoặc phân công.  
- **Thư viện nào cung cấp khả năng này?** Aspose.Tasks cho Java, một thư viện quản lý dự án bằng Java.  
- **Tôi có cần giấy phép để thử không?** Có – bản dùng thử miễn phí 30 ngày có sẵn trên trang web Aspose.  
- **Tôi có thể thêm các giá trị tra cứu không?** Chắc chắn; bạn có thể cung cấp danh sách các giá trị cho phép cho các trường văn bản hoặc thời lượng.  
- **API có tương thích với Java 8 và các phiên bản sau không?** Có, nó hỗ trợ Java 8+ và chạy trên mọi hệ điều hành chính.

## Thuộc tính mở rộng của tác vụ là gì?
Thuộc tính mở rộng của tác vụ là một cột do người dùng định nghĩa, lưu trữ thông tin bổ sung cho mỗi tác vụ trong tệp Project. Nó hoạt động giống như một trường tích hợp sẵn nhưng có thể chứa bất kỳ kiểu dữ liệu nào bạn cần, chẳng hạn như văn bản, số, ngày tháng hoặc thời lượng.

## Tại sao nên sử dụng Aspose.Tasks cho Java?
Aspose.Tasks hỗ trợ **hơn 50 định dạng tệp** và có thể xử lý các dự án với **hơn 10.000 tác vụ** mà không cần cài đặt Microsoft Project. Thư viện hoạt động hoàn toàn offline, đảm bảo tính riêng tư dữ liệu và hiệu năng quyết định cho các giải pháp quy mô doanh nghiệp.

## Yêu cầu trước
- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Tasks cho Java đã được cài đặt. Bạn có thể tải xuống từ [website](https://releases.aspose.com/tasks/java/).  
- Một IDE Java (IntelliJ IDEA, Eclipse hoặc VS Code) đã được cấu hình trên máy của bạn.

## Nhập các gói
Các câu lệnh `import` cung cấp quyền truy cập vào các lớp cốt lõi bạn sẽ cần, chẳng hạn như `Project`, `ExtendedAttributeDefinition` và `ExtendedAttribute`.  

`Project` đại diện cho một tệp Microsoft Project và cung cấp các phương thức để đọc, sửa đổi và lưu lại.  
`ExtendedAttributeDefinition` định nghĩa một trường tùy chỉnh có thể gắn vào tác vụ, nguồn lực hoặc phân công.  
`ExtendedAttribute` là một thể hiện của định nghĩa, chứa giá trị thực tế cho một thực thể cụ thể.

## Làm thế nào để thêm thuộc tính mở rộng dạng văn bản thuần cho một tác vụ?
Để thêm thuộc tính mở rộng dạng văn bản thuần, bạn đầu tiên tải dự án, sau đó tạo một định nghĩa loại Text, thêm nó vào bộ sưu tập của dự án, tạo một tác vụ, khởi tạo thuộc tính từ định nghĩa, đặt giá trị văn bản, gắn nó vào tác vụ và cuối cùng lưu dự án.

### 1. Đặt đường dẫn thư mục tài liệu
Xác định vị trí các tệp nguồn và đầu ra của bạn.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Tạo một dự án mới
Khởi tạo một đối tượng `Project`, tùy chọn tải một tệp .mpp hiện có.

```java
String dataDir = "Your Document Directory";
```

### 3. Tạo định nghĩa thuộc tính mở rộng loại Text1
Định nghĩa trường tùy chỉnh dưới dạng cột văn bản thuần có tên “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Thêm định nghĩa vào bộ sưu tập thuộc tính mở rộng của dự án
Đăng ký định nghĩa mới để dự án nhận diện nó.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Thêm một tác vụ vào dự án
Tạo một tác vụ sẽ nhận trường tùy chỉnh.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Tạo một thuộc tính mở rộng từ định nghĩa thuộc tính
Tạo một thể hiện mà bạn có thể gắn vào một tác vụ cụ thể.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Gán giá trị cho thuộc tính mở rộng đã tạo
Đặt văn bản thực tế bạn muốn lưu, ví dụ: “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Thêm thuộc tính mở rộng vào tác vụ
Gắn thể hiện thuộc tính vào bộ sưu tập `ExtendedAttributes` của tác vụ.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Lưu dự án
Ghi dự án đã cập nhật trở lại đĩa ở định dạng mong muốn.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Làm thế nào để thêm thuộc tính văn bản với tùy chọn tra cứu?
Khi thêm thuộc tính văn bản có tra cứu, bạn thực hiện các bước giống như với thuộc tính văn bản thuần, nhưng trước khi thêm định nghĩa, bạn phải điền bộ sưu tập `LookupValues` của nó với các chuỗi cho phép. Các giá trị này sẽ xuất hiện dưới dạng danh sách thả xuống trong Microsoft Project, đảm bảo tính nhất quán dữ liệu.

## Làm thế nào để thêm thuộc tính thời lượng với tùy chọn tra cứu?
Để thêm thuộc tính thời lượng có tra cứu, thay thế loại `Text1` bằng `Duration2` khi tạo định nghĩa, sau đó điền bộ sưu tập `LookupValues` bằng các chuỗi thời lượng như “1 day”, “2 days”, v.v. Sau khi định nghĩa được thêm vào dự án, tạo thể hiện thuộc tính, đặt giá trị thời lượng, gắn vào tác vụ và lưu tệp.

## Các vấn đề thường gặp và khắc phục
- **Giá trị tra cứu không hiển thị** – Đảm bảo bạn thêm mỗi mục tra cứu vào bộ `LookupValues` *trước* khi gọi `project.getExtendedAttributes().add(definition)`.  
- **Giá trị thuộc tính không được lưu** – Xác nhận rằng bạn đã thêm thể hiện `ExtendedAttribute` vào tác vụ *sau* khi đặt giá trị.  
- **Kích thước tệp tăng bất ngờ** – Khi làm việc với các dự án rất lớn, cân nhắc gọi `project.setSaveOptions(new ProjectSaveOptions())` để bật lưu incremental.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java cùng với các thư viện Java khác không?**  
A: Có, Aspose.Tasks cho Java tích hợp mượt mà với bất kỳ hệ sinh thái Java nào, bao gồm Spring, Hibernate và Apache POI.

**Q: Aspose.Tasks cho Java có phù hợp cho các ứng dụng quản lý dự án quy mô lớn không?**  
A: Chắc chắn. Thư viện được thiết kế để xử lý các dự án có hàng ngàn tác vụ và hỗ trợ streaming để giảm mức sử dụng bộ nhớ.

**Q: Có những lưu ý nào về giấy phép khi sử dụng Aspose.Tasks cho Java trong dự án thương mại không?**  
A: Có, bạn cần một giấy phép thương mại hợp lệ. Bạn có thể xem chi tiết trên [trang web Aspose.Tasks](https://purchase.aspose.com/buy).

**Q: Làm sao tôi có thể nhận hỗ trợ hoặc trợ giúp với Aspose.Tasks cho Java?**  
A: Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận trợ giúp cộng đồng, hoặc mở ticket hỗ trợ qua tài khoản Aspose của bạn.

**Q: Tôi có thể dùng thử Aspose.Tasks cho Java trước khi mua không?**  
A: Có, bạn có thể tải phiên bản dùng thử miễn phí trên trang [Aspose.Tasks free trial](https://releases.aspose.com/).

---

**Cập nhật lần cuối:** 2026-09-30  
**Kiểm tra với:** Aspose.Tasks cho Java 24.10  
**Tác giả:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Hướng dẫn liên quan

- [Các cột tùy chỉnh và thuộc tính mở rộng trong quản lý dự án Java](/tasks/java/project-management/extended-attributes/)
- [Đọc thuộc tính mở rộng của tác vụ với Aspose.Tasks cho Java](/tasks/java/task-properties/extended-task-attributes/)
- [Cách tạo dự án aspose.tasks – Đặt thuộc tính mới cho tác vụ](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}