---
date: 2026-04-06
description: Tìm hiểu cách thay đổi kiểu dáng thanh và tùy chỉnh màu sắc thanh trong
  Aspose.Tasks cho .NET để nâng cao khả năng hiển thị dự án.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Thanh Định dạng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cách thay đổi kiểu dáng thanh trong Aspose.Tasks
url: /vi/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thay Đổi Kiểu Định Dạng Thanh trong Aspose.Tasks

## Giới thiệu

Nếu bạn cần **cách thay đổi thanh** xuất hiện trong tệp Microsoft Project, Aspose.Tasks cho .NET cung cấp cho bạn toàn quyền kiểm soát màu sắc, hình dạng và kiểu chữ của thanh. Bằng cách tùy chỉnh màu thanh và các thuộc tính trực quan khác, bạn có thể làm cho kế hoạch dự án dễ đọc hơn và phù hợp hơn với thương hiệu của tổ chức. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn qua một ví dụ đầy đủ, từng bước, cho thấy cách thay đổi kiểu định dạng thanh, từ việc tải dự án đến xuất nó với các quy tắc trực quan mới được áp dụng.

## Câu trả lời nhanh
- **Có thể định dạng gì?** Thanh, mốc quan trọng và văn bản nhiệm vụ trong biểu đồ Gantt.  
- **Định dạng nào hỗ trợ thanh được định dạng?** PDF, XLSX, HTML và MPP gốc khi lưu bằng `PdfSaveOptions`.  
- **Có cần giấy phép không?** Cần giấy phép thương mại cho việc sử dụng trong môi trường sản xuất; bản dùng thử miễn phí có thể dùng để thử nghiệm.  
- **Có thể áp dụng nhiều kiểu không?** Có – thêm bao nhiêu đối tượng `BarStyle` tùy bạn.  
- **Có tương thích với .NET Core không?** Hoàn toàn – hoạt động với .NET Framework và .NET Core/5/6+.

## Kiểu Định Dạng Thanh là gì trong Aspose.Tasks?

Kiểu định dạng thanh cho phép bạn định nghĩa các quy tắc trực quan mà engine Aspose.Tasks áp dụng khi render biểu đồ Gantt. Mỗi quy tắc (một **BarStyle**) nhắm tới một loại mục cụ thể—nhiệm vụ, mốc quan trọng hoặc nhiệm vụ tổng hợp—và cho phép bạn đặt màu sắc, hình dạng và thậm chí văn bản tùy chỉnh.

## Tại sao nên tùy chỉnh màu thanh?

Việc tùy chỉnh màu thanh giúp các bên liên quan nhanh chóng nhận diện các đường quan trọng, nhiệm vụ bị trễ hoặc mốc quan trọng. Nó cũng cho phép bạn phù hợp với bảng màu công ty, làm cho báo cáo trông chuyên nghiệp và đồng nhất với thương hiệu.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn bạn có:

1. **Aspose.Tasks for .NET** – tải xuống từ [trang tải xuống](https://releases.aspose.com/tasks/net/).  
2. Môi trường phát triển hỗ trợ .NET (Framework 4.6+, .NET Core 3.1+ hoặc mới hơn).  
3. Kiến thức cơ bản về C# – các ví dụ sử dụng mã đơn giản, tự chứa.

## Nhập không gian tên

Đầu tiên, nhập các không gian tên chứa các lớp chúng ta sẽ sử dụng:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Bước 1: Tải Dự Án

Tải một tệp MPP hiện có (hoặc tạo một tệp mới) để bạn có đối tượng dự án để làm việc:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Bước 2: Cấu hình tùy chọn lưu

Tạo một thể hiện `PdfSaveOptions` và khởi tạo bộ sưu tập `BarStyles` nơi chúng ta sẽ lưu các kiểu tùy chỉnh của mình:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Bước 3: Định nghĩa Kiểu Thanh

Bây giờ chúng ta tạo một đối tượng `BarStyle` và thiết lập các thuộc tính kiểm soát cách thanh hiển thị. Đây là nơi chúng ta **tùy chỉnh màu thanh** và hình dạng:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Bước 4: Tùy chỉnh Bộ chuyển đổi Văn bản (Tùy chọn)

Nếu bạn muốn điều chỉnh văn bản hiển thị trên thanh, bạn có thể gán một bộ chuyển đổi tùy chỉnh. Ví dụ này thêm tiền tố vào tên nhiệm vụ nếu chúng chưa bắt đầu bằng “T”:

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

## Bước 5: Thêm Kiểu Thanh vào Tùy chọn

Thêm kiểu đã cấu hình đầy đủ vào bộ sưu tập `BarStyles` của tùy chọn lưu:

```csharp
options.BarStyles.Add(style);
```

## Bước 6: Lưu Dự Án

Cuối cùng, xuất dự án. PDF (hoặc định dạng khác) sẽ render biểu đồ Gantt sử dụng kiểu thanh chúng ta đã định nghĩa:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **Kiểu thanh không được áp dụng** | Bộ sưu tập `BarStyles` trống hoặc không được gắn vào tùy chọn lưu. | Đảm bảo bạn thêm `BarStyle` vào `options.BarStyles` trước khi gọi `Save`. |
| **Màu sắc trông khác trong PDF** | Quá trình render PDF có thể sử dụng hồ sơ màu khác. | Sử dụng các giá trị `System.Drawing.Color` tiêu chuẩn hoặc định nghĩa màu ARGB tùy chỉnh. |
| **Bộ chuyển đổi văn bản gây lỗi tham chiếu null** | Thuộc tính `Tsk.Name` của nhiệm vụ là null đối với một số nhiệm vụ. | Thêm kiểm tra null trước khi truy cập `task.Get(Tsk.Name)`. |

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể áp dụng nhiều kiểu thanh cho một dự án duy nhất không?

A1: Có, bạn có thể định nghĩa và áp dụng nhiều kiểu thanh cho các loại nhiệm vụ khác nhau trong cùng một dự án.

### Câu hỏi 2: Có thể thay đổi kiểu thanh một cách động trong thời gian chạy không?

A2: Có, bạn có thể thay đổi kiểu thanh một cách động dựa trên các điều kiện nhất định hoặc sở thích người dùng trong ứng dụng của bạn.

### Câu hỏi 3: Aspose.Tasks có hỗ trợ xuất dự án với các thanh được định dạng sang các định dạng tệp khác nhau không?

A3: Có, Aspose.Tasks hỗ trợ xuất dự án với các thanh được định dạng sang nhiều định dạng như PDF, XLSX và HTML.

### Câu hỏi 4: Có các kiểu thanh được định sẵn trong Aspose.Tasks không?

A4: Mặc dù Aspose.Tasks cung cấp các kiểu thanh mặc định, các nhà phát triển cũng có thể tạo các kiểu thanh tùy chỉnh phù hợp với yêu cầu dự án của họ.

### Câu hỏi 5: Tôi có thể truy xuất và sửa đổi các kiểu thanh hiện có trong dự án bằng API không?

A5: Có, bạn có thể truy xuất và sửa đổi các kiểu thanh hiện có một cách lập trình bằng API Aspose.Tasks cho .NET.

## Câu hỏi thường gặp

**Q: Làm thế nào để thay đổi màu thanh cho các nhiệm vụ thường thay vì mốc quan trọng?**  
A: Đặt `style.ItemType = BarItemType.Task;` và gán `style.BarColor` tới `Color` mong muốn.

**Q: Tôi có thể sử dụng cách này để định dạng thanh khi xuất ra HTML không?**  
A: Có. Sử dụng `HtmlSaveOptions` và điền bộ sưu tập `BarStyles` của nó theo cùng cách.

**Q: Có giới hạn số lượng kiểu thanh tôi có thể định nghĩa không?**  
A: Thực tế không; bạn có thể thêm bao nhiêu tùy ý, nhưng cần lưu ý hiệu năng khi bộ sưu tập rất lớn.

**Q: Tôi có cần gọi `project.Calculate()` sau khi thay đổi kiểu không?**  
A: Không, các kiểu được áp dụng trong quá trình lưu; việc tính toán lại chỉ cần thiết cho các thay đổi lịch trình.

**Cập nhật lần cuối:** 2026-04-06  
**Kiểm tra với:** Aspose.Tasks 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}