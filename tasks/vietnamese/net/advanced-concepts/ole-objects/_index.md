---
date: 2026-03-16
description: Tìm hiểu cách xóa các đối tượng OLE bằng Aspose.Tasks cho .NET, và khám
  phá cách quản lý OLE và xóa OLE một cách hiệu quả trong các dự án của bạn.
linktitle: How to Remove OLE Objects in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Cách xóa các đối tượng OLE trong Aspose.Tasks cho .NET
url: /vi/net/advanced-concepts/ole-objects/
weight: 22
---

 unchanged.

Now produce final content.

Be careful to preserve markdown formatting.

Let's craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Xóa Các Đối Tượng OLE trong Aspose.Tasks cho .NET

## Giới thiệu

Aspose.Tasks cho .NET cung cấp cho bạn khả năng kiểm soát toàn bộ các đối tượng OLE (Object Linking and Embedding) nằm bên trong các tệp Microsoft Project. Trong hướng dẫn này, bạn sẽ học **cách xóa các đối tượng OLE**, cách **quản lý nội dung OLE**, và các bước chính xác để **xóa dữ liệu OLE** khi không còn cần thiết. Khi hoàn thành, bạn sẽ có thể tải một tệp dự án, kiểm tra các đối tượng OLE được nhúng, xóa chúng một cách an toàn, và lưu lại dự án đã được làm sạch — tất cả bằng mã C# sạch sẽ và dễ đọc.

## Trả lời nhanh
- **Cách chính để xóa các đối tượng OLE là gì?** Sử dụng `project.OleObjects.Clear()` rồi lưu dự án.  
- **Tôi có cần giấy phép đặc biệt không?** Cần có giấy phép Aspose.Tasks hợp lệ cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tôi có thể kiểm tra nội dung OLE trước khi xóa không?** Có, duyệt qua `project.OleObjects` để đọc các thuộc tính hoặc byte nội dung.  
- **Việc xóa OLE trong các dự án lớn có an toàn không?** Hoàn toàn an toàn – thao tác nhanh và không ảnh hưởng đến dữ liệu dự án khác.

## “Xóa các đối tượng OLE” có nghĩa là gì trong ngữ cảnh Aspose.Tasks?

Xóa các đối tượng OLE có nghĩa là xóa các tệp nhúng (hình ảnh, bảng Excel, tài liệu Word, v.v.) được lưu bên trong tệp Microsoft Project (.mpp). Điều này hữu ích khi bạn muốn giảm kích thước tệp, loại bỏ các tham chiếu lỗi thời, hoặc tuân thủ các chính sách lưu trữ dữ liệu.

## Tại sao nên quản lý các đối tượng OLE bằng Aspose.Tasks?

- **Kiểm soát chi tiết** – Truy cập ID, tên và byte thô của từng đối tượng OLE.  
- **Tự động hoá** – Dọn dẹp hàng chục dự án một cách lập trình mà không cần mở chúng trong Microsoft Project.  
- **Hỗ trợ đa phiên bản** – Hoạt động với các tệp Project 2007‑2023.  

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Aspose.Tasks cho .NET** đã được cài đặt. Bạn có thể tải về từ [đây](https://releases.aspose.com/tasks/net/).  
2. Kiến thức cơ bản về **C#** và hệ sinh thái **.NET**.  
3. Môi trường phát triển như **Visual Studio** (Community hoặc cao hơn).  

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cung cấp API của Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Cách quản lý các đối tượng OLE – Hướng dẫn từng bước

Dưới đây chúng tôi sẽ trình bày ba kịch bản phổ biến:

1. **Kiểm tra các đối tượng OLE** – đọc thuộc tính và một đoạn nhỏ của nội dung nhị phân.  
2. **Xóa toàn bộ các đối tượng OLE** – thao tác “xóa OLE” cốt lõi.  
3. **Đọc thông tin vị trí hiển thị** – hữu ích khi bạn cần điều chỉnh cách các đối tượng OLE xuất hiện trong Gantt hoặc các chế độ xem khác.

### Kịch bản 1: Kiểm tra các đối tượng OLE

#### Bước 1: Tải tệp dự án  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Bước 2: Truy cập các đối tượng OLE  
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

#### Bước 3: Duyệt qua các đối tượng OLE  
```csharp
foreach (var oleObject in oleObjects)
{
    // Access and print OLE object properties
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Continue for other properties
}
```

#### Bước 4: Lấy một phần nhỏ của nội dung nhị phân (tùy chọn)  
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

### Kịch bản 2: Cách xóa OLE – loại bỏ tất cả các đối tượng nhúng

#### Bước 1: Tải tệp dự án  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Bước 2: Xóa các đối tượng OLE  
```csharp
project.OleObjects.Clear();
```

#### Bước 3: Lưu dự án đã được làm sạch  
```csharp
project.Save("ClearedProject.mpp");
```

> **Mẹo chuyên nghiệp:** Sau khi xóa các đối tượng OLE, bạn có thể gọi `project.Save` với tên tệp khác để giữ nguyên bản gốc.

### Kịch bản 3: Lấy các thuộc tính vị trí hiển thị của đối tượng

#### Bước 1: Tải tệp dự án  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Bước 2: Truy cập đối tượng OLE đầu tiên và vị trí của nó trong chế độ xem Gantt  
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

#### Bước 3: Lấy các thuộc tính vị trí  
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## Những lỗi thường gặp và cách khắc phục

| Vấn đề | Lý do | Cách khắc phục |
|-------|--------|----------------|
| `project.OleObjects` rỗng | Tệp .mpp nguồn không chứa bất kỳ đối tượng OLE nào. | Kiểm tra lại tệp dự án có thực sự nhúng dữ liệu OLE (ví dụ: một bảng Excel đính kèm). |
| `project.Save` ném ngoại lệ | Tệp đang bị khóa hoặc bạn không có quyền ghi. | Đóng mọi phiên bản mở của tệp và đảm bảo thư mục đích có quyền ghi. |
| Byte nội dung trông bị hỏng | Bạn đang đọc toàn bộ mảng byte dưới dạng văn bản. | Sử dụng `Get10Bytes` hoặc ghi byte ra tệp để kiểm tra bằng công cụ phù hợp. |

## Câu hỏi thường gặp

**H: Aspose.Tasks có thể xử lý các định dạng đối tượng OLE khác nhau không?**  
Đ: Có, nó hỗ trợ hình ảnh, tài liệu Office, PDF và nhiều định dạng OLE khác.

**H: API có tương thích với các phiên bản Microsoft Project cũ không?**  
Đ: Hoàn toàn – Aspose.Tasks hoạt động với các tệp Project từ 2007 tới các phiên bản mới nhất năm 2023.

**H: Làm sao để xóa chỉ một số đối tượng OLE cụ thể thay vì xóa toàn bộ?**  
Đ: Tìm `OleObject` mong muốn bằng `Id` hoặc `Name` và gọi `project.OleObjects.Remove(oleObject)` trước khi lưu.

**H: Việc xóa OLE có ảnh hưởng đến các phụ thuộc công việc hoặc lịch trình không?**  
Đ: Không. Các đối tượng OLE là các yếu tố hiển thị độc lập; việc xóa chúng không thay đổi quan hệ giữa các công việc.

**H: Tôi có thể tìm thêm ví dụ về thao tác OLE ở đâu?**  
Đ: Tham khảo tài liệu chính thức của Aspose.Tasks và tham chiếu API cho các lớp `OleObject` và `VisualObjectsPlacements`.

## Kết luận

Chúng ta đã bao quát mọi thứ cần thiết để **xóa các đối tượng OLE** và quản lý nội dung OLE trong Aspose.Tasks cho .NET. Bằng cách làm theo các ví dụ từng bước, bạn có thể kiểm tra, xóa và điều chỉnh vị trí hiển thị của các đối tượng OLE, giúp các tệp dự án của bạn gọn nhẹ và tập trung hơn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-03-16  
**Kiểm tra với:** Aspose.Tasks 24.11 cho .NET  
**Tác giả:** Aspose