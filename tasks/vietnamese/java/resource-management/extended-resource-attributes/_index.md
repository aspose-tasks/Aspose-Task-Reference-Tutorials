---
date: 2026-06-10
description: Tìm hiểu cách tạo thuộc tính mở rộng trong Java, tải tệp Microsoft Project,
  đặt giá trị số và lưu dự án dưới dạng XML bằng Aspose.Tasks for Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Xử lý Thuộc tính Tài nguyên Mở rộng trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách tạo thuộc tính mở rộng trong Java với Aspose.Tasks
url: /vi/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo thuộc tính mở rộng trong Java với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn thực hành này, bạn sẽ **tạo thuộc tính mở rộng trong Java** cho một tệp Microsoft Project bằng Aspose.Tasks. Chúng tôi sẽ hướng dẫn tải một dự án hiện có, định nghĩa một thuộc tính số mới, gán giá trị cho một tài nguyên, và cuối cùng lưu các thay đổi dưới dạng tệp XML. Khi hoàn thành, bạn sẽ có một mẫu mã có thể tái sử dụng trong bất kỳ giải pháp quản lý dự án dựa trên Java nào.

## Câu trả lời nhanh
- **Thuộc tính mở rộng là gì?**  
  Một trường do người dùng định nghĩa (ví dụ: Tuổi, Cấp độ kỹ năng) lưu trữ dữ liệu bổ sung cho tài nguyên hoặc nhiệm vụ.  
- **API nào tạo ra nó?**  
  Aspose.Tasks for Java cung cấp lớp `ExtendedAttributeDefinition` để định nghĩa và quản lý các thuộc tính tùy chỉnh.  
- **Tôi có cần giấy phép không?**  
  Giấy phép đánh giá tạm thời hoạt động cho việc phát triển; giấy phép đầy đủ là bắt buộc cho triển khai sản xuất.  
- **Tôi có thể lưu số không?**  
  Có – sử dụng `setNumericValue(BigDecimal)` để gán giá trị thập phân chính xác.  
- **Làm thế nào để lưu các thay đổi?**  
  Gọi `project.save("output.xml", SaveFileFormat.Xml)` để ghi dự án đã cập nhật dưới dạng XML.

## Thuộc tính tùy chỉnh là gì?
Một **thuộc tính tùy chỉnh** (còn gọi là thuộc tính mở rộng) là một cột bổ sung mà bạn có thể thêm vào tài nguyên hoặc nhiệm vụ trong Microsoft Project. Nó cho phép bạn ghi lại dữ liệu không được các trường mặc định bao phủ, chẳng hạn như tuổi nhân viên, mức độ chứng chỉ, hoặc bất kỳ chỉ số nào đặc thù cho doanh nghiệp.

## Tại sao tạo thuộc tính mở rộng trong Java?
Việc tạo thuộc tính mở rộng trong Java cho phép bạn làm giàu dữ liệu dự án một cách lập trình, đảm bảo tính nhất quán giữa các tệp và hỗ trợ báo cáo tự động. Khi định nghĩa thuộc tính một lần, bạn có thể áp dụng nó cho bất kỳ số lượng tài nguyên hoặc nhiệm vụ nào mà không cần nhập liệu thủ công, tiết kiệm thời gian và giảm lỗi.

- **‑ Điều chỉnh dữ liệu cho tổ chức của bạn** – lưu bất kỳ chỉ số nào quan trọng mà không cần các giải pháp thủ công trong Excel.  
- **‑ Cho phép báo cáo phong phú hơn** – truy vấn trường tùy chỉnh sau này cho bảng điều khiển hoặc phân tích.  
- **‑ Duy trì tính nhất quán** – áp dụng cùng một định nghĩa một cách lập trình trên hàng chục dự án, loại bỏ lỗi con người.  
- **‑ Kiểm chứng hiệu năng** – Aspose.Tasks xử lý các dự án lên tới 10.000 nhiệm vụ và 5.000 tài nguyên mà không cần tải toàn bộ tệp vào bộ nhớ, theo các tiêu chuẩn sản phẩm.

## Yêu cầu trước
1. **Java Development Kit** – Cài đặt JDK 8 hoặc mới hơn.  
2. **Aspose.Tasks for Java** – tải bản phát hành mới nhất từ [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, hoặc bất kỳ môi trường phát triển Java nào tương thích.  

## Cách tạo thuộc tính mở rộng trong Java?
Tải dự án của bạn, định nghĩa thuộc tính, gắn nó vào một tài nguyên và lưu tệp – tất cả trong một vài bước đơn giản. Các phần sau sẽ chia nhỏ mỗi bước thành giải thích ngắn gọn kèm theo vị trí placeholder cho mã thực tế của bạn.

### Hướng dẫn từng bước

#### Nhập gói
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` và các lớp liên quan nằm trong không gian tên `com.aspose.tasks`. Nhập chúng ở đầu tệp Java của bạn.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### Bước 1: Xác định thư mục dữ liệu
`Paths` là một lớp tiện ích cung cấp các phương thức để lấy đường dẫn hệ thống tệp một cách độc lập với nền tảng.

```java
String dataDir = "Your Data Directory";
```

#### Bước 2: Tải tệp Microsoft Project
`Project` đại diện cho một tệp Microsoft Project trong bộ nhớ, cho phép truy cập đọc và ghi nội dung của nó.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Bước 3: Định nghĩa Thuộc tính Tùy chỉnh
`ExtendedAttributeDefinition` định nghĩa lược đồ của một trường tùy chỉnh mới có thể được gắn vào tài nguyên hoặc nhiệm vụ.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Bước 4: Đặt Giá trị Số trong Java
`ExtendedAttributeResource` chứa giá trị của một thuộc tính tùy chỉnh cho một thể hiện tài nguyên cụ thể.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Bước 5: Thêm Tài nguyên và Gắn Thuộc tính Tùy chỉnh
`Resource` mô hình hoá một tài nguyên dự án như người, thiết bị hoặc vật liệu.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Bước 6: Lưu Dự án dưới dạng XML
`SaveFileFormat` liệt kê các định dạng đầu ra được hỗ trợ để lưu dự án, bao gồm XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Bước 7: Hiển thị Kết quả
`System.out.println` in ra một dòng văn bản tới đầu ra console tiêu chuẩn.

```java
System.out.println("Process completed Successfully");
```

## Những Cạm Bẫy Thường Gặp & Mẹo
- **Xung đột ID thuộc tính:** Luôn gọi `project.getExtendedAttributes().getById(id)` trước khi tạo định nghĩa mới để tránh trùng lặp định danh.  
- **Xử lý độ chính xác:** Ưu tiên `BigDecimal` hơn `float`/`double` cho các giá trị số chính xác; điều này tránh lỗi làm tròn trong báo cáo.  
- **Độ tin cậy đường dẫn tệp:** Sử dụng `Paths.get(...).toAbsolutePath()` hoặc cấu hình thư mục làm việc của IDE để loại bỏ `FileNotFoundException`.  

## Câu Hỏi Thường Gặp

**Q: Tôi có thể tạo thuộc tính tùy chỉnh cho nhiệm vụ cũng như tài nguyên không?**  
A: Có – sử dụng `ExtendedAttributeTask` thay vì `ExtendedAttributeResource` khi định nghĩa lược đồ thuộc tính.

**Q: Có thể thêm nhiều thuộc tính tùy chỉnh cùng lúc không?**  
A: Chắc chắn. Tạo các đối tượng `ExtendedAttributeDefinition` riêng biệt cho mỗi thuộc tính và gắn chúng vào các tài nguyên hoặc nhiệm vụ mong muốn.

**Q: Tôi có thể lưu dự án ở những định dạng nào?**  
A: Aspose.Tasks hỗ trợ XML, MPP, PDF, HTML và hơn 30 định dạng khác. Trong ví dụ này chúng tôi đã sử dụng `SaveFileFormat.Xml`.

**Q: Tôi có cần giấy phép cho bản dựng phát triển không?**  
A: Giấy phép đánh giá tạm thời đủ cho việc thử nghiệm. Đối với bất kỳ triển khai sản xuất nào, cần có giấy phép thương mại đầy đủ.

**Q: Làm thế nào để đọc lại giá trị thuộc tính tùy chỉnh sau này?**  
A: Gọi `resource.getExtendedAttributes()` và lặp qua bộ sưu tập; lấy giá trị lưu trữ bằng `getNumericValue()` hoặc `getTextValue()`.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Các Hướng Dẫn Liên Quan

- [Cách tạo tài nguyên – Quản lý tài nguyên với Aspose.Tasks cho Java](/tasks/java/resource-management/)
- [Tạo trường tùy chỉnh Aspose - Xử lý thuộc tính mở rộng](/tasks/java/project-management/extended-attributes/)
- [Cách tạo dự án – Đặt thuộc tính nhiệm vụ mới với Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}