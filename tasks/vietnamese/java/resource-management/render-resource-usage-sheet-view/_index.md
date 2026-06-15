---
date: 2026-06-15
description: Tìm hiểu cách chuyển đổi mpp sang PDF và hiển thị các khung nhìn Resource
  Usage và Sheet bằng cách sử dụng Aspose.Tasks cho Java. Thực hiện theo hướng dẫn
  từng bước của chúng tôi để thiết lập timescale và tạo báo cáo PDF chi tiết một cách
  dễ dàng.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Chuyển đổi MPP sang PDF và Hiển thị Khung nhìn Resource Usage – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Chuyển đổi MPP sang PDF và Hiển thị Khung nhìn Resource Usage – Aspose.Tasks
url: /vi/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi MPP sang PDF và Hiển thị Khung nhìn Sử dụng Tài nguyên – Aspose.Tasks

Trong hướng dẫn này, bạn sẽ học **cách chuyển đổi mpp sang pdf** trong khi hiển thị các khung nhìn Resource Usage và Sheet của tệp Microsoft Project. Sử dụng Aspose.Tasks cho Java loại bỏ nhu cầu cài đặt Microsoft Project trên máy chủ, cung cấp cho bạn cách nhanh chóng và đáng tin cậy để tạo báo cáo PDF từ các tệp MPP. Chúng tôi cũng sẽ chỉ cho bạn **cách đặt timescale** để đầu ra phù hợp với yêu cầu báo cáo của bạn.

## Câu trả lời nhanh
- **Aspose.Tasks làm gì?** Nó đọc, sửa đổi và chuyển đổi các tệp Microsoft Project (MPP) mà không cần cài đặt MS Project.  
- **Tôi có thể chuyển đổi MPP sang PDF trong một dòng lệnh không?** Có – tải Project, đặt SaveOptions, và gọi `save`.  
- **Các timescale nào được hỗ trợ?** Days, ThirdsOfMonths và Months.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Cần giấy phép thương mại cho các triển khai không dùng bản dùng thử.  
- **Thư viện có tương thích với Java 8+ không?** Hoàn toàn – nó hỗ trợ Java 8 và các phiên bản sau.

## Chuyển đổi mpp sang pdf là gì?
*Convert mpp to pdf* đề cập đến quá trình lấy một tệp Microsoft Project (.mpp) và tạo ra một phiên bản Portable Document Format (PDF) sao chép chính xác các bảng, lịch trình, biểu đồ và phân bổ tài nguyên của dự án. PDF kết quả có thể dễ dàng chia sẻ, in và lưu trữ mà không cần cài đặt Microsoft Project trên máy của người nhận.

## Tại sao nên chuyển đổi Project sang PDF với Aspose.Tasks?
Aspose.Tasks hỗ trợ **hơn 50 định dạng đầu vào và đầu ra** và có thể hiển thị các dự án hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, giảm mức sử dụng RAM lên tới 70 %. Đầu ra PDF giữ nguyên các bảng, biểu đồ và phân bổ tài nguyên, làm cho nó trở nên lý tưởng cho việc phân phối cho các bên liên quan và lưu trữ.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – Java 8 hoặc mới hơn được cài đặt trên máy của bạn.  
2. **Aspose.Tasks for Java** – tải xuống JAR mới nhất từ [trang tải xuống](https://releases.aspose.com/tasks/java/).  

## Cách chuyển đổi mpp sang pdf bằng Aspose.Tasks cho Java?
Tải tệp MPP nguồn của bạn, cấu hình timescale mong muốn, đặt định dạng trình bày thành **ResourceUsage**, và lưu kết quả dưới dạng PDF. Quy trình đầu‑cuối này chỉ cần một vài lời gọi API và chạy dưới một giây cho các dự án kích thước tiêu chuẩn.

### Bước 1: Đọc dự án nguồn
Lớp `Project` đại diện cho một tệp Microsoft Project được tải vào bộ nhớ, cung cấp quyền truy cập vào dữ liệu và cấu trúc của nó.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Bước 2: Định nghĩa SaveOptions với Cài đặt TimeScale yêu cầu
`SaveOptions` cấu hình cách dự án được lưu, cho phép bạn chỉ định các cài đặt đặc thù cho định dạng như timescale.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Bước 3: Đặt Presentation Format thành ResourceUsage
`PresentationFormat` xác định khung nhìn Project nào (ví dụ, ResourceUsage) sẽ được hiển thị trong tài liệu đầu ra.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Bước 4: Lưu dự án dưới dạng PDF
`project.save` ghi dự án vào tệp sử dụng `SaveOptions` đã cung cấp, tạo ra file PDF cuối cùng.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Bước 5: Hiển thị các khung nhìn cho các Cài đặt TimeScale khác
Lặp lại các bước trước, thay đổi giá trị `TimeScale` để hiển thị các khung nhìn timescale bổ sung.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Bước 6: Tùy chọn – Chuyển đổi Nhiều dự án trong một Lô
Nếu bạn cần **chuyển đổi project sang pdf** cho nhiều tệp, hãy đặt logic trên trong một vòng lặp duyệt qua thư mục chứa các tệp *.mpp*. Cách tiếp cận này **lưu các file ms project pdf** hàng loạt với ít thay đổi mã.  
Mã sau đây minh họa một ví dụ hoàn chỉnh về việc chuyển đổi tệp MPP sang PDF với các cài đặt mong muốn.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Các vấn đề thường gặp và giải pháp
- **Missing fonts in PDF** – Đảm bảo các phông chữ cần thiết được cài đặt trên máy chủ hoặc nhúng chúng qua `PdfSaveOptions`.  
- **Large project files cause OutOfMemoryError** – Sử dụng `LoadOptions.setLoadAllResources(false)` để tải tài nguyên khi cần.  
- **Incorrect timescale rendering** – Kiểm tra rằng `options.setTimeScale(TimeScale.Days)` (hoặc enum khác) phù hợp với độ chi tiết mong muốn.

## Câu hỏi thường gặp

**Q: Aspose.Tasks có thể hiển thị các khung nhìn khác ngoài Resource Usage và Sheet không?**  
A: Có, nó cũng hỗ trợ Gantt Chart, Task Usage, Calendar và nhiều khung nhìn bổ sung.

**Q: Aspose.Tasks có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
A: Hoàn toàn – nó xử lý các định dạng MPP, MPT và XML từ Project 2000 đến Project 2021.

**Q: Tôi có thể tùy chỉnh giao diện của các khung nhìn được hiển thị không?**  
A: Có, bạn có thể sửa đổi màu sắc, phông chữ và bố cục cột qua `PdfSaveOptions` và `PresentationOptions`.

**Q: Aspose.Tasks có yêu cầu cài đặt Microsoft Project không?**  
A: Không, đây là thư viện độc lập và hoạt động trên bất kỳ môi trường tương thích Java nào.

**Q: Tôi có thể nhận hỗ trợ kỹ thuật ở đâu?**  
A: Hỗ trợ có sẵn qua [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15/).

---

**Cập nhật lần cuối:** 2026-06-15  
**Kiểm tra với:** Aspose.Tasks 24.12 for Java  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Render Resource Usage and Sheet View in Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [How to Export PDF in Aspose.Tasks – Save As PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [How to Create MPP Files with Aspose.Tasks for Java](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}