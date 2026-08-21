---
date: 2026-03-19
description: Học cách thiết lập baseline dự án và quản lý baseline nhiệm vụ một cách
  hiệu quả với Aspose.Tasks cho .NET, đảm bảo việc theo dõi tiến độ dự án một cách
  chính xác.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Thiết lập Đường cơ sở Dự án – Quản lý Đường cơ sở Giao nhiệm vụ trong Aspose.Tasks
url: /vi/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt Đường cơ sở Dự án – Quản lý Đường cơ sở Giao nhiệm vụ trong Aspose.Tasks

## Introduction

Khi làm việc với các nhiệm vụ quản lý dự án, **đặt một đường cơ sở dự án** là điều thiết yếu để đo lường tiến độ thực tế so với kế hoạch gốc. Aspose.Tasks cho .NET không chỉ cho phép bạn **đặt đường cơ sở dự án** mà còn cung cấp kiểm soát đầy đủ đối với các đường cơ sở giao nhiệm vụ, cho phép theo dõi hiệu suất chính xác. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn toàn bộ quy trình—tải dự án, đặt đường cơ sở, đọc dữ liệu đường cơ sở giao nhiệm vụ, và so sánh các đường cơ sở—để bạn có thể tự tin giám sát dự án của mình.

## Quick Answers
- **Câu hỏi “đặt đường cơ sở dự án” có nghĩa là gì?** Nó ghi lại lịch trình và dữ liệu chi phí gốc để so sánh sau này với hiệu suất thực tế.  
- **Phương thức API nào đặt đường cơ sở?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Có cần gọi riêng để đặt đường cơ sở giao nhiệm vụ không?** Không, chúng được lưu tự động khi bạn đặt đường cơ sở dự án.  
- **Các định dạng nào được hỗ trợ?** MPP, XML, MPX và nhiều hơn nữa qua Aspose.Tasks.  
- **Cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại cho việc sử dụng không phải bản thử nghiệm.

## Prerequisites

- Kiến thức cơ bản về lập trình C#.  
- Visual Studio (bất kỳ phiên bản mới nào).  
- Thư viện Aspose.Tasks cho .NET đã được thêm vào dự án của bạn. Bạn có thể tải xuống từ [here](https://releases.aspose.com/tasks/net/).  
- Truy cập vào một tệp dự án ở định dạng MPP (ví dụ, `AssignmentBaseline2007.mpp`).

## Import Namespaces

Thêm các namespace cần thiết ở đầu tệp C# của bạn để trình biên dịch biết nơi tìm các lớp Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Step 1: Load Project and Set Project Baseline

Đầu tiên, tải tệp MPP hiện có và sau đó gọi `SetBaseline` để **đặt đường cơ sở dự án** cho toàn bộ dự án.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Step 2: Read Assignment Baseline Information

Sau khi đã đặt đường cơ sở, mỗi giao nhiệm vụ tài nguyên sẽ chứa các bản ghi đường cơ sở riêng. Vòng lặp dưới đây trích xuất và in ra các chi tiết đó, bao gồm ngày bắt đầu/kết thúc, chi phí, công việc và bất kỳ dữ liệu theo thời gian nào.

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

## Step 3: Compare Assignment Baselines

Bạn có thể so sánh các đường cơ sở của các giao nhiệm vụ khác nhau bằng các toán tử so sánh và bằng nhau có sẵn. Điều này hữu ích khi bạn cần phát hiện sự thay đổi lịch trình hoặc chi phí vượt mức giữa các công việc.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Common Issues and Solutions

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Dữ liệu đường cơ sở xuất hiện trống** | Tệp dự án được mở ở chế độ chỉ đọc hoặc đường cơ sở chưa bao giờ được đặt. | Gọi `project.SetBaseline(BaselineType.Baseline)` trước khi đọc các đường cơ sở giao nhiệm vụ. |
| **`NullReferenceException` trên `TimephasedData`** | Không phải tất cả các đường cơ sở đều chứa mục thời gian. | Luôn kiểm tra `baseline.TimephasedData != null` (như trong mã). |
| **Lấy UID không đúng** | Giá trị UID khác nhau giữa các phiên bản tệp. | Sử dụng `ResourceAssignments.GetByUid` với UID đúng hoặc lặp để tìm giao nhiệm vụ cần thiết. |

## Frequently Asked Questions

**Q: Aspose.Tasks có thể xử lý nhiều đường cơ sở cho một giao nhiệm vụ không?**  
A: Có, Aspose.Tasks hỗ trợ nhiều đường cơ sở cho mỗi giao nhiệm vụ, cho phép theo dõi toàn diện tiến độ dự án theo thời gian.

**Q: Aspose.Tasks có tương thích với các định dạng tệp dự án khác ngoài MPP không?**  
A: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án, bao gồm XML, MPX và MPP, đảm bảo tương thích với các công cụ quản lý dự án khác nhau.

**Q: Tôi có thể sửa đổi thông tin đường cơ sở bằng cách lập trình sử dụng Aspose.Tasks không?**  
A: Chắc chắn, Aspose.Tasks cung cấp các API phong phú để sửa đổi thông tin đường cơ sở một cách động theo yêu cầu dự án, mang lại sự linh hoạt và kiểm soát trong quy trình quản lý dự án.

**Q: Aspose.Tasks có cung cấp tài liệu và nguồn hỗ trợ cho nhà phát triển không?**  
A: Có, các nhà phát triển có thể truy cập tài liệu đầy đủ, hướng dẫn và diễn đàn trên trang web Aspose.Tasks, giúp việc tích hợp và khắc phục sự cố trở nên dễ dàng.

**Q: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?**  
A: Có, các nhà phát triển có thể nhận phiên bản dùng thử miễn phí của Aspose.Tasks cho .NET từ [here](https://releases.aspose.com/), cho phép họ đánh giá các tính năng và khả năng trước khi quyết định mua.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

---