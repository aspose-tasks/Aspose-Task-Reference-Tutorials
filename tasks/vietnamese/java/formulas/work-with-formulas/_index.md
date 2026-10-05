---
date: 2026-10-05
description: Tìm hiểu cách tạo dự án thử nghiệm và tính số ngày giữa các ngày bằng
  Aspose.Tasks cho Java, thêm một custom field, và thao tác các tệp MPP một cách hiệu
  quả.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Làm việc với formulas trong Aspose.Tasks
og_description: Tạo dự án thử nghiệm và tính số ngày giữa các ngày bằng Aspose.Tasks
  cho Java. Hướng dẫn này cho thấy cách thêm một custom field, đặt task deadlines,
  và lưu dự án dưới dạng tệp MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Tạo dự án thử nghiệm và tính số ngày giữa các ngày
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Tạo dự án thử nghiệm và tính số ngày giữa các ngày
url: /vi/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo dự án thử nghiệm và tính số ngày giữa các ngày

Trong hướng dẫn này, bạn sẽ **tạo dự án thử nghiệm** và **tính số ngày giữa các ngày** bằng cách thêm một trường tùy chỉnh, định nghĩa một thuộc tính mở rộng, và áp dụng công thức Microsoft Project thông qua thư viện Aspose.Tasks cho Java. Cho dù bạn cần tạo lịch trình, tính thời hạn, hoặc tự động hoá báo cáo, Aspose.Tasks cho phép bạn thao tác dữ liệu Project một cách lập trình mà không cần cài đặt trên máy tính để bàn, hỗ trợ hơn 50 định dạng nhập và xuất và xử lý các tệp hàng trăm trang trong chế độ tiết kiệm bộ nhớ.

## Câu trả lời nhanh
- **Nội dung hướng dẫn?** Nó cho thấy cách tạo một dự án thử nghiệm, định nghĩa một thuộc tính mở rộng, đặt thời hạn cho một nhiệm vụ, và sử dụng công thức để tính số ngày giữa các ngày.  
- **Thư viện nào được yêu cầu?** Aspose.Tasks for Java (phiên bản mới nhất).  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại là bắt buộc cho việc sử dụng trong môi trường sản xuất.  
- **IDE nào tôi có thể sử dụng?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, VS Code) hỗ trợ JDK 8+.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút để sao chép mã và chạy nó.

## “calculate days between dates” là gì trong Aspose.Tasks?
Trong Aspose.Tasks, công thức là một chuỗi có thể tham chiếu đến các trường nhiệm vụ và thực hiện các phép tính. `[Deadline] - [Finish]` là cú pháp công thức mà Aspose.Tasks sử dụng để trả về sự chênh lệch số ngày giữa hai trường ngày. Kết quả được lưu dưới dạng giá trị số đại diện cho số ngày nguyên, bạn có thể hiển thị trong một trường tùy chỉnh hoặc sử dụng trong các phép tính tiếp theo.

## Tại sao nên dùng Aspose.Tasks để tính số ngày giữa các ngày?
Aspose.Tasks cung cấp **độ bao phủ API đầy đủ** cho mọi thuộc tính của Project, Task và Resource, chạy trên Windows, Linux và macOS, và **không yêu cầu cài đặt Microsoft Project hoặc Office**. Động cơ có thể xử lý các dự án với **hơn 500 nhiệm vụ** trong vòng chưa đầy một giây trên phần cứng máy chủ tiêu chuẩn, làm cho nó trở thành lựa chọn lý tưởng cho các pipeline CI, container Docker, và xử lý hàng loạt với khối lượng lớn.

## Cách đặt thời hạn cho một nhiệm vụ
`java.util.Calendar` là một lớp Java đại diện cho một thời điểm cụ thể. Bạn đặt thời hạn bằng cách gán giá trị `java.util.Calendar` cho trường `Tsk.DEADLINE` của một nhiệm vụ. Sau khi tạo thể hiện Calendar, đặt năm, tháng và ngày thành thời hạn mong muốn, sau đó gọi `task.set(Tsk.DEADLINE, calendar);`. Thời hạn được lưu trong tệp dự án và có thể được sử dụng trong các công thức như `[Deadline] - [Finish]`.

## Cách định nghĩa thuộc tính mở rộng
Một thuộc tính mở rộng là một trường tùy chỉnh lưu trữ kết quả của công thức của bạn. Bạn tạo nó một lần, đặt một bí danh thân thiện, và gắn biểu thức `[Deadline] - [Finish]` để mỗi nhiệm vụ có thể tự động tính khoảng thời gian. Tạo nó bằng cách khởi tạo `ExtendedAttribute`, đặt Alias, gán công thức, và thêm vào bộ sưu tập của dự án.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn có những thứ sau:

- **Java Development Kit (JDK) 8+** – tải xuống từ trang web Oracle hoặc sử dụng OpenJDK.  
- **Aspose.Tasks for Java** – lấy JAR mới nhất từ [trang tải xuống Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) và thêm vào classpath của dự án hoặc các phụ thuộc Maven/Gradle.

## Nhập các gói
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Hướng dẫn từng bước

### Bước 1: Tạo dự án thử nghiệm với trường tùy chỉnh
Chúng ta bắt đầu bằng cách **tạo một dự án thử nghiệm** và thêm một trường tùy chỉnh sẽ sau này chứa kết quả công thức của chúng ta.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Mẹo chuyên nghiệp:* `CreateTestProjectWithCustomField()` là một phương thức trợ giúp tạo lịch tối thiểu và đăng ký một thuộc tính mở rộng sẵn sàng cho việc gán công thức.

### Bước 2: Định nghĩa một thuộc tính mở rộng (thêm trường tùy chỉnh)
Tiếp theo, chúng ta **định nghĩa một thuộc tính mở rộng** – thực chất là trường tùy chỉnh – và đặt cho nó một bí danh thân thiện. Đây là nơi chúng ta **thêm logic trường tùy chỉnh**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** làm cho trường dễ đọc trong Project.  
- **Formula** tính số ngày giữa ngày *Finish* của một nhiệm vụ và *Deadline* của nó – cốt lõi của *calculate days between dates*.

### Bước 3: Đặt thời hạn cho một nhiệm vụ (thêm nhiệm vụ thời hạn & đặt thời hạn nhiệm vụ)
Bây giờ chúng ta **thêm dữ liệu nhiệm vụ thời hạn** bằng cách đặt thuộc tính *Deadline* cho một nhiệm vụ cụ thể.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Thể hiện `Calendar` xác định chính xác thời điểm thời hạn.  
- `set(Tsk.DEADLINE, …)` **đặt thời hạn cho nhiệm vụ** đã chọn.

### Bước 4: Lưu dự án (xử lý tệp Microsoft Project)
Cuối cùng, chúng ta **xử lý Microsoft Project** bằng cách lưu các thay đổi vào tệp MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Bạn có thể mở `SaveFile.mpp` trong Microsoft Project để xem trường tùy chỉnh, kết quả công thức và thời hạn được phản ánh trong lịch trình.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Công thức không tính toán** | Đảm bảo chuỗi `Formula` của thuộc tính sử dụng đúng tên trường (ví dụ: `[Deadline]`, `[Finish]`). |
| **Không tìm thấy nhiệm vụ** | Kiểm tra ID nhiệm vụ (`1` trong ví dụ) có tồn tại; sử dụng `project.getRootTask().getChildren().size()` để gỡ lỗi. |
| **Lỗi giấy phép** | Áp dụng giấy phép Aspose.Tasks hợp lệ trước khi gọi bất kỳ phương thức API nào (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
A: Có, Aspose.Tasks cung cấp API cho .NET, Java và các nền tảng khác, cho phép bạn thao tác các tệp Microsoft Project bằng ngôn ngữ bạn chọn.

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks không?**  
A: Chắc chắn. Tải bản dùng thử đầy đủ chức năng từ [trang tải xuống Aspose.Tasks](https://releases.aspose.com/).

**Q: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks ở đâu?**  
A: Tài liệu chính thức được lưu trữ tại [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Làm thế nào để tôi nhận được hỗ trợ cho Aspose.Tasks?**  
A: Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để đặt câu hỏi và chia sẻ kinh nghiệm với cộng đồng.

**Q: Tôi có cần giấy phép tạm thời để đánh giá không?**  
A: Giấy phép tạm thời có sẵn cho việc thử nghiệm ngắn hạn; bạn có thể yêu cầu từ [trang yêu cầu giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

**Cập nhật lần cuối:** 2026-10-05  
**Kiểm thử với:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tạo tệp MPP – Tạo & Lưu dự án trống ở định dạng MPP với Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Đặt ngày bắt đầu dự án trong MS Project bằng Aspose.Tasks cho Java](/tasks/java/project-properties/write-project-info/)
- [Cách tạo thuộc tính mở rộng trong Java với Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}