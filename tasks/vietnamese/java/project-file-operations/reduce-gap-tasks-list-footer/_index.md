---
date: 2026-05-20
description: Tìm hiểu cách xuất dự án sang PDF, giảm khoảng cách chân trang và lưu
  dự án dưới dạng hình ảnh bằng Aspose.Tasks for Java. Tối ưu hoá bố cục MS Project
  của bạn một cách dễ dàng.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Xuất dự án sang PDF và giảm khoảng cách giữa danh sách công việc và chân
  trang trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Xuất dự án sang PDF và giảm khoảng cách giữa danh sách công việc và chân trang
  trong Aspose.Tasks
url: /vi/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xuất Dự Án sang PDF và Giảm Khoảng Cách Giữa Danh Sách Nhiệm Vụ và Chân Trang trong Aspose.Tasks

## Giới thiệu  
Trong hướng dẫn này, bạn sẽ khám phá **cách xuất dự án sang PDF** đồng thời giảm khoảng trống không mong muốn giữa danh sách nhiệm vụ và chân trang trong các tệp Microsoft Project. Khi kết thúc hướng dẫn, bạn sẽ có thể tạo ra các tệp PDF sạch sẽ, hình ảnh PNG và các trang HTML với bố cục gọn gàng bằng cách sử dụng Aspose.Tasks cho Java. Hãy cùng đi qua quy trình từng bước, và bạn sẽ thấy tại sao điều này quan trọng đối với việc báo cáo chuyên nghiệp.

## Câu trả lời nhanh  
- **Ý nghĩa của “export project to PDF” là gì?** Nó chuyển đổi tệp MPP thành tài liệu PDF, giữ nguyên các nhiệm vụ, thời gian biểu và định dạng.  
- **Tại sao giảm khoảng cách chân trang?** Khoảng cách nhỏ hơn tạo ra các báo cáo gọn gàng, chuyên nghiệp hơn, đặc biệt đối với tài liệu in hoặc xem trên web.  
- **Tôi có thể lưu dự án dưới dạng hình ảnh không?** Có – Aspose.Tasks hỗ trợ PNG, JPEG và các định dạng hình ảnh khác.  
- **Tôi có cần giấy phép đặc biệt không?** Có sẵn bản dùng thử miễn phí; giấy phép thương mại là bắt buộc cho việc sử dụng trong môi trường sản xuất.  
- **Phiên bản Java nào được yêu cầu?** Java 8 hoặc cao hơn hoạt động với thư viện Aspose.Tasks hiện tại.  

## “export project to PDF” là gì?  
Xuất dự án sang PDF chuyển đổi cấu trúc MPP nội bộ thành một tài liệu di động có thể mở trên bất kỳ thiết bị nào mà không cần Microsoft Project. Điều này lý tưởng cho việc chia sẻ báo cáo trạng thái, cập nhật cho các bên liên quan, hoặc lưu trữ kế hoạch dự án. Nó giữ nguyên bố cục, màu sắc và cấu trúc nhiệm vụ gốc, đảm bảo PDF trông giống hệt tệp nguồn.

## Tại sao giảm khoảng cách chân trang?  
Khoảng cách chân trang mặc định có thể tạo ra không gian trắng không cần thiết, gây ra vấn đề phân trang và giao diện không cân đối. Giảm khoảng cách này đảm bảo nội dung của bạn sử dụng trang một cách hiệu quả, làm cho PDF hoặc hình ảnh cuối cùng dễ đọc hơn. Bố cục gọn hơn cũng giảm tổng số trang, có thể giảm chi phí in ấn và cải thiện việc điều hướng trên màn hình.

## Cách giảm khoảng cách giữa danh sách nhiệm vụ và chân trang?  
`setReduceFooterGap` là một thuộc tính Boolean kiểm soát khoảng cách chân trang khi xuất.  
Aspose.Tasks cung cấp tùy chọn `setReduceFooterGap(true)` cho các thao tác lưu hình ảnh, PDF và HTML. Bật cờ này sẽ yêu cầu engine nén không gian giữa hàng nhiệm vụ cuối cùng và chân trang. Khi đặt thành true, trình render tự động cắt giảm lề mà không làm mất dữ liệu nhiệm vụ, tạo ra bố cục trang sạch sẽ hơn.

## Lưu Dự Án dưới dạng Hình ảnh với Aspose.Tasks  
`ImageSaveOptions` cấu hình cách dự án được render thành tệp hình ảnh.  
Lớp `ImageSaveOptions` cho phép bạn xuất một ảnh chụp nhanh lịch trình dưới dạng PNG, JPEG hoặc BMP. Khi bạn cũng bật `setReduceFooterGap(true)`, hình ảnh được tạo ra sẽ phản ánh bố cục PDF gọn gàng, cung cấp cho bạn một hình ảnh sạch sẽ cho các bài thuyết trình hoặc bảng điều khiển.

## Xuất Dự Án Java sang PDF  
Các phần sau đây hướng dẫn quy trình **java project export** hoàn chỉnh, từ việc tải tệp MPP đến lưu nó dưới ba định dạng khác nhau.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có các yêu cầu sau:
1. Java Development Kit (JDK) – phiên bản 8 hoặc cao hơn.  
2. Thư viện Aspose.Tasks cho Java – tải xuống từ [here](https://releases.aspose.com/tasks/java/).  

## Nhập các Gói  
Before diving into the coding part, let's import the necessary packages:

```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Bước 1: Cung cấp Đường dẫn tới Thư mục Dữ liệu của Bạn  
```java
String dataDir = "Your Data Directory";
```  
Đảm bảo thay thế `"Your Data Directory"` bằng đường dẫn tới thư mục dữ liệu thực tế của bạn, nơi chứa tệp Microsoft Project (`HomeMovePlan.mpp` trong ví dụ này).

## Bước 2: Đọc tệp MPP  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Dòng mã này đọc tệp Microsoft Project có tên `HomeMovePlan.mpp`.

## Bước 3: Đặt ImageSaveOptions (Lưu Dự Án dưới dạng Hình ảnh)  
`ImageSaveOptions` cấu hình cách dự án được render thành tệp hình ảnh.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Cấu hình các tùy chọn lưu hình ảnh, đặt `ReduceFooterGap` thành `true` để giảm khoảng cách giữa danh sách nhiệm vụ và chân trang.

## Bước 4: Lưu dưới dạng Hình ảnh  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Lưu dự án dưới dạng hình ảnh với các tùy chọn đã cấu hình.

## Bước 5: Đặt PdfSaveOptions (Xuất Dự Án sang PDF)  
`PdfSaveOptions` chỉ định các cài đặt cho việc xuất dự án sang định dạng PDF.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Xác định các tùy chọn lưu PDF, đảm bảo đặt `ReduceFooterGap` thành `true`.

## Bước 6: Lưu dưới dạng PDF  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Lưu dự án dưới dạng PDF với các tùy chọn đã cấu hình.

## Bước 7: Đặt HtmlSaveOptions  
`HtmlSaveOptions` kiểm soát việc chuyển đổi dự án sang HTML, bao gồm các tùy chọn về kiểu dáng và bố cục.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
Chỉ định các tùy chọn lưu HTML, đặt `ReduceFooterGap` thành `true`.

## Bước 8: Lưu dưới dạng HTML  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
Lưu dự án dưới dạng tệp HTML với các tùy chọn đã cấu hình.

## Các Trường hợp Sử dụng Thông thường và Mẹo
- **Báo cáo cho các bên liên quan:** Xuất sang PDF với khoảng cách chân trang giảm để giữ báo cáo ngắn gọn và thân thiện với máy in.  
- **Ảnh chụp nhanh Dashboard:** Sử dụng xuất hình ảnh khi bạn cần một hình ảnh nhanh cho Power BI hoặc Confluence.  
- **Xuất bản web:** Xuất HTML giữ lại tính tương tác và có thể nhúng trực tiếp vào các cổng intranet.  
- **Mẹo chuyên nghiệp:** Đối với các dự án rất lớn, tăng `Resolution` trong `ImageSaveOptions` lên 300 dpi để duy trì độ rõ nét trong khi vẫn hưởng lợi từ khoảng cách giảm.

## Câu hỏi thường gặp (Bổ sung)

**Q: Giảm khoảng cách chân trang ảnh hưởng như thế nào đến việc phân trang?**  
A: Nó giảm thiểu không gian trống ở cuối mỗi trang, cho phép nhiều nhiệm vụ hơn nằm trên một trang và giảm tổng số trang.

**Q: Tôi có thể áp dụng cài đặt giảm khoảng cách này chỉ cho một trang duy nhất không?**  
A: Có, bằng cách đặt `setRenderToSinglePage(true)` trong `ImageSaveOptions` bạn có thể kiểm soát việc phân trang đồng thời vẫn giảm khoảng cách.

**Q: Tùy chọn `setReduceFooterGap` có sẵn cho các định dạng xuất khác không?**  
A: Hiện tại nó được hỗ trợ cho xuất PNG, PDF và HTML. Đối với các định dạng khác, bạn có thể cần điều chỉnh bố cục thủ công.

**Q: Nếu dự án của tôi chứa các trường tùy chỉnh—các trường này có được giữ lại không?**  
A: Tất cả các trường tùy chỉnh được giữ lại trong quá trình xuất; các điều chỉnh bố cục chỉ ảnh hưởng đến khoảng cách, không ảnh hưởng đến dữ liệu.

**Q: Thư viện có xử lý các dự án lớn một cách hiệu quả không?**  
A: Aspose.Tasks truyền dữ liệu theo luồng và có thể xử lý các tệp MPP hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ; tuy nhiên, hãy cấp phát đủ không gian heap khi xuất hình ảnh độ phân giải cao.

---

**Cập nhật lần cuối:** 2026-05-20  
**Kiểm tra với:** Aspose.Tasks 24.11 for Java  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Lưu Dự Án dưới dạng Hình ảnh – Định dạng 24bppRgb với Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Lưu Dự Án dưới dạng Mẫu, CSV và Văn bản với Aspose.Tasks cho Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Cách Tạo Tệp MPP – Tạo & Lưu Dự Án Trống ở Định dạng MPP với Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}