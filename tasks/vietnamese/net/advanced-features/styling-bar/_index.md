---
title: Thanh tạo kiểu trong Aspose.Tasks
linktitle: Thanh tạo kiểu trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách tạo kiểu cho các thanh trong Aspose.Tasks cho .NET để nâng cao khả năng trực quan hóa dự án.
weight: 19
url: /vi/net/advanced-features/styling-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thanh tạo kiểu trong Aspose.Tasks

## Giới thiệu

Thanh tạo kiểu trong Aspose.Tasks là một khía cạnh thiết yếu của việc tạo ra các kế hoạch dự án hấp dẫn về mặt hình ảnh. Với tính linh hoạt do API Aspose.Tasks cung cấp, các nhà phát triển có thể tùy chỉnh các khía cạnh khác nhau của thanh, chẳng hạn như màu sắc, hình dạng và kiểu văn bản, để nâng cao khả năng trực quan hóa dự án. Trong hướng dẫn này, chúng ta sẽ khám phá cách tạo kiểu cho các thanh bằng Aspose.Tasks cho .NET, chia nhỏ từng ví dụ thành các bước có thể quản lý được.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[trang tải xuống](https://releases.aspose.com/tasks/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển có hỗ trợ .NET framework.
3. Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có lợi.

## Nhập không gian tên

Đầu tiên, hãy nhập các không gian tên cần thiết để truy cập các lớp và phương thức Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Bước 1: Tải dự án

Để bắt đầu, hãy tải tệp dự án bằng API Aspose.Tasks:

```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Bước 2: Định cấu hình tùy chọn lưu

Xác định các tùy chọn lưu, chỉ định kiểu thanh sẽ được áp dụng:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Bước 3: Xác định kiểu thanh

Tạo kiểu thanh mới và tùy chỉnh các thuộc tính của nó:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Đặt loại mục thanh
style.BarColor = Color.Green; // Đặt màu thanh
style.BarShape = BarShape.HalfHeight; // Đặt hình dạng thanh
style.StartShape = Shape.LeftBracket; // Đặt hình ở đầu thanh
style.StartShapeColor = Color.Aqua; // Đặt màu của hình bắt đầu
style.EndShape = Shape.RightBracket; // Đặt hình ở cuối thanh
style.EndShapeColor = Color.Aquamarine; // Đặt màu của hình dạng cuối
style.TextStyle = new TextStyle(); // Đặt kiểu văn bản
style.TextStyle.BackgroundColor = Color.Black; // Đặt màu nền cho văn bản
```

## Bước 4: Tùy chỉnh Trình chuyển đổi văn bản

Tùy chọn, tùy chỉnh trình chuyển đổi văn bản để sửa đổi kết xuất văn bản:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Bước 5: Thêm kiểu thanh vào tùy chọn

Thêm kiểu thanh được định cấu hình vào các tùy chọn lưu:

```csharp
options.BarStyles.Add(style);
```

## Bước 6: Lưu dự án

Cuối cùng, lưu dự án với các kiểu thanh được áp dụng:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Phần kết luận

Tùy chỉnh kiểu thanh trong Aspose.Tasks cho .NET cung cấp cho các nhà phát triển khả năng tạo các kế hoạch dự án hấp dẫn trực quan. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tạo kiểu cho các thanh một cách hiệu quả để đáp ứng các yêu cầu trực quan hóa dự án cụ thể.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể áp dụng nhiều kiểu thanh cho một dự án không?

Câu trả lời 1: Có, bạn có thể xác định và áp dụng nhiều kiểu thanh cho các loại nhiệm vụ khác nhau trong cùng một dự án.
   
### Câu hỏi 2: Có thể tự động thay đổi kiểu thanh trong thời gian chạy không?

Câu trả lời 2: Có, bạn có thể tự động sửa đổi kiểu thanh dựa trên các điều kiện nhất định hoặc tùy chọn người dùng trong ứng dụng của mình.
   
### Câu hỏi 3: Aspose.Tasks có hỗ trợ xuất các dự án có thanh được tạo kiểu sang các định dạng tệp khác nhau không?

Câu trả lời 3: Có, Aspose.Tasks hỗ trợ xuất các dự án có thanh được tạo kiểu sang nhiều định dạng khác nhau như PDF, XLSX và HTML.
   
### Câu hỏi 4: Có các kiểu thanh được xác định trước trong Aspose.Tasks không?

Câu trả lời 4: Mặc dù Aspose.Tasks cung cấp các kiểu thanh mặc định, nhưng nhà phát triển cũng có thể tạo các kiểu thanh tùy chỉnh phù hợp với yêu cầu dự án của họ.
   
### Câu hỏi 5: Tôi có thể truy xuất và sửa đổi các kiểu thanh hiện có trong dự án bằng API không?

Câu trả lời 5: Có, bạn có thể truy xuất và sửa đổi các kiểu thanh hiện có theo chương trình bằng cách sử dụng Aspose.Tasks for .NET API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
