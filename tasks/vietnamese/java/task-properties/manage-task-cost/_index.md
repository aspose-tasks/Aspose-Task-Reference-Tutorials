---
date: 2026-02-20
description: Tìm hiểu cách tính biến động chi phí dự án và quản lý chi phí công việc
  trong Java bằng Aspose.Tasks. Hãy làm theo hướng dẫn từng bước của chúng tôi để
  thiết lập chi phí và kiểm soát ngân sách.
linktitle: Manage Task Costs in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tính Độ Chênh Lệch Chi Phí Dự Án bằng Aspose.Tasks cho Java
url: /vi/java/task-properties/manage-task-cost/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tính toán chênh lệch chi phí dự án với Aspose.Tasks

## Introduction
Trong hướng dẫn toàn diện này, bạn sẽ khám phá **cách tính toán chênh lệch chi phí dự án** và quản lý chi phí nhiệm vụ một cách hiệu quả trong các ứng dụng Java của bạn với Aspose.Tasks. Dù bạn đang theo dõi một dự án nội bộ nhỏ hay một triển khai doanh nghiệp quy mô lớn, việc hiểu chênh lệch chi phí giúp bạn giữ ngân sách đúng hướng và phát hiện sớm các khoản vượt quá.

## Quick Answers
- **What is cost variance?** Sự khác biệt giữa chi phí dự kiến (cố định) và chi phí thực tế (còn lại).  
- **Which API method sets a task’s cost?** `task.set(Tsk.COST, BigDecimal.valueOf(...))`.  
- **Do I need a license for development?** Bản dùng thử miễn phí đủ cho việc kiểm tra; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Can I retrieve project‑level cost data?** Có, bằng cách truy cập các thuộc tính chi phí của nhiệm vụ gốc.  
- **What Java version is supported?** Aspose.Tasks hoạt động với Java 8 và các phiên bản mới hơn.

## What is “calculate project cost variance”?
Việc tính toán chênh lệch chi phí dự án có nghĩa là so sánh **chi phí cố định** mà bạn đã lên kế hoạch ban đầu cho một nhiệm vụ hoặc dự án với **chi phí còn lại** phản ánh công việc chưa hoàn thành. Chênh lệch này cho bạn biết liệu bạn đang dưới hay vượt ngân sách, cho phép thực hiện các điều chỉnh chủ động.

## Why use Aspose.Tasks to calculate project cost variance?
- **Full .NET‑free Java API** – không cần thư viện gốc.  
- **Rich cost‑management properties** (`COST`, `FIXED_COST`, `REMAINING_COST`, `COST_VARIANCE`).  
- **Easy integration** với các dự án Maven/Gradle hiện có.  
- **Accurate reporting** có thể xuất ra các tệp MS Project®.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Java Development Kit (JDK)** – đã cài đặt Java 8 hoặc mới hơn.  
2. **Aspose.Tasks for Java library** – tải xuống từ trang chính thức **[here](https://releases.aspose.com/tasks/java/)**.  
3. Một IDE hoặc công cụ xây dựng (IntelliJ, Eclipse, Maven, Gradle) để biên dịch và chạy mã mẫu.

## Import Packages
Thêm các lớp Aspose.Tasks cần thiết vào tệp nguồn Java của bạn để có thể làm việc với dự án và nhiệm vụ.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Import Aspose.Tasks classes
```

## Step‑by‑Step Guide

### Step 1: Set up Your Project
Đầu tiên, tạo một thể hiện `Project` mới và chỉ đến thư mục nơi bạn có thể lưu các tệp được tạo.

```java
// Set the path to your document directory
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project();
```

### Step 2: Add a New Task
Thêm một nhiệm vụ dưới nhiệm vụ gốc. Đây là nơi chúng ta sẽ gán chi phí.

```java
// Add a new task to the root task
Task task = project.getRootTask().getChildren().add("Task");
```

### Step 3: Set Task Cost – **how to set cost**
Gán một chi phí dự kiến cho nhiệm vụ. Trong thực tế, chi phí này có thể lấy từ bảng tính ngân sách.

```java
// Set the task cost to 800
task.set(Tsk.COST, BigDecimal.valueOf(800));
```

### Step 4: Retrieve and Display Cost Information – **how to manage costs**
Bây giờ chúng ta sẽ đọc lại các thuộc tính chi phí khác nhau, bao gồm chênh lệch chi phí đã được tính.

```java
// Retrieve and print task information
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// Retrieve and print project-level cost information
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```

**What you’ll see:**  
- `Remaining Cost` phản ánh công việc chưa hoàn thành.  
- `Fixed Cost` là mức cơ sở bạn đã đặt (800 trong ví dụ này).  
- `Cost Variance` được tính tự động là **Fixed – Remaining**.  
- Các giá trị tương tự cũng có sẵn ở mức dự án (nhiệm vụ gốc), cho phép bạn **tính toán chênh lệch chi phí dự án** cho tất cả các nhiệm vụ.

### Step 5: Repeat for Additional Tasks (Optional)
Nếu dự án của bạn có nhiều giai đoạn, lặp lại Các bước 2‑4 cho mỗi nhiệm vụ. Tổng hợp các chênh lệch riêng lẻ sẽ cho bạn chênh lệch chi phí dự án tổng thể.

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| `NullPointerException` when accessing task properties | Nhiệm vụ chưa được thêm vào cấu trúc dự án. | Đảm bảo bạn gọi `project.getRootTask().getChildren().add(...)` trước khi đặt chi phí. |
| Cost values appear as `0` | Sử dụng `int` thay vì `BigDecimal`. | Luôn sử dụng `BigDecimal.valueOf(...)` như trong ví dụ. |
| Unexpected variance (negative) | `REMAINING_COST` vượt quá `FIXED_COST`. | Xác minh rằng bạn cập nhật chi phí còn lại khi công việc tiến triển. |

## Frequently Asked Questions

**Q: Tôi có thể tìm tài liệu cho Aspose.Tasks cho Java ở đâu?**  
A: Bạn có thể truy cập tài liệu **[here](https://reference.aspose.com/tasks/java/)**.

**Q: Làm thế nào để tải xuống thư viện Aspose.Tasks cho Java?**  
A: Tải xuống thư viện **[here](https://releases.aspose.com/tasks/java/)**.

**Q: Tôi có thể mua Aspose.Tasks cho Java ở đâu?**  
A: Bạn có thể mua tại **[here](https://purchase.aspose.com/buy)**.

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể nhận bản dùng thử miễn phí **[here](https://releases.aspose.com/)**.

**Q: Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho Java ở đâu?**  
A: Truy cập diễn đàn hỗ trợ **[here](https://forum.aspose.com/c/tasks/15)**.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}