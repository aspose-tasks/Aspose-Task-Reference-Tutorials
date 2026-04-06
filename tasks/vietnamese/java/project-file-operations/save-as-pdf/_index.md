---
date: 2026-03-27
description: Tìm hiểu cách lưu dự án dưới dạng PDF bằng Aspose.Tasks cho Java, hướng
  dẫn đơn giản để chuyển đổi MPP sang PDF và xuất file dự án một cách hiệu quả.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách Lưu Dự Án Dưới Dạng PDF với Aspose.Tasks – Hướng Dẫn Xuất
url: /vi/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Lưu Dự Án dưới dạng PDF với Aspose.Tasks – Hướng Dẫn Xuất

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách lưu dự án dưới dạng pdf** bằng Aspose.Tasks cho Java. Chúng tôi sẽ hướng dẫn bạn từ việc chuyển đổi chỉ bằng một dòng lệnh đến tùy chỉnh PDF nâng cao, để bạn có thể chuyển bất kỳ tệp MPP (hoặc định dạng hỗ trợ khác) nào thành tài liệu PDF được hoàn thiện, có thể chia sẻ. Dù bạn cần một báo cáo in nhanh hay một biểu đồ Gantt được định dạng đầy đủ, các bước này sẽ giúp bạn thực hiện nhanh chóng.

## Câu trả lời nhanh
- **“Xuất PDF” có nghĩa là gì trong Aspose.Tasks?** Nó có nghĩa là chuyển đổi một tệp dự án (ví dụ: MPP) thành tài liệu PDF giữ nguyên bố cục hình ảnh.  
- **Phiên bản thư viện nào được yêu cầu?** Bất kỳ phiên bản Aspose.Tasks cho Java nào hỗ trợ `PdfSaveOptions` (khuyến nghị dùng bản mới nhất).  
- **Có cần giấy phép cho việc chuyển đổi này không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể tùy chỉnh giao diện PDF không?** Có – bạn có thể đặt thang thời gian, chú giải và các `PdfSaveOptions` khác.  
- **Việc chuyển đổi có nhanh cho các dự án lớn không?** Thông thường trong vài giây; hiệu năng phụ thuộc vào kích thước dự án và các tùy chọn đã chọn.

## “Lưu dự án dưới dạng pdf” trong ngữ cảnh Aspose.Tasks là gì?
Lưu một dự án dưới dạng PDF với Aspose.Tasks có nghĩa là lấy một tệp dự án (như `.mpp`, `.xml`, hoặc `.xlsx`) và tạo ra một PDF phản ánh biểu đồ Gantt, chế độ xem sử dụng nhiệm vụ, hoặc bất kỳ định dạng trình bày nào bạn cấu hình. Điều này hữu ích cho việc báo cáo, tài liệu, hoặc chia sẻ các chế độ xem chỉ‑đọc với các bên không chuyên môn.

## Tại sao nên xuất biểu đồ Gantt ra PDF?
- **Đọc được trên mọi thiết bị:** PDF mở được trên bất kỳ thiết bị nào mà không cần phần mềm dự án gốc.  
- **Trình bày chuyên nghiệp:** Giữ nguyên màu sắc, phông chữ và bố cục cho các báo cáo gửi cho khách hàng.  
- **Dễ dàng phân phối:** Chia sẻ qua email, intranet hoặc lưu trữ đám mây mà không lo về kiểm soát phiên bản.  
- **Tuân thủ & lưu trữ:** PDF là định dạng lý tưởng cho lưu trữ dài hạn và đáp ứng các yêu cầu pháp lý.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy chắc chắn bạn đã có:

1. **Java Development Kit (JDK):** JDK 8 trở lên đã được cài đặt trên máy tính.  
2. **Thư viện Aspose.Tasks cho Java:** Tải thư viện từ trang chính thức [ở đây](https://releases.aspose.com/tasks/java/).  
3. **Tệp Dự Án:** Có một tệp dự án hiện có (ví dụ: `HomeMovePlan.mpp`) sẵn sàng để chuyển đổi.

## Nhập các gói
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Hướng dẫn từng bước

### Bước 1: Đọc tệp dự án đầu vào
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Thay `"Your Data Directory"` bằng đường dẫn tuyệt đối nơi tệp `.mpp` của bạn nằm. Điều này sẽ tải dự án vào bộ nhớ để bạn có thể thao tác hoặc xuất ra.

### Bước 2: Lưu dự án dưới dạng PDF (Chuyển đổi cơ bản)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Dòng lệnh trên thực hiện một thao tác **lưu dự án dưới dạng pdf** đơn giản, tạo ra `Project5.pdf` trong cùng thư mục.

### Bước 3: Điều chỉnh nội dung vừa với kích thước ô (Tùy chọn PDF nâng cao)
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

### Bước 4: Ẩn chú giải (Kết quả gọn hơn)
```java
o.setLegendOnEachPage(false);
```
Tắt chú giải có thể làm PDF gọn hơn, đặc biệt với các dự án lớn.

### Bước 5: Lưu dự án với các tùy chọn đã áp dụng
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Bước cuối cùng này ghi PDF bằng các tùy chọn tùy chỉnh đã định nghĩa ở trên, tạo ra tài liệu có thang thời gian tháng mà không có chú giải trên mỗi trang.

## Xuất biểu đồ Gantt ra PDF – Định dạng tùy chỉnh
Nếu bạn muốn xuất chỉ biểu đồ Gantt với giao diện cụ thể, đặt `PresentationFormat` thành `GanttChart` và điều chỉnh các tùy chọn bổ sung như `setBarColor` hoặc `setShowCriticalTasks`. Cách này cho phép bạn **export gantt chart to pdf** với toàn quyền kiểm soát các yếu tố hình ảnh.

## Các vấn đề thường gặp & Mẹo
- **Không tìm thấy tệp:** Đảm bảo `dataDir` kết thúc bằng dấu phân cách thư mục (`/` hoặc `\\`) và trỏ tới thư mục đúng.  
- **Trang trắng:** Kiểm tra rằng `PresentationFormat` đã chọn khớp với chế độ xem bạn mong muốn (ví dụ: Gantt, Task Usage).  
- **Tệp lớn mất thời gian:** Xem xét đặt `o.setFitContent(false)` cho các dự án rất lớn để giảm thời gian xử lý.  

## Câu hỏi thường gặp

**H: Aspose.Tasks có tương thích với mọi phiên bản Java không?**  
Đ: Có, Aspose.Tasks hỗ trợ các phiên bản Java từ JDK 6 trở lên.

**H: Tôi có thể tùy chỉnh giao diện của PDF xuất ra không?**  
Đ: Chắc chắn! Aspose.Tasks cung cấp nhiều **pdf save options**—như thang thời gian, hiển thị chú giải và định dạng trình bày—để bạn điều chỉnh PDF theo nhu cầu.

**H: Aspose.Tasks có hỗ trợ các định dạng tệp khác để chuyển đổi không?**  
Đ: Có, bạn có thể chuyển đổi giữa MPP, XML, XLSX và nhiều định dạng khác, làm cho nó trở thành công cụ đa năng cho **convert mpp to pdf** và các chuyển đổi khác.

**H: Có phiên bản dùng thử cho Aspose.Tasks không?**  
Đ: Có, bạn có thể tải bản dùng thử miễn phí của Aspose.Tasks [ở đây](https://releases.aspose.com/).

**H: Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?**  
Đ: Để được hỗ trợ và trợ giúp, hãy truy cập diễn đàn chính thức [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn đã biết **cách lưu dự án dưới dạng pdf** từ bất kỳ dự án Java nào sử dụng Aspose.Tasks, từ việc lưu một dòng đơn giản đến tùy chỉnh nâng cao với `PdfSaveOptions`. Áp dụng các kỹ thuật này để tạo ra các PDF chuyên nghiệp, có thể chia sẻ cho báo cáo, trình bày với khách hàng hoặc lưu trữ.

---

**Cập nhật lần cuối:** 2026-03-27  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}