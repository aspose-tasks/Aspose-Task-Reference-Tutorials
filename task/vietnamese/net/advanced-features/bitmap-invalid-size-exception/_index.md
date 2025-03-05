---
title: Xử lý ngoại lệ kích thước không hợp lệ cho Bitmap trong Aspose.Tasks
linktitle: Xử lý ngoại lệ kích thước không hợp lệ cho Bitmap trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách xử lý BitmapInvalidSizeException trong Aspose.Tasks cho .NET khi lưu dự án dưới dạng hình ảnh. Hướng dẫn toàn diện với hướng dẫn từng bước.
type: docs
weight: 22
url: /vi/net/advanced-features/bitmap-invalid-size-exception/
---
## Giới thiệu

 Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc xử lý các`BitmapInvalidSizeException` khi làm việc với Aspose.Tasks cho .NET. Aspose.Tasks là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project theo chương trình, cho phép thực hiện các tác vụ như lưu dự án dưới dạng hình ảnh. Tuy nhiên, đôi khi, khi cố gắng lưu dự án dưới dạng hình ảnh, chúng ta có thể gặp phải lỗi`Invalid Size Exception`liên quan đến bitmap. Hướng dẫn này nhằm mục đích hướng dẫn bạn qua quá trình phát hiện và xử lý ngoại lệ này một cách hiệu quả.

## Điều kiện tiên quyết

Trước khi tiếp tục với hướng dẫn này, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:
1. Hiểu biết cơ bản về ngôn ngữ lập trình C#.
2. Đã cài đặt Aspose.Tasks cho .NET.
3. Làm quen với việc làm việc với các tập tin Microsoft Project.

## Nhập không gian tên

Trước khi bắt đầu, hãy đảm bảo nhập các không gian tên cần thiết:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Bước 1: Khởi tạo dự án và xác định chế độ xem

 Đầu tiên, khởi tạo một`Project` đối tượng và xác định một khung nhìn, chẳng hạn như`GanttChartView`.

```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

## Bước 2: Chỉ định tùy chọn lưu hình ảnh

Tiếp theo, chỉ định các tùy chọn lưu hình ảnh, bao gồm định dạng và khoảng thời gian.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

## Bước 3: Đặt đơn vị và số lượng thang thời gian

Điều chỉnh đơn vị thời gian và đếm theo yêu cầu của bạn. Trong ví dụ này, chúng tôi đặt khoảng thời gian thành phút.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

## Bước 4: Lưu dự án dưới dạng hình ảnh

Cố gắng lưu dự án dưới dạng hình ảnh bằng các tùy chọn đã chỉ định.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

## Bước 5: Bắt và xử lý ngoại lệ

 Thực hiện xử lý ngoại lệ để nắm bắt`BitmapInvalidSizeException` nếu nó xảy ra trong quá trình lưu ảnh.

```csharp
try
{
    // Cố gắng lưu dự án dưới dạng hình ảnh
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Xử lý ngoại lệ
    Console.WriteLine(ex.Message);
}
```

## Phần kết luận

 Tóm lại, việc xử lý`BitmapInvalidSizeException` khi lưu dự án dưới dạng hình ảnh trong Aspose.Tasks cho .NET là rất quan trọng để đảm bảo ứng dụng của bạn thực thi trơn tru. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể nắm bắt và xử lý ngoại lệ này một cách hiệu quả, từ đó nâng cao tính chắc chắn của các giải pháp quản lý dự án của bạn.

## Câu hỏi thường gặp

### Câu hỏi 1: Điều gì gây ra BitmapInvalidSizeException trong Aspose.Tasks?

Câu trả lời 1: Ngoại lệ này xảy ra khi cố gắng lưu dự án dưới dạng hình ảnh với tham số kích thước bitmap không hợp lệ.

### Câu hỏi 2: Tôi có thể tùy chỉnh khoảng thời gian khi lưu dự án dưới dạng hình ảnh không?

Câu trả lời 2: Có, bạn có thể điều chỉnh đơn vị thời gian và đếm theo yêu cầu của mình, như được minh họa trong hướng dẫn.

### Câu hỏi 3: Tôi có thể tìm thêm tài nguyên để làm việc với Aspose.Tasks cho .NET ở đâu?

Câu trả lời 3: Bạn có thể khám phá các tài liệu và diễn đàn hỗ trợ do Aspose.Tasks cung cấp để được hướng dẫn và hỗ trợ toàn diện.

### Câu hỏi 4: Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?

Trả lời 4: Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, cho phép khả năng tương tác liền mạch.

### Câu hỏi 5: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Tasks?

Câu trả lời 5: Bạn có thể lấy giấy phép tạm thời cho mục đích đánh giá thông qua liên kết được cung cấp trong bài viết.