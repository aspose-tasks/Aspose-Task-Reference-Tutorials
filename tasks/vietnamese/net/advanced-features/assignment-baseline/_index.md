---
title: Quản lý đường cơ sở của bài tập trong Aspose.Tasks
linktitle: Quản lý đường cơ sở của bài tập trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý đường cơ sở của nhiệm vụ một cách hiệu quả với Aspose.Tasks cho .NET, đảm bảo theo dõi chính xác tiến độ và hiệu suất của dự án.
weight: 14
url: /vi/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Quản lý đường cơ sở của bài tập trong Aspose.Tasks

## Giới thiệu

Khi thực hiện các nhiệm vụ quản lý dự án, việc quản lý các đường cơ sở của nhiệm vụ là rất quan trọng để theo dõi tiến độ một cách chính xác. Aspose.Tasks for .NET cung cấp một bộ công cụ toàn diện để xử lý các đường cơ sở của bài tập một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quy trình quản lý đường cơ sở của nhiệm vụ theo từng bước.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Visual Studio được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Tasks cho .NET đã được thêm vào dự án của bạn. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
- Truy cập vào tệp dự án ở định dạng MPP.

## Nhập không gian tên

Để bắt đầu làm việc với Aspose.Tasks, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình. Thêm các không gian tên sau vào đầu tệp C# của bạn:

```csharp
using Aspose.Tasks;
using System;


```

## Bước 1: Tải dự án và đặt đường cơ sở

 Đầu tiên, tải tệp dự án bằng cách sử dụng`Project` lớp từ Aspose.Tasks. Sau đó, đặt loại đường cơ sở cho dự án bằng cách sử dụng`SetBaseline` phương pháp.

```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Bước 2: Đọc thông tin cơ bản của bài tập

Lặp lại từng nhiệm vụ tài nguyên trong dự án và truy xuất thông tin cơ bản cho từng nhiệm vụ.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Bước 3: Kiểm tra sự bình đẳng cơ bản

So sánh thông tin cơ bản cho các bài tập khác nhau bằng các phương pháp so sánh khác nhau do Aspose.Tasks cung cấp.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Kiểm tra sự bình đẳng cơ bản
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Kiểm tra so sánh cơ sở
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Hiển thị mã băm cơ sở
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Phần kết luận

Quản lý đường cơ sở phân công là một phần không thể thiếu trong quản lý dự án, cho phép theo dõi chính xác tiến độ và hiệu suất. Với Aspose.Tasks for .NET, việc xử lý các đường cơ sở của nhiệm vụ trở nên hợp lý và hiệu quả, cung cấp cho các nhà phát triển các công cụ mạnh mẽ để nâng cao quy trình quản lý dự án.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks có thể xử lý nhiều đường cơ sở cho một nhiệm vụ không?

Câu trả lời 1: Có, Aspose.Tasks hỗ trợ nhiều đường cơ sở cho mỗi nhiệm vụ, cho phép theo dõi toàn diện tiến độ dự án theo thời gian.

### Câu hỏi 2: Aspose.Tasks có tương thích với nhiều định dạng tệp dự án khác ngoài MPP không?

Câu trả lời 2: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án, bao gồm XML, MPX và MPP, đảm bảo khả năng tương thích với nhiều công cụ quản lý dự án khác nhau.

### Câu hỏi 3: Tôi có thể sửa đổi thông tin cơ sở theo chương trình bằng Aspose.Tasks không?

Câu trả lời 3: Hoàn toàn có thể, Aspose.Tasks cung cấp các API mở rộng để sửa đổi thông tin cơ sở một cách linh hoạt theo yêu cầu của dự án, mang lại sự linh hoạt và khả năng kiểm soát các quy trình quản lý dự án.

### Câu hỏi 4: Aspose.Tasks có cung cấp tài liệu và tài nguyên hỗ trợ cho nhà phát triển không?

Câu trả lời 4: Có, nhà phát triển có thể truy cập tài liệu, hướng dẫn và diễn đàn toàn diện trên trang web Aspose.Tasks, tạo điều kiện tích hợp và khắc phục sự cố suôn sẻ.

### Câu hỏi 5: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?

 Câu trả lời 5: Có, nhà phát triển có thể tải phiên bản dùng thử miễn phí của Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/), cho phép họ đánh giá các tính năng và khả năng của nó trước khi đưa ra quyết định mua hàng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
