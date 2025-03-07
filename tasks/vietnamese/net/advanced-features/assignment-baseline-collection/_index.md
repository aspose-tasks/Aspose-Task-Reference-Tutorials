---
title: Bộ sưu tập các đường cơ sở của bài tập trong Aspose.Tasks
linktitle: Bộ sưu tập các đường cơ sở của bài tập trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý hiệu quả các đường cơ sở phân công trong quản lý dự án bằng cách sử dụng Aspose.Tasks cho .NET. Nâng cao năng suất và độ chính xác.
weight: 15
url: /vi/net/advanced-features/assignment-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bộ sưu tập các đường cơ sở của bài tập trong Aspose.Tasks

## Giới thiệu

Trong lĩnh vực quản lý dự án, việc theo dõi và quản lý các mốc thời gian phân công là rất quan trọng để đảm bảo sự thành công của dự án và tuân thủ các mốc thời gian. Aspose.Tasks for .NET cung cấp một bộ tính năng mạnh mẽ để hỗ trợ xử lý hiệu quả các đường cơ sở phân công trong các dự án. Trong hướng dẫn này, chúng ta sẽ đi sâu vào những điểm phức tạp khi làm việc với Bộ sưu tập cơ sở bài tập bằng Aspose.Tasks cho .NET.

## Điều kiện tiên quyết

Trước khi tiếp tục với hướng dẫn này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Kiến thức cơ bản về ngôn ngữ lập trình C#.
2. Visual Studio được cài đặt trên hệ thống của bạn.
3.  Aspose.Tasks cho thư viện .NET đã được cài đặt. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).

## Nhập không gian tên

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;


```

## Bước 1: Tải tệp dự án

Đầu tiên, chúng ta cần tải tệp dự án chứa đường cơ sở của bài tập.

```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## Bước 2: Đọc Đường cơ sở của Bài tập

Tiếp theo, chúng tôi lặp lại từng hoạt động phân công tài nguyên trong dự án để truy cập các đường cơ sở tương ứng của chúng.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    var baselines = assignment.Baselines;
    Console.WriteLine("Count of assignment baselines: " + baselines.Count);
    Console.WriteLine("Parent Assignment: " + baselines.ParentAssignment);
    foreach (var baseline in baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
    }

    Console.WriteLine();
}
```

## Bước 3: Xóa đường cơ sở của bài tập

Trong bước này, chúng tôi trình bày cách xóa tất cả các đường cơ sở của nhiệm vụ khỏi dự án.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    List<AssignmentBaseline> baselines = assignment.Baselines.ToList();
    foreach (var baseline in baselines)
    {
        assignment.Baselines.Remove(baseline);
    }
}
```

## Phần kết luận

Quản lý hiệu quả các mốc thời gian phân công là điều tối quan trọng trong quản lý dự án, đảm bảo tuân thủ lịch trình và theo dõi tiến độ dự án một cách chính xác. Với Aspose.Tasks for .NET, việc xử lý các đường cơ sở của nhiệm vụ trở nên liền mạch, cung cấp cho các nhà phát triển các công cụ cần thiết để hợp lý hóa các quy trình quản lý dự án.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks có thể xử lý các đường cơ sở phân công cho các định dạng tệp dự án khác nhau không?

Câu trả lời 1: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án khác nhau, bao gồm MPP, XML và MPX, cho phép bạn quản lý đường cơ sở của bài tập trên các loại tệp khác nhau một cách dễ dàng.

### Câu hỏi 2: Aspose.Tasks có tương thích với tất cả các phiên bản .NET Framework không?

Câu trả lời 2: Aspose.Tasks for .NET tương thích với nhiều phiên bản .NET Framework, đảm bảo tính tương thích và tính linh hoạt cho các nhà phát triển trên các môi trường khác nhau.

### Câu hỏi 3: Tôi có thể thao tác các đường cơ sở của bài tập theo chương trình bằng Aspose.Tasks không?

Câu trả lời 3: Hoàn toàn có thể, Aspose.Tasks cung cấp một API toàn diện cho phép các nhà phát triển tạo, đọc, cập nhật và xóa các đường cơ sở của nhiệm vụ theo yêu cầu của dự án theo chương trình.

### Câu hỏi 4: Aspose.Tasks có cung cấp hỗ trợ kỹ thuật cho nhà phát triển không?

Câu trả lời 4: Có, Aspose.Tasks cung cấp hỗ trợ kỹ thuật mạnh mẽ thông qua diễn đàn cộng đồng, nơi các nhà phát triển có thể tìm kiếm sự trợ giúp, chia sẻ kiến thức và cộng tác với các đồng nghiệp.

### Câu hỏi 5: Tôi có thể dùng thử Aspose.Tasks trước khi mua hàng không?

Câu trả lời 5: Có, Aspose.Tasks cung cấp phiên bản dùng thử miễn phí, cho phép các nhà phát triển khám phá các tính năng và chức năng của nó trước khi đưa ra quyết định mua hàng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
