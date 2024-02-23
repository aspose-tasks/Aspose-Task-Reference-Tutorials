---
title: Nắm vững các tiêu chí lọc của dự án MS với Aspose.Tasks
linktitle: Tiêu chí lọc trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách triển khai tiêu chí lọc trong MS Project bằng Aspose.Tasks for .NET. Tăng hiệu quả quản lý dự án bằng phân tích dữ liệu mục tiêu.
type: docs
weight: 18
url: /vi/net/tasks-project-management/filter-criteria/
---
## Giới thiệu
Trong lĩnh vực quản lý dự án, Microsoft Project là một công cụ vững chắc, cung cấp rất nhiều tính năng để hỗ trợ người lập kế hoạch và quản lý dự án. Trong số nhiều chức năng của nó có khả năng lọc dữ liệu dự án, cho phép người dùng tập trung vào các khía cạnh cụ thể trong nhiệm vụ dự án của họ. Tuy nhiên, việc thành thạo các khả năng lọc này có thể là một nhiệm vụ khó khăn nếu không có hướng dẫn phù hợp. Hướng dẫn này nhằm mục đích làm sáng tỏ quy trình bằng cách cung cấp hướng dẫn từng bước về cách triển khai bộ lọc tiêu chí trong MS Project bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1. Hiểu biết cơ bản về C#: Cần phải làm quen với ngôn ngữ lập trình C# để nắm bắt các khái niệm được đề cập trong hướng dẫn này.
2.  Cài đặt Aspose.Tasks cho .NET: Đảm bảo bạn đã cài đặt Aspose.Tasks cho .NET trong môi trường phát triển của mình. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/net/).
3. Tệp dự án Microsoft: Chuẩn bị sẵn tệp Microsoft Project (ví dụ: Project2003.mpp), tệp này bạn sẽ sử dụng để triển khai các tiêu chí lọc.

## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết để làm việc với Aspose.Tasks cho .NET. Thực hiện theo các bước sau:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Bước 1: Tải tệp dự án
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Giải thích: Dòng mã này khởi tạo một phiên bản mới của`Project` class và tải tệp Microsoft Project được chỉ định bởi đường dẫn của nó.
## Bước 2: Truy xuất bộ lọc tác vụ
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Giải thích: Ở đây, chúng tôi truy xuất bộ lọc tác vụ từ dự án. Điều chỉnh chỉ số (`[1]`) theo yêu cầu của bạn để chọn bộ lọc mong muốn.
## Bước 3: Hiển thị hàng tiêu chí
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Giải thích: Phần này lặp qua từng hàng tiêu chí của bộ lọc và hiển thị trường, hoạt động, kiểm tra và các giá trị của nó (nếu có).
## Bước 4: In tiêu chí bộ lọc
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Giải thích: In hoạt động của các tiêu chí lọc.
## Bước 5: Hiển thị chi tiết tiêu chí
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Giải thích: Phần này truy xuất và hiển thị thông tin chi tiết về từng hàng tiêu chí, cung cấp thông tin chi tiết về cấu hình của bộ lọc.

## Phần kết luận
Nắm vững tiêu chí lọc trong MS Project bằng Aspose.Tasks for .NET là một kỹ năng quý giá có thể nâng cao đáng kể hiệu quả quản lý dự án. Bằng cách làm theo hướng dẫn này, bạn đã học được cách thao tác các tiêu chí lọc theo chương trình, cho phép bạn điều chỉnh các chế độ xem dự án theo nhu cầu cụ thể của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể áp dụng đồng thời nhiều bộ lọc trong MS Project không?
Đáp: Có, bạn có thể kết hợp nhiều bộ lọc để tinh chỉnh thêm dữ liệu dự án của mình.
### Câu hỏi: Aspose.Tasks có hỗ trợ các phiên bản cũ hơn của tệp Microsoft Project không?
Trả lời: Có, Aspose.Tasks cung cấp khả năng tương thích ngược, cho phép bạn làm việc với nhiều phiên bản khác nhau của tệp Microsoft Project.
### Câu hỏi: Aspose.Tasks có tương thích với các khung .NET khác không?
Trả lời: Aspose.Tasks hỗ trợ .NET Framework, .NET Core và .NET Standard, đảm bảo tính linh hoạt trên các môi trường phát triển khác nhau.
### Câu hỏi: Tôi có thể tùy chỉnh tiêu chí lọc dựa trên điều kiện động không?
Đáp: Hoàn toàn có thể, bạn có thể điều chỉnh tiêu chí lọc theo chương trình dựa trên các tham số động, cho phép phân tích dữ liệu dự án thích ứng.
### Câu hỏi: Tôi có thể tìm kiếm hỗ trợ ở đâu nếu gặp sự cố với Aspose.Tasks?
 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để tìm kiếm sự hỗ trợ từ cộng đồng hoặc liên hệ trực tiếp với bộ phận hỗ trợ của Aspose.Tasks để được hỗ trợ cá nhân hóa.