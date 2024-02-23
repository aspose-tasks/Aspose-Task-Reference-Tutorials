---
title: Làm việc với thao tác KHÔNG trong Aspose.Tasks
linktitle: Làm việc với thao tác KHÔNG trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách sử dụng thao tác NOT trong Aspose.Tasks for .NET để lọc các tác vụ một cách hiệu quả. Hãy nâng cao khả năng quản lý dự án của bạn ngay bây giờ.
type: docs
weight: 20
url: /vi/net/advanced-concepts/not-operation/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng thao tác NOT trong Aspose.Tasks cho .NET. Thao tác NOT cho phép chúng ta đảo ngược điều kiện lọc, cho phép chúng ta chọn các phần tử không đáp ứng tiêu chí đã chỉ định.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Visual Studio: Bạn cần có bản cài đặt Visual Studio đang hoạt động để làm theo các ví dụ về mã.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[trang mạng](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ hữu ích trong việc hiểu các ví dụ về mã.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết cho mã của chúng tôi:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Bước 1: Thiết lập dự án và nhiệm vụ

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Chúng tôi bắt đầu bằng cách tải tệp dự án có tên "Project2.mpp" bằng cách sử dụng`Project` lớp được cung cấp bởi Aspose.Tasks. Đảm bảo rằng tệp dự án tồn tại trong thư mục được chỉ định.

## Bước 2: Thu thập nhiệm vụ dự án

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Ở đây, chúng tôi tạo ra một`ChildTasksCollector` đối tượng để tập hợp tất cả các nhiệm vụ trong dự án. Sau đó chúng tôi sử dụng`TaskUtils.Apply`phương pháp duyệt qua hệ thống phân cấp nhiệm vụ của dự án và thu thập tất cả các nhiệm vụ con.

## Bước 3: Xác định điều kiện lọc

```csharp
var filter = new NullCondition();
```

 Chúng tôi xác định điều kiện lọc bằng cách sử dụng lớp tùy chỉnh có tên`NullCondition`, Điều kiện này chọn các tác vụ có giá trị null.

## Bước 4: Áp dụng thao tác NOT

```csharp
var condition = new Not<Task>(filter);
```

 Chúng ta áp dụng thao tác NOT cho điều kiện lọc bằng cách sử dụng`Not<T>` lớp được cung cấp bởi Aspose.Tasks. Điều này sẽ đảo ngược điều kiện lọc, chọn các tác vụ không có giá trị null.

## Bước 5: Lọc nhiệm vụ

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Chúng tôi lọc các tác vụ đã thu thập dựa trên điều kiện được áp dụng bằng cách sử dụng tùy chỉnh`Filter` phương pháp. Phương thức này lấy một tập hợp các tác vụ có thể đếm được và một điều kiện lọc làm tham số đầu vào và trả về danh sách các tác vụ thỏa mãn điều kiện.

## Bước 6: Xử lý các tác vụ đã lọc

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Làm việc với các thuộc tính khác...
}
```

Cuối cùng, chúng tôi lặp lại các tác vụ đã lọc và thực hiện bất kỳ thao tác mong muốn nào. Trong ví dụ này, chúng tôi chỉ in tên của các tác vụ ra bảng điều khiển.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách làm việc với thao tác NOT trong Aspose.Tasks cho .NET. Bằng cách đảo ngược các điều kiện lọc, chúng tôi có thể chọn lọc các phần tử không đáp ứng các tiêu chí đã chỉ định, nâng cao tính linh hoạt trong thao tác tác vụ trong dự án.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks với các khung .NET khác không?

Trả lời: Có, Aspose.Tasks hỗ trợ nhiều khung .NET khác nhau bao gồm .NET Core, .NET Standard và .NET Framework.

### Câu hỏi 2: Aspose.Tasks có bản dùng thử miễn phí không?

 Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ[trang mạng](https://releases.aspose.com/).

### Câu 3: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks?

 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) cho bất kỳ truy vấn hỗ trợ hoặc hỗ trợ kỹ thuật.

### Câu hỏi 4: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks không?

 Đáp: Có, bạn có thể mua giấy phép tạm thời từ[trang mua hàng](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 5: Tôi có thể tìm tài liệu toàn diện về Aspose.Tasks ở đâu?

 Đáp: Bạn có thể truy cập tài liệu đầy đủ trên[Trang tài liệu Aspose.Tasks](https://reference.aspose.com/tasks/net/).