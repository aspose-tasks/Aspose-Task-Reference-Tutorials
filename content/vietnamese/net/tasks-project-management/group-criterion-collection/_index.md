---
title: Quản lý tiêu chí nhóm dự án MS với Aspose.Tasks
linktitle: Quản lý bộ sưu tập tiêu chí nhóm trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý bộ sưu tập Dự án MS Tiêu chí Nhóm bằng Aspose.Tasks cho .NET. Hướng dẫn từng bước dành cho nhà phát triển.
type: docs
weight: 28
url: /vi/net/tasks-project-management/group-criterion-collection/
---
## Giới thiệu
Aspose.Tasks for .NET là một API mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project theo chương trình. Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý bộ sưu tập Tiêu chí nhóm trong MS Project bằng Aspose.Tasks.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Tasks for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Tasks trong dự án .NET của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).

2. Tệp dự án Microsoft: Có sẵn tệp Microsoft Project (MPP) để làm việc.

## Nhập không gian tên

Trước tiên, bạn cần nhập các vùng tên cần thiết vào mã C# của mình. Bước này rất quan trọng để truy cập các chức năng do Aspose.Tasks cung cấp.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Bước 1: Tải tệp dự án

 Khởi tạo một`Project` đối tượng bằng cách tải tệp MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Bước 2: Tiêu chí nhóm truy cập

Truy xuất nhóm từ dự án và truy cập các tiêu chí của nó.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Bước 3: Lặp lại các tiêu chí nhóm

Lặp lại từng tiêu chí trong nhóm và hiển thị các thuộc tính của nó.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Bước 4: Xóa tiêu chí nhóm

Xóa tiêu chí nhóm hiện có nếu nó không ở chế độ chỉ đọc.

```csharp
group.GroupCriteria.Clear();
```

## Bước 5: Thêm tiêu chí mới

Tạo một tiêu chí nhóm mới và thêm nó vào nhóm.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Bước 6: Sao chép tiêu chí sang nhóm khác

Sao chép tiêu chí từ nhóm này sang nhóm khác.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách quản lý bộ sưu tập Dự án MS Tiêu chí Nhóm bằng Aspose.Tasks cho .NET. Bằng cách làm theo các bước này, bạn có thể thao tác hiệu quả các tiêu chí nhóm trong tệp Microsoft Project của mình theo chương trình.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks có tương thích với tất cả các phiên bản Microsoft Project không?

Trả lời: Có, Aspose.Tasks hỗ trợ các tệp Microsoft Project thuộc nhiều phiên bản khác nhau, bao gồm 2003, 2007, 2010, 2013 và 2016.

### Câu hỏi 2: Tôi có thể áp dụng nhiều tiêu chí cho một nhóm không?

Đáp: Hoàn toàn có thể, bạn có thể thêm nhiều tiêu chí vào một nhóm bằng cách lặp lại từng tiêu chí và thêm chúng cho phù hợp.

### Câu hỏi 3: Có phiên bản dùng thử cho Aspose.Tasks không?

 Trả lời: Có, bạn có thể nhận bản dùng thử miễn phí Aspose.Tasks từ[đây](https://releases.aspose.com/).

### Câu hỏi 4: Tôi có thể tìm tài liệu về Aspose.Tasks ở đâu?

 Đáp: Bạn có thể tham khảo tài liệu[đây](https://reference.aspose.com/tasks/net/).

### Câu hỏi 5: Làm cách nào tôi có thể nhận được hỗ trợ nếu gặp bất kỳ vấn đề nào?

 Trả lời: Nếu bạn có bất kỳ câu hỏi nào hoặc gặp phải bất kỳ vấn đề nào, bạn có thể tìm kiếm sự hỗ trợ từ diễn đàn Aspose.Tasks.[đây](https://forum.aspose.com/c/tasks/15).