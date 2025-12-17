---
date: 2025-12-17
description: Tìm hiểu cách lưu dự án dưới dạng hình ảnh và thay đổi độ phân giải hình
  ảnh trong Java bằng Aspose.Tasks for Java. Hướng dẫn từng bước này cho thấy cách
  render dữ liệu MS Project với định dạng 24bppRgb.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Lưu Dự Án dưới dạng Hình ảnh – Định dạng 24bppRgb với Aspose.Tasks
url: /vi/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu Dự Án dưới Dạng Hình Ảnh – Định Dạng 24bppRgb với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **save project as image** bằng cách sử dụng định dạng pixel 24bppRgb với Aspose.Tasks cho Java. Việc render dữ liệu MS Project thành hình ảnh rất hữu ích khi bạn cần chia sẻ một ảnh chụp nhanh trực quan của lịch trình, nhúng một dòng thời gian vào báo cáo, hoặc tạo các thumbnail cho cổng dự án. Chúng tôi cũng sẽ chỉ cho bạn cách **change image resolution java** để đáp ứng yêu cầu chất lượng của bạn.

## Câu trả lời nhanh
- **Tôi có thể render dự án thành hình ảnh không?** Yes, Aspose.Tasks lets you save a project as TIFF, PNG, JPEG, etc.  
- **Định dạng pixel nào cho độ sâu màu tốt nhất?** `Format24bppRgb` provides true‑color (24‑bit) images.  
- **Làm sao tôi điều chỉnh độ phân giải hình ảnh?** Use `setHorizontalResolution` and `setVerticalResolution` on `ImageSaveOptions`.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** A commercial license is required for non‑evaluation use.  
- **Điều này có tương thích với tất cả các phiên bản Java không?** Works with Java 8 and newer.

## “save project as image” là gì?
Lưu dự án dưới dạng hình ảnh chuyển đổi biểu diễn trực quan của tệp Microsoft Project (`.mpp`) thành định dạng raster (ví dụ: TIFF). Tệp kết quả có thể được hiển thị trong trình duyệt, chèn vào tài liệu, hoặc in mà không cần ứng dụng Project gốc.

## Tại sao nên sử dụng định dạng 24bppRgb?
Định dạng pixel 24bppRgb lưu mỗi pixel với 8 bit cho màu đỏ, xanh lá và xanh dương, mang lại chất lượng màu thật mà không có kênh alpha. Điều này lý tưởng cho các báo cáo có độ rõ cao, nơi độ trung thực màu sắc quan trọng, đồng thời giữ kích thước tệp ở mức hợp lý so với các định dạng 32‑bit.

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

### Bước 1: Xác định Thư mục Dữ liệu
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối nơi tệp `.mpp` của bạn nằm.

### Bước 2: Tải tệp Dự án
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
Ở đây chúng tôi đặt định dạng đầu ra là TIFF, chỉ định độ phân giải **72 dpi** (bạn có thể thay đổi các giá trị này để phù hợp với nhu cầu của mình – đây là nơi bạn **change image resolution java**), và chọn định dạng pixel 24bppRgb cho đầu ra màu thật.

### Bước 4: Lưu dữ liệu Dự án dưới dạng Hình ảnh
```java
project.save(dataDir + "resFile.tif", options);
```
Phương thức `save` ghi hình ảnh đã render vào `resFile.tif` bằng cách sử dụng các tùy chọn đã định nghĩa ở trên.

## Các vấn đề thường gặp và giải pháp
| Issue | Reason | Fix |
|-------|--------|-----|
| **Kết quả hình ảnh trống** | Giao diện dự án có thể trống. | Gọi `project.setDefaultView(ViewType.Gantt);` trước khi lưu. |
| **Hình ảnh chất lượng thấp** | Độ phân giải được đặt quá thấp. | Tăng `setHorizontalResolution` và `setVerticalResolution` (ví dụ: 150 dpi). |
| **Định dạng pixel không được hỗ trợ** | Sử dụng phiên bản Aspose.Tasks cũ. | Nâng cấp lên phiên bản Aspose.Tasks for Java mới nhất. |

## Kết luận
Bây giờ bạn đã biết cách **save project as image** với định dạng 24bppRgb và điều chỉnh độ phân giải bằng Aspose.Tasks cho Java. Cách tiếp cận này cho phép bạn tạo ra các biểu diễn trực quan rõ ràng, màu sắc chính xác của lịch trình dự án để chia sẻ, báo cáo hoặc lưu trữ.

## Câu hỏi thường gặp
### Hỏi: Tôi có thể render dữ liệu dự án ở các định dạng hình ảnh khác không?
A: Có, Aspose.Tasks hỗ trợ render dữ liệu dự án thành các định dạng hình ảnh khác nhau như PNG, JPEG, BMP, v.v.

### Hỏi: Aspose.Tasks có tương thích với các phiên bản khác nhau của MS Project không?
A: Có, Aspose.Tasks hỗ trợ nhiều phiên bản của MS Project bao gồm 2003, 2007, 2010, 2013 và 2016.

### Hỏi: Tôi có thể tùy chỉnh độ phân giải và định dạng pixel của hình ảnh đã render không?
A: Có, bạn có thể tùy chỉnh độ phân giải và định dạng pixel theo yêu cầu của mình bằng Aspose.Tasks.

### Hỏi: Aspose.Tasks có yêu cầu giấy phép cho việc sử dụng thương mại không?
A: Có, bạn cần mua giấy phép để sử dụng Aspose.Tasks trong môi trường thương mại. Bạn có thể nhận giấy phép tạm thời để thử nghiệm từ [here](https://purchase.aspose.com/temporary-license/).

### Hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?
A: Bạn có thể nhận hỗ trợ cho Aspose.Tasks từ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Cập nhật lần cuối:** 2025-12-17  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}