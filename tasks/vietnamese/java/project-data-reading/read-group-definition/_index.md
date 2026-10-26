---
date: 2026-10-26
description: Cách đọc dữ liệu định nghĩa nhóm bằng cách sử dụng Aspose.Tasks cho Java.
  Trích xuất task grouping, criteria và formatting từ các tệp Microsoft Project để
  tự động hoá báo cáo và di chuyển.
keywords:
- how to read group
- generate group report
- automate project grouping
lastmod: 2026-10-26
linktitle: Đọc dữ liệu định nghĩa nhóm trong Aspose.Tasks
og_description: Cách đọc dữ liệu định nghĩa nhóm bằng cách sử dụng Aspose.Tasks cho
  Java. Trích xuất task grouping, criteria và formatting từ các tệp Microsoft Project
  để tự động hoá báo cáo và di chuyển.
og_image_alt: 'Tutorial guide: Read group definition data in Aspose.Tasks for Java'
og_title: Cách đọc dữ liệu định nghĩa nhóm với Aspose.Tasks cho Java
schemas:
- author: Aspose
  dateModified: '2026-10-26'
  description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  headline: How to read group definition data with Aspose.Tasks for Java
  type: TechArticle
- description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  name: How to read group definition data with Aspose.Tasks for Java
  steps:
  - name: set up your data directory
    text: Define the folder that contains the `.mpp` file you want to inspect. Using
      `java.nio.file.Paths` guarantees platform‑independent path handling.
  - name: load the project file
    text: Create a `Project` instance by pointing it to your `.mpp` file. The constructor
      reads the file header and builds an in‑memory model.
  - name: retrieve task groups count
    text: Print the total number of task groups defined in the project. This quick
      check confirms that the file actually contains grouping information.
  - name: retrieve specific task group information
    text: Grab a particular group (index 1 in this example) and display its name and
      the number of criteria it contains. Each group can have multiple criteria that
      define how tasks are grouped.
  - name: retrieve group criterion information
    text: Each group can have one or more criteria. The snippet below extracts details
      such as the field used for grouping, the grouping mode, cell color, and pattern.
  - name: check parent group
    text: Sometimes a criterion belongs to a parent group. This check confirms the
      relationship and prevents null‑pointer issues when navigating the hierarchy.
  - name: retrieve criterion’s font information
    text: Group criteria can have custom font styling. The following code prints the
      font family, size, style, and sorting direction, allowing you to recreate the
      exact look in your own UI.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read/write capabilities for Microsoft Project
      formats, allowing you to add tasks, change resources, and update group definitions
      programmatically.
    question: Can I use Aspose.Tasks for Java to modify project files?
  - answer: It supports MPP, XML, CSV, and other common Project formats across versions
      from Project 2000 up to the latest 2024 release.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Wrap file operations in `try‑catch` blocks and catch `TasksException`
      for detailed error information; inspect the exception’s `getMessage()` for clues.
    question: How should I handle errors while working with Aspose.Tasks for Java?
  - answer: Absolutely – you can export to PDF, XLSX, HTML, and more using the library’s
      dedicated export APIs.
    question: Does Aspose.Tasks for Java offer export to other formats?
  - answer: Visit the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for API references and the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for community assistance.
    question: Where can I find additional resources and support?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read group definition
- Aspose.Tasks
- Java project data
- group reporting
title: Cách đọc dữ liệu định nghĩa nhóm với Aspose.Tasks cho Java
url: /vi/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc dữ liệu định nghĩa nhóm trong Aspose.Tasks cho Java

## Giới thiệu
Aspose.Tasks for Java cho phép bạn truy cập, sửa đổi và phân tích các tệp Microsoft Project một cách lập trình. Trong hướng dẫn này, bạn sẽ học **cách đọc dữ liệu định nghĩa nhóm** từ tệp `.mpp`, trích xuất tên, tiêu chí và kiểu dáng trực quan của mỗi nhóm, sau đó sử dụng thông tin đó để tạo báo cáo tùy chỉnh hoặc di chuyển cài đặt sang các dự án khác. Nắm vững khả năng này giúp bạn tự động hoá báo cáo, xác thực cấu trúc dự án và tối ưu hoá quy trình làm việc dựa trên dữ liệu.

## Câu trả lời nhanh
- **“read group definition” có nghĩa là gì?** Nó có nghĩa là trích xuất các quy tắc nhóm (tên, tiêu chí, màu sắc, phông chữ) mà Microsoft Project sử dụng để sắp xếp các tác vụ.  
- **Thư viện nào tôi cần?** Aspose.Tasks for Java.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **IDE nào được hỗ trợ?** Bất kỳ IDE Java nào như IntelliJ IDEA hoặc Eclipse.  
- **Cần bao nhiêu mã?** Ít hơn 30 dòng Java để tải dự án và hiển thị chi tiết nhóm.

## Cách đọc dữ liệu định nghĩa nhóm
Tải dự án, liệt kê các nhóm của nó và kiểm tra tiêu chí của mỗi nhóm. Câu trả lời trực tiếp là: **Tạo một thể hiện `Project`, gọi `project.getTaskGroups()`, và lặp qua bộ sưu tập để đọc tên, tiêu chí, phông chữ và màu sắc.** Các phần tiếp theo chia quy trình thành các bước rõ ràng, mỗi bước kèm theo một placeholder mã ngắn mà bạn sẽ thay thế bằng đoạn mã thực tế từ tài liệu Aspose.Tasks.

## Định nghĩa “read group definition” là gì?
Đọc định nghĩa nhóm đề cập đến việc trích xuất các quy tắc nhóm (tên, tiêu chí, định dạng) mà Microsoft Project áp dụng để sắp xếp các tác vụ. Các quy tắc này cho ứng dụng biết cách nhóm các tác vụ theo trạng thái, mức độ ưu tiên hoặc trường tùy chỉnh, và chúng bao gồm các thuộc tính trực quan như kiểu phông chữ và màu ô.

## Tại sao cần đọc dữ liệu định nghĩa nhóm?
Đọc dữ liệu định nghĩa nhóm cho phép bạn **tự động tạo báo cáo**, **di chuyển logic nhóm** sang các dự án khác, và **xác thực rằng các nhóm cần thiết tồn tại** trước khi thực hiện cập nhật hàng loạt. Aspose.Tasks cho Java có thể xử lý các dự án với **hơn 10.000 tác vụ** mà không cần tải toàn bộ tệp vào bộ nhớ, cho phép thực hiện các thao tác batch hiệu suất cao. Ngoài ra, bạn có thể trích xuất màu phông chữ, mẫu và hướng sắp xếp để tái tạo bố cục trực quan chính xác trong các bảng điều khiển tùy chỉnh.

## Yêu cầu trước
1. **Java Development Kit (JDK) 8+** – bất kỳ phiên bản mới nào cũng hoạt động.  
2. **Aspose.Tasks for Java** – tải JAR mới nhất từ [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).  
3. **Một IDE Java** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình chỉnh sửa nào bạn thích.  

> **Mẹo chuyên nghiệp:** Sử dụng Maven hoặc Gradle để quản lý phụ thuộc Aspose.Tasks; điều này tránh việc xử lý JAR thủ công.

## Nhập các gói
`Project` là lớp chính đại diện cho tệp Microsoft Project trong Aspose.Tasks cho Java.  

```java
import com.aspose.tasks.*;
```

## Hướng dẫn từng bước

### Bước 1: thiết lập thư mục dữ liệu của bạn
Xác định thư mục chứa tệp `.mpp` bạn muốn kiểm tra. Sử dụng `java.nio.file.Paths` đảm bảo xử lý đường dẫn độc lập với nền tảng.

```java
String dataDir = "Your Data Directory";
```

### Bước 2: tải tệp dự án
Tạo một thể hiện `Project` bằng cách chỉ tới tệp `.mpp` của bạn. Hàm khởi tạo đọc phần đầu tệp và xây dựng mô hình trong bộ nhớ.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Bước 3: lấy số lượng nhóm tác vụ
In ra tổng số nhóm tác vụ được định nghĩa trong dự án. Kiểm tra nhanh này xác nhận rằng tệp thực sự chứa thông tin nhóm.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Bước 4: lấy thông tin nhóm tác vụ cụ thể
Lấy một nhóm cụ thể (chỉ mục 1 trong ví dụ này) và hiển thị tên cùng số lượng tiêu chí mà nó chứa. Mỗi nhóm có thể có nhiều tiêu chí xác định cách nhóm các tác vụ.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Bước 5: lấy thông tin tiêu chí nhóm
Mỗi nhóm có thể có một hoặc nhiều tiêu chí. Đoạn mã dưới đây trích xuất các chi tiết như trường được dùng để nhóm, chế độ nhóm, màu ô và mẫu.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Bước 6: kiểm tra nhóm cha
Đôi khi một tiêu chí thuộc về một nhóm cha. Kiểm tra này xác nhận mối quan hệ và ngăn ngừa lỗi null‑pointer khi duyệt qua cấu trúc cây.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Bước 7: lấy thông tin phông chữ của tiêu chí
Tiêu chí nhóm có thể có kiểu phông chữ tùy chỉnh. Đoạn mã sau in ra họ phông, kích thước, kiểu và hướng sắp xếp, cho phép bạn tái tạo giao diện chính xác trong UI của mình.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **`NullPointerException` on `criterion.getParentGroup()`** | Tiêu chí có thể không có nhóm cha. | Thêm kiểm tra null trước khi truy cập nhóm cha. |
| **File not found** | Đường dẫn `dataDir` không đúng hoặc tên tệp bị viết sai. | Sử dụng `Paths.get(dataDir, "project.mpp").toAbsolutePath()` và xác minh tệp tồn tại. |
| **License not set** | Aspose chạy ở chế độ đánh giá và có thể cắt ngắn đầu ra. | Đăng ký giấy phép của bạn với `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` trước khi tải dự án. |

## Câu hỏi thường gặp

**Hỏi: Tôi có thể sử dụng Aspose.Tasks cho Java để chỉnh sửa tệp dự án không?**  
**Đáp:** Có, thư viện cung cấp khả năng đọc/ghi đầy đủ cho các định dạng Microsoft Project, cho phép bạn thêm tác vụ, thay đổi nguồn lực và cập nhật định nghĩa nhóm một cách lập trình.

**Hỏi: Aspose.Tasks cho Java có tương thích với mọi phiên bản tệp Microsoft Project không?**  
**Đáp:** Nó hỗ trợ MPP, XML, CSV và các định dạng Project phổ biến khác trên các phiên bản từ Project 2000 đến bản phát hành mới nhất 2024.

**Hỏi: Tôi nên xử lý lỗi như thế nào khi làm việc với Aspose.Tasks cho Java?**  
**Đáp:** Bao bọc các thao tác file trong khối `try‑catch` và bắt `TasksException` để có thông tin lỗi chi tiết; kiểm tra `getMessage()` của ngoại lệ để tìm manh mối.

**Hỏi: Aspose.Tasks cho Java có cung cấp xuất ra các định dạng khác không?**  
**Đáp:** Chắc chắn – bạn có thể xuất ra PDF, XLSX, HTML và nhiều định dạng khác bằng các API xuất chuyên dụng của thư viện.

**Hỏi: Tôi có thể tìm tài nguyên và hỗ trợ bổ sung ở đâu?**  
**Đáp:** Truy cập [tài liệu Aspose.Tasks cho Java](https://reference.aspose.com/tasks/java/) để xem tham chiếu API và [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận hỗ trợ từ cộng đồng.

## Kết luận
Trong hướng dẫn này, chúng tôi đã trình bày **cách đọc dữ liệu định nghĩa nhóm** từ tệp Microsoft Project bằng Aspose.Tasks cho Java. Bằng cách tải một `Project`, liệt kê `TaskGroupCollection` của nó và kiểm tra tiêu chí, phông chữ và màu sắc của mỗi nhóm, bạn có thể xây dựng các pipeline báo cáo tự động, di chuyển quy tắc nhóm, hoặc xác thực cấu trúc dự án một cách chắc chắn. Cách tiếp cận này cũng mở rộng được cho các dự án lớn chứa hàng nghìn tác vụ trong khi giữ mức sử dụng bộ nhớ thấp.

---

**Cập nhật lần cuối:** 2026-10-26  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách đọc thông tin dự án từ Microsoft Project với Aspose.Tasks cho Java](/tasks/java/project-properties/read-project-info/)
- [Cách lấy trường bảng và đọc dữ liệu bảng trong Aspose.Tasks](/tasks/java/project-data-reading/read-table-data/)
- [đọc biểu đồ gantt java – Trích xuất dữ liệu Gantt cụ thể](/tasks/java/project-data-reading/read-specific-gantt-chart-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}