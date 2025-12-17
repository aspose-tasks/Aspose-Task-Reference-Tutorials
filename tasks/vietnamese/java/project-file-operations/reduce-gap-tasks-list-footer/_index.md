---
date: 2025-12-17
description: Tìm hiểu cách xuất dự án sang PDF, giảm khoảng trống ở chân trang và
  lưu dự án dưới dạng hình ảnh bằng Aspose.Tasks cho Java. Tối ưu hoá bố cục MS Project
  của bạn một cách dễ dàng.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Xuất dự án sang PDF và giảm khoảng cách giữa danh sách nhiệm vụ và chân trang
  trong Aspose.Tasks
url: /vi/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xuất Dự Án sang PDF và Giảm Khoảng Cách Giữa Danh Sách Nhiệm Vụ và Chân Trang trong Aspose.Tasks

## Giới thiệu  
Trong hướng dẫn này, bạn sẽ khám phá **cách xuất dự án sang PDF** đồng thời giảm không gian không mong muốn giữa danh sách nhiệm vụ và chân trang trong các tệp Microsoft Project. Khi hoàn thành, bạn sẽ có thể tạo ra các tệp PDF sạch sẽ, hình ảnh PNG và các trang HTML với bố cục gọn gàng bằng Aspose.Tasks cho Java. Hãy cùng thực hiện từng bước một.

## Trả lời nhanh  
- **“Xuất dự án sang PDF” có nghĩa là gì?** Nó chuyển đổi tệp MPP thành tài liệu PDF, giữ nguyên các nhiệm vụ, thời gian và định dạng.  
- **Tại sao cần giảm khoảng cách chân trang?** Khoảng cách nhỏ hơn tạo ra các báo cáo chặt chẽ, chuyên nghiệp hơn, đặc biệt đối với tài liệu in hoặc xem trên web.  
- **Tôi có thể lưu dự án dưới dạng hình ảnh không?** Có – Aspose.Tasks hỗ trợ PNG, JPEG và các định dạng hình ảnh khác.  
- **Có cần giấy phép đặc biệt không?** Có phiên bản dùng thử miễn phí; giấy phép thương mại cần thiết cho việc sử dụng trong môi trường sản xuất.  
- **Yêu cầu phiên bản Java nào?** Java 8 hoặc cao hơn hoạt động tốt với thư viện Aspose.Tasks hiện tại.

## “Xuất dự án sang PDF” là gì?  
Việc xuất dự án sang PDF chuyển đổi cấu trúc nội bộ của tệp MPP thành một tài liệu di động có thể mở trên bất kỳ thiết bị nào mà không cần Microsoft Project. Điều này rất hữu ích để chia sẻ báo cáo trạng thái, cập nhật cho các bên liên quan hoặc lưu trữ kế hoạch dự án.

## Tại sao cần giảm khoảng cách chân trang?  
Khoảng cách chân trang mặc định có thể tạo ra không gian trắng không cần thiết, gây ra vấn đề phân trang và làm cho tài liệu trông không cân đối. Giảm khoảng cách này giúp nội dung sử dụng trang một cách hiệu quả hơn, làm cho PDF hoặc hình ảnh cuối cùng dễ đọc hơn.

## Cách giảm khoảng cách giữa danh sách nhiệm vụ và chân trang?  
Aspose.Tasks cung cấp tùy chọn `setReduceFooterGap(true)` cho các thao tác lưu dưới dạng hình ảnh, PDF và HTML. Bật cờ này sẽ yêu cầu engine nén không gian giữa hàng nhiệm vụ cuối cùng và chân trang.

## Lưu dự án dưới dạng hình ảnh với Aspose.Tasks  
Nếu bạn cần một ảnh chụp nhanh của lịch trình, có thể **lưu dự án dưới dạng hình ảnh** (PNG) đồng thời áp dụng cùng cài đặt giảm khoảng cách.

## Xuất dự án Java sang PDF  
Các phần sau sẽ hướng dẫn quy trình **xuất dự án Java** hoàn chỉnh, từ việc tải tệp MPP đến lưu dưới ba định dạng khác nhau.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn đã có:
1. Java Development Kit (JDK) – phiên bản 8 trở lên.  
2. Thư viện Aspose.Tasks cho Java – tải về từ [here](https://releases.aspose.com/tasks/java/).  

## Nhập gói
Trước khi viết mã, hãy nhập các gói cần thiết:
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

## Bước 1: Cung cấp đường dẫn tới thư mục dữ liệu của bạn
```java
String dataDir = "Your Data Directory";
```
Đảm bảo thay thế `"Your Data Directory"` bằng đường dẫn thực tế tới thư mục chứa tệp Microsoft Project (`HomeMovePlan.mpp` trong ví dụ này).

## Bước 2: Đọc tệp MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Dòng mã này đọc tệp Microsoft Project có tên `HomeMovePlan.mpp`.

## Bước 3: Đặt ImageSaveOptions (Lưu dự án dưới dạng hình ảnh)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Cấu hình các tùy chọn lưu hình ảnh, đặt `ReduceFooterGap` thành `true` để giảm khoảng cách giữa danh sách nhiệm vụ và chân trang.

## Bước 4: Lưu dưới dạng hình ảnh
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Lưu dự án dưới dạng hình ảnh với các tùy chọn đã cấu hình.

## Bước 5: Đặt PdfSaveOptions (Xuất dự án sang PDF)
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

## Kết luận  
Tóm lại, việc giảm khoảng cách giữa danh sách nhiệm vụ và chân trang trong các tệp Microsoft Project là một quy trình đơn giản với Aspose.Tasks cho Java. Bằng cách làm theo các bước trong hướng dẫn này, bạn có thể **xuất dự án sang PDF**, lưu dưới dạng hình ảnh hoặc tạo HTML mà vẫn giữ được bố cục gọn gàng và chuyên nghiệp.

## Câu hỏi thường gặp

### Q: Aspose.Tasks có tương thích với mọi phiên bản của Microsoft Project không?

A: Aspose.Tasks hỗ trợ các định dạng Microsoft Project 2003‑2019, đảm bảo tính tương thích trên nhiều phiên bản khác nhau.

### Q: Tôi có thể tùy chỉnh giao diện của chân trang trong tài liệu dự án không?

A: Có, Aspose.Tasks cung cấp nhiều tùy chọn để tùy chỉnh chân trang, bao gồm giảm khoảng cách và điều chỉnh vị trí nội dung.

### Q: Aspose.Tasks có hỗ trợ lưu dự án ở các định dạng khác ngoài PNG, PDF và HTML không?

A: Có, Aspose.Tasks hỗ trợ đa dạng định dạng, bao gồm XLSX, XML và MPP, cùng nhiều định dạng khác.

### Q: Có phiên bản dùng thử cho Aspose.Tasks không?

A: Có, bạn có thể tải phiên bản dùng thử miễn phí của Aspose.Tasks từ [here](https://releases.aspose.com/).

### Q: Tôi có thể nhận hỗ trợ ở đâu nếu gặp vấn đề khi sử dụng Aspose.Tasks?

A: Bạn có thể nhận trợ giúp từ diễn đàn cộng đồng Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Các câu hỏi thường gặp bổ sung

**Q: Giảm khoảng cách chân trang ảnh hưởng như thế nào đến phân trang?**  
A: Nó giảm không gian trắng ở cuối mỗi trang, cho phép nhiều nhiệm vụ hơn hiển thị trên một trang và giảm tổng số trang.

**Q: Tôi có thể áp dụng cài đặt giảm khoảng cách chỉ cho một trang duy nhất không?**  
A: Có, bằng cách đặt `setRenderToSinglePage(true)` trong `ImageSaveOptions` bạn có thể kiểm soát phân trang đồng thời vẫn giảm khoảng cách.

**Q: Tùy chọn `setReduceFooterGap` có hỗ trợ các định dạng xuất khác không?**  
A: Hiện tại nó được hỗ trợ cho xuất PNG, PDF và HTML. Đối với các định dạng khác, bạn có thể cần điều chỉnh bố cục thủ công.

**Q: Nếu dự án của tôi có trường tùy chỉnh, chúng có được giữ lại không?**  
A: Tất cả các trường tùy chỉnh sẽ được giữ nguyên trong quá trình xuất; các điều chỉnh bố cục chỉ ảnh hưởng đến khoảng cách, không thay đổi dữ liệu.

**Q: Thư viện có xử lý các dự án lớn hiệu quả không?**  
A: Aspose.Tasks truyền dữ liệu theo luồng và có thể xử lý các tệp MPP lớn; tuy nhiên, hãy đảm bảo có đủ bộ nhớ khi xuất ra hình ảnh độ phân giải cao.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}