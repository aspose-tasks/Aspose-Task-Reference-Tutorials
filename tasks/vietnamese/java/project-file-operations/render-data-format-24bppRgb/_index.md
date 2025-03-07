---
title: Kết xuất dữ liệu dự án MS với định dạng 24bppRgb trong Aspose.Tasks
linktitle: Kết xuất dữ liệu với định dạng 24bppRgb trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách hiển thị dữ liệu MS Project dưới dạng hình ảnh trong Java bằng Aspose.Tasks. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
weight: 11
url: /vi/java/project-file-operations/render-data-format-24bppRgb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kết xuất dữ liệu dự án MS với định dạng 24bppRgb trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình kết xuất dữ liệu với định dạng MS Project 24bppRgb bằng Aspose.Tasks cho Java. Việc hiển thị dữ liệu dự án thành định dạng hình ảnh có thể hữu ích cho nhiều mục đích khác nhau như chia sẻ tiến độ dự án một cách trực quan hoặc tạo báo cáo.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Tasks cho Java: Tải xuống và cài đặt Aspose.Tasks cho Java từ[đây](https://releases.aspose.com/tasks/java/).
3. Kiến thức cơ bản về lập trình Java: Làm quen với ngôn ngữ lập trình Java sẽ hữu ích để hiểu và triển khai các ví dụ về mã.

## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết trong dự án Java của mình:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Hãy chia ví dụ được cung cấp thành nhiều bước:
## Bước 1: Xác định thư mục dữ liệu
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Data Directory";
```
Trong bước này, bạn xác định thư mục chứa dữ liệu dự án của bạn. Thay thế`"Your Data Directory"` với đường dẫn thực tế đến thư mục dữ liệu của bạn.
## Bước 2: Tải tệp dự án
```java
Project project = new Project(dataDir + "project.mpp");
```
Ở đây, chúng tôi tải tệp MS Project (`project.mpp` ) bằng cách sử dụng Aspose.Tasks và lưu trữ nó trong`project` sự vật.
## Bước 3: Định cấu hình tùy chọn lưu hình ảnh
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Bước này liên quan đến việc định cấu hình các tùy chọn để lưu dữ liệu dự án dưới dạng hình ảnh. Chúng tôi chỉ định định dạng hình ảnh (TIFF), độ phân giải ngang và dọc cũng như định dạng pixel (24bppRgb).
## Bước 4: Lưu dữ liệu dự án dưới dạng hình ảnh
```java
project.save(dataDir + "resFile.tif", options);
```
Cuối cùng, chúng tôi lưu dữ liệu dự án dưới dạng tệp hình ảnh (`resFile.tif`) với các tùy chọn được chỉ định.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách hiển thị dữ liệu dự án với định dạng MS Project 24bppRgb bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng chuyển đổi dữ liệu dự án của mình sang định dạng hình ảnh cho nhiều mục đích khác nhau.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể hiển thị dữ liệu dự án ở các định dạng hình ảnh khác không?
Trả lời: Có, Aspose.Tasks hỗ trợ hiển thị dữ liệu dự án thành nhiều định dạng hình ảnh khác nhau như PNG, JPEG, BMP, v.v.
### Câu hỏi: Aspose.Tasks có tương thích với các phiên bản khác nhau của MS Project không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều phiên bản MS Project bao gồm 2003, 2007, 2010, 2013 và 2016.
### Hỏi: Tôi có thể tùy chỉnh độ phân giải và định dạng pixel của hình ảnh được hiển thị không?
Trả lời: Có, bạn có thể tùy chỉnh độ phân giải và định dạng pixel theo yêu cầu của mình bằng Aspose.Tasks.
### Câu hỏi: Aspose.Tasks có yêu cầu giấy phép sử dụng thương mại không?
 Trả lời: Có, bạn cần mua giấy phép sử dụng Aspose.Tasks cho mục đích thương mại. Bạn có thể xin giấy phép tạm thời cho mục đích thử nghiệm từ[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?
 Trả lời: Bạn có thể nhận hỗ trợ cho Aspose.Tasks từ[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
