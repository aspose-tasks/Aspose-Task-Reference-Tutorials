---
date: 2026-02-26
description: Học cách lưu dự án dưới dạng PDF và tạo bảng công việc bằng Aspose.Tasks
  cho Java. Xuất MPP sang PDF nhanh chóng với hướng dẫn từng bước này.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lưu dự án dưới dạng PDF – Kết xuất bảng công việc với Aspose.Tasks cho Java
url: /vi/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu Dự Án dưới dạng PDF – Render Bảng Công Việc trong Aspose.Tasks

## Introduction
Trong hướng dẫn toàn diện này, bạn sẽ khám phá cách **lưu dự án dưới dạng PDF** và tạo một bảng công việc với Aspose.Tasks cho Java. Cho dù bạn cần xuất tệp MPP sang PDF để các bên liên quan xem xét hoặc chỉ đơn giản là tạo một bảng công việc sạch sẽ để báo cáo, hướng dẫn này sẽ hướng dẫn bạn qua từng bước, giải thích lý do mỗi thiết lập quan trọng, và hiển thị mã chính xác bạn cần chạy.

## Quick Answers
- **What does “save project as pdf” do?** Nó chuyển đổi tệp Microsoft Project (MPP) thành tài liệu PDF, tùy chọn định dạng dưới dạng bảng công việc.  
- **Which format is used for a task‑sheet PDF?** Tùy chọn `PresentationFormat.TaskSheet` trong `PdfSaveOptions`.  
- **Do I need a license to run the code?** Cần một giấy phép tạm thời hoặc đầy đủ cho môi trường sản xuất; bản dùng thử miễn phí hoạt động cho việc đánh giá.  
- **What are the main prerequisites?** Java JDK, thư viện Aspose.Tasks cho Java, và một tệp dự án hợp lệ (ví dụ, *.mpp).  
- **Can I customize the PDF layout?** Có, Aspose.Tasks cung cấp nhiều thuộc tính `PdfSaveOptions` để định dạng và thiết lập trang.

## What is “save project as pdf”?
Lưu dự án dưới dạng PDF chuyển đổi dữ liệu nội bộ của dự án thành một tài liệu di động, chỉ đọc. Điều này lý tưởng để chia sẻ lịch trình, bảng công việc hoặc báo cáo trạng thái với các bên liên quan không có Microsoft Project cài đặt.

## Why render a task sheet?
Bảng công việc hiển thị mỗi nhiệm vụ trong dạng bảng, cho thấy ID, tên, ngày bắt đầu/kết thúc và các trường khác. Việc render nó thành PDF đảm bảo định dạng nhất quán trên các nền tảng và dễ dàng in hoặc nhúng vào các tài liệu khác.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Java Development Kit (JDK)** – phiên bản mới nhất đã được cài đặt và `java`/`javac` có sẵn trong PATH của bạn.  
2. **Aspose.Tasks for Java** – tải thư viện từ trang chính thức [here](https://releases.aspose.com/tasks/java/).  
3. Một **project file** hợp lệ (`*.mpp`) mà bạn muốn chuyển đổi, ví dụ, `NewProductDev.mpp`.  

## Import Packages
Đầu tiên, nhập các lớp Aspose.Tasks cần thiết. Những import này cho phép bạn truy cập các tùy chọn lưu PDF, định dạng trình bày và đối tượng `Project` cốt lõi.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## Step‑by‑Step Guide

### Step 1: Set Your Document Directory
Xác định thư mục nơi tệp MPP nguồn nằm và nơi PDF được tạo ra sẽ được ghi. Sử dụng đường dẫn tuyệt đối hoặc tương đối đều được; chỉ cần đảm bảo thư mục tồn tại.

```java
String dataDir = "Your Document Directory";
```

### Step 2: Load the Project File
Tạo một thể hiện `Project` bằng cách tải tệp MPP hiện có. Đối tượng này đại diện cho toàn bộ cấu trúc dự án trong bộ nhớ.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### Step 3: Configure Save Options – Export MPP to PDF
Khởi tạo `PdfSaveOptions` và thông báo cho Aspose.Tasks rằng bạn muốn PDF được render dưới dạng **bảng công việc**. Đây là bước then chốt cho trường hợp sử dụng *export project pdf*.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### Step 4: Save the Project as a Task Sheet – Save Project as PDF
Gọi phương thức `save` trên đối tượng `Project`, truyền tên tệp đích và các tùy chọn đã cấu hình. Hành động này **chuyển đổi tệp MPP thành PDF** được định dạng dưới dạng bảng công việc.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### Step 5: Review the Result
Đi tới thư mục bạn đã chỉ định (`dataDir`). Bạn sẽ thấy `taskSheet.pdf` chứa danh sách các nhiệm vụ được định dạng gọn gàng. Mở nó bằng bất kỳ trình xem PDF nào để xác nhận việc chuyển đổi đã thành công.

## Common Issues and Solutions
- **FileNotFoundException** – Đảm bảo `dataDir` kết thúc bằng dấu phân cách đường dẫn (`/` hoặc `\\`) và tên tệp MPP là đúng.  
- **LicenseException** – Nếu bạn gặp lỗi giấy phép, áp dụng giấy phép tạm thời hoặc mua trước khi gọi bất kỳ API nào của Aspose.Tasks.  
- **Blank PDF** – Kiểm tra dự án thực sự có nhiệm vụ; dự án trống sẽ tạo PDF trống.

## Frequently Asked Questions

**Q: Is Aspose.Tasks compatible with all Java versions?**  
A: Có, Aspose.Tasks hoạt động với nhiều phiên bản Java. Xem [documentation](https://reference.aspose.com/tasks/java/) để biết chi tiết.

**Q: Can I try Aspose.Tasks before purchasing?**  
A: Chắc chắn! Khám phá phiên bản dùng thử miễn phí [here](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: Tham gia cộng đồng Aspose.Tasks trên [forum](https://forum.aspose.com/c/tasks/15) để được hỗ trợ và thảo luận.

**Q: How do I obtain a temporary license for Aspose.Tasks?**  
A: Nhận giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I purchase Aspose.Tasks for Java?**  
A: Mua Aspose.Tasks cho Java [here](https://purchase.aspose.com/buy).

## Conclusion
Bằng cách làm theo các bước này, bạn đã học cách **lưu dự án dưới dạng PDF**, cụ thể là render một bảng công việc, sử dụng Aspose.Tasks cho Java. Khả năng này cho phép bạn *export MPP to PDF* nhanh chóng, chia sẻ các bản sao dự án dễ đọc, và tích hợp dữ liệu dự án vào quy trình báo cáo rộng hơn.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}