---
date: 2026-03-19
description: Tìm hiểu cách thêm nhiều cột tùy chỉnh và định dạng độ rộng cột tùy chỉnh
  khi xuất dự án sang XML bằng Aspose.Tasks cho .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Thêm nhiều cột tùy chỉnh vào chế độ xem Assignment trong Aspose.Tasks
url: /vi/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Nhiều Cột Tùy Chỉnh vào Giao Diện Assignment trong Aspose.Tasks

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá **cách thêm nhiều cột tùy chỉnh** vào giao diện assignment với Aspose.Tasks cho .NET. Các cột tùy chỉnh cho phép bạn hiển thị dữ liệu bổ sung—như ghi chú, chi phí, hoặc các cờ tùy chỉnh—trực tiếp trong các báo cáo đã xuất. Khi kết thúc hướng dẫn, bạn sẽ có thể định dạng độ rộng của cột tùy chỉnh, xuất dự án ra XML, và tùy chỉnh giao diện để phù hợp với nhu cầu quản lý dự án của bạn.

## Câu trả lời nhanh
- **Bạn có thể đạt được gì?** Hiển thị bất kỳ dữ liệu assignment nào trong các cột tùy chỉnh và kiểm soát giao diện của chúng.  
- **Định dạng nào hỗ trợ?** Xuất dự án ra XML (hoặc các định dạng khác) bằng cách sử dụng `Spreadsheet2003SaveOptions`.  
- **Có cần giấy phép không?** Có, cần một giấy phép Aspose.Tasks hợp lệ để sử dụng trong môi trường sản xuất.  
- **Phiên bản .NET nào hoạt động?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tôi có thể thêm bao nhiêu cột?** Không giới hạn – chỉ cần tạo thêm các thể hiện `AssignmentViewColumn`.

## Các cột tùy chỉnh đa dạng là gì?
Các cột tùy chỉnh đa dạng là các trường do người dùng định nghĩa xuất hiện cùng với các cột assignment mặc định khi dự án được lưu hoặc xuất. Chúng cung cấp cho bạn khả năng hiển thị bất kỳ thuộc tính nào của đối tượng `ResourceAssignment`, chẳng hạn như ghi chú tùy chỉnh, mã chi phí, hoặc các giá trị tính toán.

## Tại sao nên thêm nhiều cột tùy chỉnh vào giao diện assignment?
- **Báo cáo nâng cao:** Bao gồm thông tin dự án cụ thể mà các cột tích hợp không bao phủ.  
- **Ra quyết định tốt hơn:** Các bên liên quan có thể xem dữ liệu chính xác họ cần mà không phải đào sâu vào các tệp thô.  
- **Định dạng nhất quán:** Kiểm soát độ rộng cột và chuyển đổi văn bản để có đầu ra sạch sẽ, dễ đọc.

## Yêu cầu trước

1. Kiến thức cơ bản về ngôn ngữ lập trình C#.  
2. Thư viện Aspose.Tasks cho .NET đã được cài đặt. Nếu chưa, bạn có thể tải xuống **[tại đây](https://releases.aspose.com/tasks/net/)**.  
3. Một môi trường phát triển tích hợp (IDE) như Visual Studio.  

## Hướng dẫn từng bước

### Bước 1: Nhập các không gian tên
Đầu tiên, nhập các không gian tên cung cấp các lớp mà chúng ta sẽ cần để làm việc với dự án và trực quan hoá.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Bước 2: Tải dự án
Tạo một thể hiện `Project` và tải một tệp MPP hiện có.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Bước 3: Tạo tùy chọn lưu Spreadsheet
Khởi tạo `Spreadsheet2003SaveOptions` – đối tượng này cho phép chúng ta tùy chỉnh giao diện assignment trước khi xuất.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Bước 4: Định nghĩa cột tùy chỉnh
Tạo một `AssignmentViewColumn` cho mỗi dữ liệu bạn muốn hiển thị. Dưới đây chúng tôi thêm một cột **Notes** với độ rộng 200 điểm.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Mẹo:** Để thêm *nhiều* cột tùy chỉnh, lặp lại bước này với các tên trường và logic delegate khác nhau, sau đó thêm mỗi thể hiện vào `options.AssignmentView.Columns`.

### Bước 5: Thêm cột tùy chỉnh vào tùy chọn
Thêm cột (hoặc các cột) vào bộ sưu tập `Columns` của giao diện assignment.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Bước 6: Duyệt qua các Assignment (Gỡ lỗi tùy chọn)
Bạn có thể lặp qua các assignment để xác minh rằng văn bản cột tùy chỉnh được tạo đúng.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Bước 7: Lưu dự án với các cột tùy chỉnh
Cuối cùng, lưu dự án. Ví dụ này lưu dưới dạng XML, nhưng bạn có thể chọn bất kỳ định dạng nào được hỗ trợ.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Cách xuất dự án ra XML với các cột tùy chỉnh?
Khi bạn gọi `project.Save` với `Spreadsheet2003SaveOptions` đã cấu hình, Aspose.Tasks sẽ ghi dữ liệu dự án—bao gồm tất cả **các cột tùy chỉnh đa dạng**—vào tệp XML đã chọn. Điều này giúp dễ dàng chia sẻ thông tin dự án đã được làm phong phú với các hệ thống hoặc bên liên quan khác.

## Định dạng độ rộng cột tùy chỉnh để đọc dễ hơn
Tham số thứ hai của hàm khởi tạo `AssignmentViewColumn` kiểm soát độ rộng cột (được đo bằng điểm). Điều chỉnh giá trị này phù hợp với lượng văn bản bạn mong đợi. Ví dụ, độ rộng **300** hoạt động tốt cho các ghi chú dài, trong khi **100** là đủ cho các cờ ngắn.

## Các vấn đề thường gặp và giải pháp
- **Văn bản cột hiển thị trống:** Đảm bảo delegate trả về một chuỗi và thuộc tính assignment nền (ví dụ, `Asn.NotesText`) đã được điền.  
- **Cột không hiển thị trong tệp đã xuất:** Kiểm tra rằng `options.AssignmentView.Columns` chứa các cột tùy chỉnh của bạn trước khi gọi `Save`.  
- **Độ rộng có vẻ bị bỏ qua:** Một số định dạng xuất có quy tắc bố cục riêng; XML tôn trọng độ rộng, nhưng PDF/HTML có thể cần thêm kiểu dáng.

## Câu hỏi thường gặp

### Q1: Tôi có thể thêm nhiều cột tùy chỉnh vào giao diện assignment không?
**A:** Có, chỉ cần tạo thêm các đối tượng `AssignmentViewColumn` và thêm mỗi đối tượng vào `options.AssignmentView.Columns`.

### Q2: Có các bộ chuyển đổi đã định nghĩa sẵn cho các trường assignment phổ biến không?
**A:** Có, Aspose.Tasks cung cấp các bộ chuyển đổi tích hợp cho nhiều trường chuẩn, giúp dễ dàng lấy dữ liệu mà không cần viết delegate tùy chỉnh.

### Q3: Tôi có thể tùy chỉnh giao diện của các cột tùy chỉnh, chẳng hạn định dạng văn bản hoặc áp dụng kiểu không?
**A:** Chắc chắn. Ngoài việc đặt độ rộng, bạn có thể sửa đổi phông chữ, căn chỉnh và các thuộc tính hiển thị khác thông qua các tùy chọn kiểu dáng của cột.

### Q4: Có thể loại bỏ các cột mặc định khỏi giao diện assignment không?
**A:** Bạn có thể loại bỏ các cột mặc định bằng cách xóa chúng khỏi bộ sưu tập `Columns` hoặc đặt độ rộng của chúng thành zero.

### Q5: Aspose.Tasks có hỗ trợ xuất dự án sang các định dạng khác ngoài bảng tính với các cột tùy chỉnh không?
**A:** Có, Aspose.Tasks có thể xuất ra PDF, HTML, XML và nhiều định dạng khác trong khi vẫn giữ nguyên định nghĩa các cột tùy chỉnh.

---

**Cập nhật lần cuối:** 2026-03-19  
**Kiểm tra với:** Aspose.Tasks 24.12 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}