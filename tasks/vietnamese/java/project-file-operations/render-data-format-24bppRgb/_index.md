---
date: 2026-03-21
description: Tìm hiểu cách tăng chất lượng hình ảnh bằng cách lưu dự án dưới dạng
  ảnh 24bppRgb và thay đổi độ phân giải hình ảnh trong Java với Aspose.Tasks. Hướng
  dẫn này cũng chỉ cách lưu các định dạng ảnh của dự án.
linktitle: Increase Image Quality – Save Project Image (24bppRgb)
second_title: Aspose.Tasks Java API
title: Tăng chất lượng hình ảnh – Lưu hình ảnh dự án (24bppRgb)
url: /vi/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tăng Chất Lượng Hình Ảnh – Lưu Hình Ảnh Dự Án (24bppRgb) với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **tăng chất lượng hình ảnh** bằng cách lưu dự án dưới dạng hình ảnh sử dụng định dạng pixel 24bppRgb với Aspose.Tasks cho Java. Việc render dữ liệu MS Project thành hình ảnh rất hữu ích khi bạn cần chia sẻ một ảnh chụp nhanh trực quan của lịch trình, nhúng một dòng thời gian vào báo cáo, hoặc tạo ảnh thu nhỏ cho cổng dự án. Chúng tôi cũng sẽ chỉ cho bạn cách **change image resolution java** để đầu ra đáp ứng đúng yêu cầu chất lượng của bạn.

## Câu trả lời nhanh
- **Tôi có thể render dự án thành hình ảnh không?** Có, Aspose.Tasks cho phép bạn lưu dự án dưới dạng TIFF, PNG, JPEG, v.v.  
- **Định dạng pixel nào cho độ sâu màu tốt nhất?** `Format24bppRgb` cung cấp hình ảnh true‑color (24‑bit).  
- **Làm thế nào để điều chỉnh độ phân giải hình ảnh?** Sử dụng `setHorizontalResolution` và `setVerticalResolution` trên `ImageSaveOptions`.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Cần giấy phép thương mại cho việc sử dụng không phải đánh giá.  
- **Liệu điều này có tương thích với mọi phiên bản Java không?** Hoạt động với Java 8 và các phiên bản mới hơn.

## Lưu hình ảnh dự án là gì?
Lưu dự án dưới dạng hình ảnh chuyển đổi biểu diễn trực quan của tệp Microsoft Project (`.mpp`) thành định dạng raster (ví dụ: TIFF). Tệp kết quả có thể được hiển thị trong trình duyệt, chèn vào tài liệu, hoặc in mà không cần ứng dụng Project gốc.

## Tại sao nên sử dụng định dạng 24bppRgb để **tăng chất lượng hình ảnh**?
Định dạng pixel 24bppRgb lưu mỗi pixel với 8 bit cho màu đỏ, xanh lá và xanh dương, cung cấp chất lượng true‑color mà không có kênh alpha. Điều này lý tưởng cho các báo cáo độ rõ cao nơi độ trung thực màu sắc quan trọng, đồng thời giữ kích thước tệp ở mức hợp lý so với các định dạng 32‑bit.

## Các trường hợp sử dụng phổ biến
- **Lưu hình ảnh biểu đồ Gantt** cho bảng điều khiển trạng thái dự án.  
- **Tạo ảnh thu nhỏ dự án** cho các bảng xem trước trong cổng web.  
- **Tùy chỉnh hình ảnh dự án** độ phân giải đầu ra cho việc in hoặc hiển thị DPI cao.  
- **Lưu hình ảnh dự án** ở các định dạng khác nhau (TIFF, PNG, JPEG) cho tài liệu.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – JDK 8 hoặc mới hơn đã được cài đặt trên máy của bạn.  
2. **Aspose.Tasks for Java** – Tải xuống và cài đặt từ [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – Quen thuộc với cú pháp Java và cách thiết lập dự án sẽ giúp bạn theo dõi các đoạn mã.

## Nhập các gói
Đầu tiên, nhập các lớp Aspose.Tasks cần thiết vào dự án Java của bạn:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Hướng dẫn từng bước

### Bước 1: Xác định thư mục dữ liệu
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối nơi tệp `.mpp` của bạn nằm.

### Bước 2: Tải tệp dự án
```java
Project project = new Project(dataDir + "project.mpp");
```
Dòng này đọc tệp Microsoft Project (`project.mpp`) và tạo một đối tượng `Project` mà Aspose.Tasks có thể thao tác.

### Bước 3: Cấu hình tùy chọn lưu hình ảnh
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Ở đây chúng tôi đặt định dạng đầu ra là TIFF, chỉ định độ phân giải **72 dpi** (bạn có thể thay đổi các giá trị này để phù hợp với nhu cầu của mình – đây là nơi bạn **change image resolution java**), và chọn định dạng pixel 24bppRgb cho đầu ra true‑color.

### Bước 4: Lưu dữ liệu dự án dưới dạng hình ảnh
```java
project.save(dataDir + "resFile.tif", options);
```
Phương thức `save` ghi hình ảnh đã render vào `resFile.tif` bằng cách sử dụng các tùy chọn đã định nghĩa ở trên.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| **Kết quả hình ảnh trống** | Giao diện dự án có thể trống. | Gọi `project.setDefaultView(ViewType.Gantt);` trước khi lưu. |
| **Hình ảnh chất lượng thấp** | Độ phân giải được đặt quá thấp. | Tăng `setHorizontalResolution` và `setVerticalResolution` (ví dụ, 150 dpi). |
| **Định dạng pixel không được hỗ trợ** | Sử dụng phiên bản Aspose.Tasks cũ hơn. | Nâng cấp lên phiên bản Aspose.Tasks for Java mới nhất. |

## Kết luận
Bây giờ bạn đã biết cách **tăng chất lượng hình ảnh** bằng cách lưu dự án dưới dạng hình ảnh với định dạng 24bppRgb và điều chỉnh độ phân giải bằng Aspose.Tasks cho Java. Cách tiếp cận này cho phép bạn tạo ra các biểu diễn trực quan rõ ràng, màu sắc chính xác của lịch trình dự án để chia sẻ, báo cáo hoặc lưu trữ.

## Câu hỏi thường gặp

**Q: Tôi có thể render dữ liệu dự án sang các định dạng hình ảnh khác không?**  
A: Có, Aspose.Tasks hỗ trợ render dữ liệu dự án thành nhiều định dạng hình ảnh như PNG, JPEG, BMP, v.v.

**Q: Aspose.Tasks có tương thích với các phiên bản khác nhau của MS Project không?**  
A: Có, Aspose.Tasks hỗ trợ nhiều phiên bản MS Project bao gồm 2003, 2007, 2010, 2013 và 2016.

**Q: Tôi có thể tùy chỉnh độ phân giải và định dạng pixel của hình ảnh đã render không?**  
A: Có, bạn có thể tùy chỉnh độ phân giải và định dạng pixel theo yêu cầu của mình bằng Aspose.Tasks.

**Q: Aspose.Tasks có yêu cầu giấy phép cho việc sử dụng thương mại không?**  
A: Có, bạn cần mua giấy phép cho việc sử dụng thương mại của Aspose.Tasks. Bạn có thể nhận giấy phép tạm thời để thử nghiệm từ [here](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?**  
A: Bạn có thể nhận hỗ trợ cho Aspose.Tasks từ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Cập nhật lần cuối:** 2026-03-21  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}