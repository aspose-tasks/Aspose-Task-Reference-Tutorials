---
date: 2025-12-20
description: Tìm hiểu cách xuất PDF trong Aspose.Tasks cho Java, một hướng dẫn đơn
  giản để chuyển đổi MPP sang PDF và lưu trữ các tệp dự án của bạn một cách hiệu quả.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách xuất PDF trong Aspose.Tasks – Lưu dưới dạng PDF
url: /vi/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách xuất PDF trong Aspose.Tasks – Lưu dưới dạng PDF

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn **cách xuất PDF** trong Aspose.Tasks cho Java, hướng dẫn quy trình lưu dự án dưới dạng PDF. Với Aspose.Tasks, bạn có thể **chuyển đổi MPP sang PDF** một cách hiệu quả, đảm bảo tính tương thích và dễ dàng chia sẻ giữa các nhóm và các bên liên quan. Hãy cùng khám phá các bước để bạn nhanh chóng có được một file PDF có thể in được từ bất kỳ file dự án nào.

## Câu trả lời nhanh
- **“Xuất PDF” có nghĩa là gì trong Aspose.Tasks?** Nó có nghĩa là chuyển đổi một file dự án (ví dụ: MPP) thành tài liệu PDF giữ nguyên bố cục hình ảnh.  
- **Phiên bản thư viện nào được yêu cầu?** Bất kỳ phiên bản Aspose.Tasks for Java nào hỗ trợ `PdfSaveOptions` (khuyến nghị dùng bản mới nhất).  
- **Có cần giấy phép cho việc chuyển đổi này không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể tùy chỉnh giao diện PDF không?** Có – bạn có thể đặt timescale, legends và các `PdfSaveOptions` khác.  
- **Quá trình chuyển đổi có nhanh cho các dự án lớn không?** Thông thường chỉ vài giây; hiệu năng phụ thuộc vào kích thước dự án và các tùy chọn đã chọn.

## “how to export pdf” trong ngữ cảnh Aspose.Tasks là gì?
Việc xuất PDF với Aspose.Tasks có nghĩa là lấy một file dự án (như `.mpp`, `.xml`, hoặc `.xlsx`) và tạo ra một PDF phản ánh biểu đồ Gantt, chế độ xem task usage, hoặc bất kỳ định dạng trình bày nào bạn cấu hình. Điều này hữu ích cho việc báo cáo, tài liệu, hoặc chia sẻ chế độ xem chỉ‑đọc với các bên không chuyên môn.

## Tại sao nên xuất file dự án sang PDF?
- **Đọc được trên mọi thiết bị:** PDF hoạt động trên bất kỳ thiết bị nào mà không cần phần mềm dự án gốc.  
- **Trình bày chuyên nghiệp:** Giữ nguyên định dạng, màu sắc và bố cục cho các báo cáo gửi cho khách hàng.  
- **Dễ dàng phân phối:** Chia sẻ qua email, intranet hoặc lưu trữ đám mây mà không lo về kiểm soát phiên bản.  
- **Tuân thủ & lưu trữ:** PDF là định dạng lý tưởng cho lưu trữ lâu dài và đáp ứng các yêu cầu pháp lý.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn đã có:

1. **Java Development Kit (JDK):** JDK 8 trở lên đã được cài đặt trên máy của bạn.  
2. **Thư viện Aspose.Tasks for Java:** Tải thư viện từ trang chính thức [ở đây](https://releases.aspose.com/tasks/java/).  
3. **File dự án:** Có một file dự án sẵn có (ví dụ: `HomeMovePlan.mpp`) để chuyển đổi.

## Nhập gói
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Hướng dẫn chi tiết

### Bước 1: Đọc file dự án đầu vào
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối tới thư mục chứa file `.mpp` của bạn. Điều này sẽ tải dự án vào bộ nhớ để bạn có thể thao tác hoặc xuất ra.

### Bước 2: Lưu dự án dưới dạng PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Dòng lệnh trên thực hiện thao tác **lưu dự án dưới dạng PDF** đơn giản, tạo ra file `Project5.pdf` trong cùng thư mục.

### Bước 3: Điều chỉnh nội dung vừa với kích thước ô (Tùy chọn lưu PDF nâng cao)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Ở đây chúng ta minh họa cách sử dụng **pdf save options** để kiểm soát bố cục:
- `setFitContent(true)` buộc nội dung vừa với chiều rộng ô.  
- `setTimescale(Timescale.Months)` thay đổi thang thời gian thành tháng.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` chọn chế độ xem Task Usage.

### Bước 4: Ẩn legends (Kết quả sạch hơn)
```java
o.setLegendOnEachPage(false);
```
Tắt legends có thể làm cho PDF gọn hơn, đặc biệt với các dự án lớn.

### Bước 5: Lưu dự án với các tùy chọn đã áp dụng
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Bước cuối cùng này ghi PDF bằng các tùy chọn tùy chỉnh đã định nghĩa ở trên, tạo ra tài liệu có thang thời gian tháng mà không có legends trên mỗi trang.

## Các vấn đề thường gặp & Mẹo
- **File không tìm thấy:** Đảm bảo `dataDir` kết thúc bằng dấu phân cách thư mục (`/` hoặc `\\`) và trỏ đúng tới thư mục chứa file.  
- **Trang trắng:** Kiểm tra `PresentationFormat` đã chọn có khớp với chế độ xem bạn mong muốn (ví dụ: Gantt, Task Usage).  
- **File lớn mất thời gian:** Xem xét đặt `o.setFitContent(false)` cho các dự án rất lớn để giảm thời gian xử lý.  

## Câu hỏi thường gặp

**H: Aspose.Tasks có tương thích với mọi phiên bản Java không?**  
Đ: Có, Aspose.Tasks hỗ trợ các phiên bản Java từ JDK 6 trở lên.

**H: Tôi có thể tùy chỉnh giao diện PDF đầu ra không?**  
Đ: Chắc chắn! Aspose.Tasks cung cấp nhiều **pdf save options**—như thang thời gian, hiển thị legend và định dạng trình bày—để bạn điều chỉnh PDF theo nhu cầu.

**H: Aspose.Tasks hỗ trợ các định dạng file khác để chuyển đổi không?**  
Đ: Có, bạn có thể chuyển đổi giữa MPP, XML, XLSX và nhiều định dạng khác, làm cho nó trở thành công cụ đa năng cho **convert mpp to pdf** và các chuyển đổi khác.

**H: Có phiên bản dùng thử cho Aspose.Tasks không?**  
Đ: Có, bạn có thể tải bản dùng thử miễn phí [ở đây](https://releases.aspose.com/).

**H: Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?**  
Đ: Để được hỗ trợ và trợ giúp, hãy truy cập diễn đàn chính thức [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Kết luận
Sau khi hoàn thành hướng dẫn này, bạn đã biết **cách xuất PDF** từ bất kỳ dự án Java nào bằng Aspose.Tasks, từ việc lưu đơn dòng đến tùy chỉnh nâng cao với `PdfSaveOptions`. Hãy áp dụng các kỹ thuật này để tạo ra các PDF chuyên nghiệp, dễ chia sẻ cho báo cáo, thuyết trình với khách hàng hoặc lưu trữ.

---

**Cập nhật lần cuối:** 2025-12-20  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}