---
date: 2025-12-07
description: Tìm hiểu cách **tạo dự án thử nghiệm** và **thêm trường tùy chỉnh** khi
  thao tác với các tệp Microsoft Project bằng Aspose.Tasks cho Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tạo dự án thử nghiệm và sử dụng công thức với Aspose.Tasks cho Java
url: /vi/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Dự Án Kiểm Thử và Sử Dụng Công Thức với Aspose.Tasks cho Java

## Introduction
Trong hướng dẫn này, bạn sẽ **tạo các tệp dự án kiểm thử**, thêm một trường tùy chỉnh, và làm việc với các công thức MS Project bằng thư viện Aspose.Tasks cho Java. Aspose.Tasks giúp việc **điều khiển dữ liệu Microsoft Project** một cách lập trình trở nên đơn giản—cho dù bạn cần tạo lịch trình, tính toán ngày, hoặc tự động hoá báo cáo. Khi kết thúc hướng dẫn, bạn sẽ có một ví dụ có thể chạy được, định nghĩa một thuộc tính mở rộng, đặt thời hạn cho một nhiệm vụ, và lưu dự án dưới dạng tệp MPP.

## Quick Answers
- **Hướng dẫn bao gồm gì?** Tạo dự án kiểm thử, thêm trường tùy chỉnh, định nghĩa thuộc tính mở rộng, và đặt thời hạn cho nhiệm vụ bằng công thức.  
- **Thư viện nào cần thiết?** Aspose.Tasks cho Java (phiên bản mới nhất).  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; cần giấy phép cho môi trường sản xuất.  
- **IDE nào có thể dùng?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, VS Code) hỗ trợ JDK 8+.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút để sao chép mã và chạy.

## What is a “Test Project” in Aspose.Tasks?
Một **dự án kiểm thử** là một tệp Microsoft Project nhẹ được tạo lập trình để minh họa hoặc xác thực chức năng. Nó chứa một tập hợp tối thiểu các nhiệm vụ, nguồn lực và trường tùy chỉnh mà bạn có thể thao tác mà không ảnh hưởng đến dữ liệu dự án thực.

## Why Use Aspose.Tasks to Manipulate Microsoft Project?
- **Bao phủ đầy đủ API** – truy cập mọi thuộc tính của Project, Task và Resource.  
- **Không cần cài đặt Office** – hoạt động trên máy chủ, pipeline CI và container Docker.  
- **Đa nền tảng** – chạy trên Windows, Linux và macOS với cùng một mã Java.  
- **Công cụ công thức mạnh mẽ** – tính toán ngày, thời lượng và trường tùy chỉnh trực tiếp trong tệp dự án.

## Prerequisites
- **Java Development Kit (JDK) 8+** – tải xuống từ trang web Oracle hoặc sử dụng OpenJDK.  
- **Aspose.Tasks cho Java** – lấy JAR mới nhất từ [trang tải Aspose.Tasks cho Java](https://releases.aspose.com/tasks/java/) và thêm vào classpath của dự án hoặc phụ thuộc Maven/Gradle.

## Import Packages
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Test Project with a Custom Field
We begin by **creating test project** and adding a custom field that will later hold our formula result.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Mẹo chuyên nghiệp:*CreateTestProjectWithCustomField()` là một phương thức trợ giúp tạo lịch tối thiểu và đăng ký một thuộc tính mở rộng sẵn sàng cho việc gán công thức.

### Step 2: Define an Extended Attribute (Add Custom Field)
Next, we **define extended attribute** – essentially the custom field – and give it a friendly alias. This is where we **add custom field** logic.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** giúp trường hiển thị dễ đọc trong Project.  
- **Formula** tính số ngày giữa ngày *Finish* và *Deadline* của một nhiệm vụ.

### Step 3: Set Deadline for a Task (Add Deadline Task & Set Task Deadline)
Now we **add deadline task** data by setting the *Deadline* property on a specific task.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Đối tượng `Calendar` xác định thời điểm deadline chính xác.  
- `set(Tsk.DEADLINE, …)` **đặt deadline cho nhiệm vụ** đã chọn.

### Step 4: Save the Project (Manipulate Microsoft Project File)
Finally, we **manipulate Microsoft Project** by persisting the changes to an MPP file.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Bạn có thể mở `SaveFile.mpp` trong Microsoft Project để xem trường tùy chỉnh, kết quả công thức và deadline được phản ánh trong lịch trình.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Công thức không tính toán** | Đảm bảo chuỗi `Formula` của thuộc tính sử dụng đúng tên trường (ví dụ, `[Deadline]`, `[Finish]`). |
| **Không tìm thấy nhiệm vụ** | Xác minh ID nhiệm vụ (`1` trong ví dụ) tồn tại; sử dụng `project.getRootTask().getChildren().size()` để gỡ lỗi. |
| **Lỗi giấy phép** | Áp dụng giấy phép Aspose.Tasks hợp lệ trước khi gọi bất kỳ phương thức API nào (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently Asked Questions

**Q: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
A: Có, Aspose.Tasks cung cấp API cho .NET, Java và các nền tảng khác, cho phép bạn **điều khiển Microsoft Project** bằng ngôn ngữ bạn chọn.

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks không?**  
A: Tất nhiên. Tải bản dùng thử đầy đủ chức năng từ [trang tải Aspose.Tasks](https://releases.aspose.com/).

**Q: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks ở đâu?**  
A: Tài liệu chính thức được lưu trữ tại [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Tasks?**  
A: Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để đặt câu hỏi và chia sẻ kinh nghiệm với cộng đồng.

**Q: Tôi có cần giấy phép tạm thời để đánh giá không?**  
A: Giấy phép tạm thời có sẵn cho việc thử nghiệm ngắn hạn; bạn có thể yêu cầu tại [đây](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2025-12-07  
**Được kiểm tra với:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}