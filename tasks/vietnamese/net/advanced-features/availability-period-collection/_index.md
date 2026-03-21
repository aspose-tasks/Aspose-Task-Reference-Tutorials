---
date: 2026-03-21
description: Tìm hiểu cách quản lý các khoảng thời gian khả dụng cho tài nguyên và
  đạt được khả năng sẵn sàng tài nguyên dự án hiệu quả với Aspose.Tasks cho .NET.
  Hướng dẫn từng bước này chỉ ra cách thêm, cập nhật và xóa các khoảng thời gian khả
  dụng.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Tính khả dụng tài nguyên dự án – Quản lý các khoảng thời gian khả dụng trong
  Aspose.Tasks
url: /vi/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Độ sẵn có tài nguyên dự án: Bộ sưu tập các khoảng thời gian sẵn có trong Aspose.Tasks

Quản lý **độ sẵn có tài nguyên dự án** là một phần cốt lõi của việc lập kế hoạch dự án thành công. Trong hướng dẫn này, bạn sẽ học **cách quản lý độ sẵn có** cho tài nguyên bằng API Aspose.Tasks cho .NET, từng bước một, từ việc tải dự án đến sao chép các khoảng thời gian giữa các tài nguyên.

## Trả lời nhanh
- **Lớp chính cho các khoảng thời gian sẵn có là gì?** `AvailabilityPeriod` trong không gian tên `Aspose.Tasks`.  
- **Tôi có thể xóa các khoảng thời gian hiện có không?** Có, gọi `resource.AvailabilityPeriods.Clear()`.  
- **Làm sao để thêm một khoảng thời gian mới?** Tạo một đối tượng `AvailabilityPeriod` và sử dụng `Add` hoặc `Insert`.  
- **Có thể sao chép các khoảng thời gian sang tài nguyên khác không?** Chắc chắn – dùng `CopyTo` rồi thêm từng mục vào tài nguyên đích.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Có, cần giấy phép thương mại Aspose.Tasks cho các triển khai không phải thử nghiệm.

## Độ sẵn có tài nguyên dự án là gì?
Độ sẵn có tài nguyên dự án xác định các ngày và đơn vị (tỷ lệ phần trăm năng lực) khi một tài nguyên có thể được gán cho các công việc. Bằng cách kiểm soát các khoảng thời gian này, bạn ngăn ngừa việc quá tải và cải thiện độ chính xác của lịch trình.

## Tại sao nên dùng Aspose.Tasks để quản lý các khoảng thời gian sẵn có?
- **Tích hợp đầy đủ .NET** – không cần COM interop, mã thuần managed.  
- **Kiểm soát chi tiết** – đặt chính xác ngày bắt đầu/kết thúc và đơn vị phân số.  
- **Sao chép dễ dàng** – di chuyển dữ liệu độ sẵn có giữa các tài nguyên mà không cần phân tích thủ công.  
- **Tối ưu hiệu năng** – làm việc hiệu quả với các tệp MPP lớn.

## Yêu cầu trước
1. **Visual Studio** – bất kỳ phiên bản mới nào (2019, 2022, hoặc mới hơn).  
2. **Aspose.Tasks cho .NET** – tải xuống từ [đây](https://releases.aspose.com/tasks/net/).  
3. **Kiến thức C# cơ bản** – bạn nên quen thuộc với lớp, collection và LINQ.

## Nhập không gian tên

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Chúng ta nhập không gian tên cốt lõi Aspose.Tasks cùng với các collection chuẩn của .NET mà sẽ cần sau này.

## Bước 1: Khởi tạo Dự án và Tài nguyên

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Ở đây chúng ta tải một tệp MPP hiện có và lấy tài nguyên mà chúng ta muốn chỉnh sửa độ sẵn có (ID = 1).

## Bước 2: Xóa các khoảng thời gian sẵn có hiện có

```csharp
resource.AvailabilityPeriods.Clear();
```

Việc xóa sẽ loại bỏ mọi khoảng thời gian đã định nghĩa trước, cho chúng ta một khởi đầu sạch sẽ.

## Bước 3: Thêm các khoảng thời gian sẵn có

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Chúng ta lấy một collection các đối tượng `AvailabilityPeriod` (giả sử hàm trợ giúp `GetPeriods` đã được định nghĩa ở nơi khác) và thêm từng cái, kiểm tra xem collection có thể ghi được không.

## Bước 4: Chèn một khoảng thời gian sẵn có mới

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Điều này tạo một khoảng thời gian tùy chỉnh cho năm 2013 và chèn nó vào vị trí 1 (khoảng thứ hai) nếu chưa tồn tại.

## Bước 5: Hiển thị các khoảng thời gian sẵn có

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Một lệnh in nhanh trên console cho thấy tổng số và chi tiết của mỗi khoảng – hữu ích cho việc gỡ lỗi hoặc xác minh.

## Bước 6: Sao chép các khoảng thời gian sẵn có sang tài nguyên khác

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Chúng ta sao chép toàn bộ collection vào một mảng, xóa các khoảng thời gian của tài nguyên đích, rồi lại thêm chúng vào. Điều này minh họa cách nhân bản dữ liệu độ sẵn có giữa các tài nguyên.

## Bước 7: Cập nhật và Xóa các khoảng thời gian sẵn có

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Ở đây chúng ta điều chỉnh `AvailableUnits` cho khoảng thời gian kế cuối và sau đó xóa khoảng thời gian 2013 mà chúng ta đã thêm trước đó.

## Các vấn đề thường gặp và giải pháp
- **Lỗi collection chỉ đọc** – Đảm bảo dự án không được mở ở chế độ chỉ đọc hoặc bạn đã gọi `resource.AvailabilityPeriods.Clear()` trước khi thêm mục mới.  
- **Các khoảng thời gian chồng lấn** – Aspose.Tasks không tự động hợp nhất các khoảng chồng; bạn có thể cần viết logic tùy chỉnh để phát hiện và giải quyết chúng.  
- **Định dạng ngày không đúng** – Luôn sử dụng đối tượng `DateTime`; việc phân tích chuỗi có thể gây lỗi phụ thuộc vào locale.

## Câu hỏi thường gặp

**H: Tôi có thể thêm trường tùy chỉnh vào các khoảng thời gian sẵn có không?**  
Đ: Không, các khoảng thời gian sẵn có trong Aspose.Tasks cho .NET không hỗ trợ trường tùy chỉnh.

**H: Các khoảng thời gian sẵn có có liên kết với công việc cụ thể nào không?**  
Đ: Không, chúng được liên kết với tài nguyên và xác định thời điểm tài nguyên chung chung có sẵn cho các công việc.

**H: Tôi có thể nhập các khoảng thời gian sẵn có từ nguồn bên ngoài không?**  
Đ: Có, bạn có thể nhập các khoảng thời gian từ CSV, XML, hoặc cơ sở dữ liệu bằng cách tạo các đối tượng `AvailabilityPeriod` và thêm chúng vào collection.

**H: Làm sao để xử lý các khoảng thời gian sẵn có chồng lấn?**  
Đ: Các chồng lấn không được tự động giải quyết; bạn cần triển khai kiểm tra tùy chỉnh để hợp nhất hoặc từ chối các khoảng thời gian xung đột.

**H: Có giới hạn số lượng khoảng thời gian sẵn có mà một tài nguyên có thể có không?**  
Đ: Không có giới hạn cứng, nhưng các collection rất lớn có thể ảnh hưởng đến hiệu năng; hãy cân nhắc gộp các khoảng thời gian khi có thể.

## Kết luận

Trong hướng dẫn này, chúng ta đã bao quát mọi thứ bạn cần biết để quản lý **độ sẵn có tài nguyên dự án** với Aspose.Tasks cho .NET — từ khởi tạo dự án và xóa dữ liệu cũ, đến thêm, chèn, sao chép, cập nhật và xóa các khoảng thời gian sẵn có. Nắm vững các bước này giúp bạn duy trì lịch làm việc của tài nguyên chính xác và làm cho lịch trình dự án trở nên thực tế hơn.

---

**Cập nhật lần cuối:** 2026-03-21  
**Đã kiểm tra với:** Aspose.Tasks cho .NET (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}