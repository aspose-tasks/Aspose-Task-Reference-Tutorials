---
title: Chuyển đổi MS Project thành JPEG trong Aspose.Tasks
linktitle: Lưu dự án dưới dạng JPEG trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách dễ dàng chuyển đổi tệp Microsoft Project thành hình ảnh JPEG bằng Aspose.Tasks cho Java. Tăng năng suất của bạn.
weight: 20
url: /vi/java/project-file-operations/save-as-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi MS Project thành JPEG trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách lưu tệp Microsoft Project dưới dạng hình ảnh JPEG bằng Aspose.Tasks cho Java. Điều này có thể đặc biệt hữu ích để chia sẻ trực quan hóa dự án hoặc tích hợp dữ liệu dự án vào báo cáo hoặc bản trình bày.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt Java trên hệ thống của mình. Bạn có thể tải xuống và cài đặt phiên bản mới nhất từ[Trang web Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java: Tải xuống và thiết lập Aspose.Tasks cho Java bằng cách làm theo hướng dẫn được cung cấp trong[tài liệu](https://reference.aspose.com/tasks/java/).

## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết vào tệp Java của bạn:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## Bước 1: Xác định thư mục dữ liệu
Đặt đường dẫn đến thư mục dữ liệu nơi chứa tệp MS Project của bạn.
```java
String dataDir = "Your Data Directory";
```
## Bước 2: Tải tệp dự án MS
Tải tệp MS Project bằng Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## Bước 3: Định cấu hình chất lượng JPEG (Tùy chọn)
 Nếu bạn muốn điều chỉnh chất lượng JPEG, bạn có thể đặt nó bằng cách sử dụng`ImageSaveOptions` lớp học. Chất lượng dao động từ 0 đến 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Đặt chất lượng JPEG thành 50
```
## Bước 4: Lưu dự án dưới dạng JPEG
Lưu tệp MS Project dưới dạng hình ảnh JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách lưu tệp Microsoft Project dưới dạng hình ảnh JPEG bằng Aspose.Tasks cho Java. Tính năng này cho phép dễ dàng chia sẻ và tích hợp dữ liệu dự án vào các tài liệu và bản trình bày khác nhau.
## Câu hỏi thường gặp
### Hỏi: Tôi có thể điều chỉnh chất lượng của ảnh JPEG không?
 Đáp: Có, bạn có thể điều chỉnh chất lượng bằng cách sử dụng`setJpegQuality()` phương pháp, với phạm vi từ 0 đến 100.
### Hỏi: Nếu tôi không chỉ định chất lượng JPEG thì sao?
Đáp: Nếu bạn không chỉ định chất lượng thì chất lượng mặc định sẽ được sử dụng.
### Câu hỏi: Aspose.Tasks dành cho Java có được sử dụng miễn phí không?
 Trả lời: Aspose.Tasks cho Java là một thư viện thương mại nhưng bạn có thể khám phá các tính năng của nó bằng bản dùng thử miễn phí. Tham quan[trang dùng thử miễn phí](https://releases.aspose.com/) để biết thêm thông tin.
### Câu hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?
Trả lời: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks không?
 Đáp: Có, bạn có thể mua giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
