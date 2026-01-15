---
date: 2026-01-15
description: Tìm hiểu cách lưu dự án dưới dạng PDF và hiển thị các chế độ xem Resource
  Usage và Sheet của MS Project bằng Aspose.Tasks cho Java. Hãy làm theo hướng dẫn
  từng bước của chúng tôi để xuất dự án sang PDF một cách dễ dàng.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lưu dự án dưới dạng PDF – Hiển thị việc sử dụng tài nguyên và chế độ xem bảng
  trong Aspose.Tasks
url: /vi/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu Dự Án dưới dạng PDF – Kết xuất chế độ Xem Sử Dụng Tài Nguyên và Bảng trong Aspose.Tasks

## Introduction
Trong hướng dẫn này, bạn sẽ khám phá cách **lưu dự án dưới dạng PDF** trong khi kết xuất các chế độ Xem Sử Dụng Tài Nguyên và Bảng của một tệp Microsoft Project. Cho dù bạn cần tạo báo cáo có thể in cho các bên liên quan hoặc chuyển đổi tệp MPP sang định dạng có thể xem được trên mọi nền tảng, Aspose.Tasks for Java giúp quá trình này trở nên đơn giản—không cần cài đặt Microsoft Project.

## Quick Answers
- **save project as pdf** làm gì? Nó chuyển đổi tệp Project (MPP) thành tài liệu PDF, giữ nguyên chế độ xem đã chọn.  
- **Chế độ xem nào có thể xuất?** Resource Usage, Sheet, Gantt, Task Usage, và các chế độ khác.  
- **Tôi có thể thay đổi thang thời gian trong PDF không?** Có—các tùy chọn bao gồm Days, ThirdsOfMonths và Months.  
- **Có cần cài đặt Microsoft Project không?** Không, Aspose.Tasks hoạt động độc lập.  
- **Cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại cho việc sử dụng không phải thử nghiệm.

## What is “save project as PDF”?
Lưu dự án dưới dạng PDF tạo ra một bản đại diện tĩnh, độ phân giải cao của một chế độ xem Project đã chọn. Điều này lý tưởng để chia sẻ với khách hàng, lưu trữ, hoặc in mà không tiết lộ tệp dự án gốc.

## Why use Aspose.Tasks to export project to PDF?
- **Không phụ thuộc vào bên ngoài** – hoạt động trên bất kỳ nền tảng nào hỗ trợ Java.  
- **Kiểm soát chi tiết** – bạn có thể chọn chế độ xem, thang thời gian và bố cục.  
- **Độ trung thực cao** – PDF phản ánh chính xác giao diện của chế độ xem Project gốc.  
- **Sẵn sàng tự động hoá** – tích hợp vào pipeline CI, dịch vụ báo cáo, hoặc bộ chuyển đổi hàng loạt.

## Prerequisites
1. **Java Development Kit (JDK)** – khuyến nghị sử dụng phiên bản mới nhất.  
2. **Aspose.Tasks for Java** – tải xuống từ [download page](https://releases.aspose.com/tasks/java/).

## Import Packages
First, import the necessary classes into your Java project:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Step‑by‑Step Guide

### Step 1: Read the Source Project
Tải tệp MPP bạn muốn chuyển đổi.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Step 2: Define SaveOptions with Required Timescale (Export Project to PDF)
Cấu hình các tùy chọn xuất PDF và đặt thang thời gian mong muốn. *Ở đây chúng tôi sử dụng **Days** làm ví dụ.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Step 3: Set the Presentation Format to ResourceUsage
Chọn chế độ xem bạn muốn kết xuất. Trong trường hợp này là chế độ **Resource Usage**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Step 4: Save the Project (Convert MPP to PDF)
Thực hiện chuyển đổi và tạo tệp PDF.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Step 5: Render Views for Other Timescale Settings (Change Timescale PDF)
Lặp lại các bước trước để tạo PDF với các thang thời gian khác nhau như **ThirdsOfMonths** và **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Common Issues and Solutions
- **Lỗi không tìm thấy tệp** – Kiểm tra `dataDir` trỏ tới thư mục đúng và tên tệp MPP khớp chính xác.  
- **Kết quả PDF trống** – Đảm bảo `PresentationFormat` khớp với chế độ xem có dữ liệu (ví dụ: ResourceUsage).  
- **Thang thời gian không đúng** – Kiểm tra lại rằng `options.setTimescale()` được gọi trước mỗi lần `project.save()`.

## Frequently Asked Questions

### Aspose.Tasks có thể kết xuất các chế độ xem khác ngoài Resource Usage và Sheet không?
Aspose.Tasks hỗ trợ kết xuất nhiều chế độ xem như Gantt Chart, Task Usage, và Calendar, trong số các chế độ khác.

### Aspose.Tasks có tương thích với các phiên bản tệp Microsoft Project khác nhau không?
Có, Aspose.Tasks hỗ trợ đa dạng định dạng tệp Microsoft Project, bao gồm MPP, MPT và các định dạng XML.

### Tôi có thể tùy chỉnh giao diện của các chế độ xem đã kết xuất bằng Aspose.Tasks không?
Chắc chắn! Aspose.Tasks cung cấp nhiều tùy chọn để tùy chỉnh giao diện và bố cục của các chế độ xem đã kết xuất theo yêu cầu của bạn.

### Aspose.Tasks có yêu cầu cài đặt Microsoft Project trên hệ thống không?
Không, Aspose.Tasks là thư viện độc lập và không cần cài đặt Microsoft Project để hoạt động.

### Có hỗ trợ kỹ thuật cho người dùng Aspose.Tasks không?
Có, người dùng Aspose.Tasks có thể nhận hỗ trợ kỹ thuật qua [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-01-15  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose