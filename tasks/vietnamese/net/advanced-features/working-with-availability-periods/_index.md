---
date: 2026-04-06
description: Tìm hiểu cách thêm nguồn lực vào dự án và thiết lập các khoảng thời gian
  khả dụng của nguồn lực bằng Aspose.Tasks cho .NET. Hướng dẫn từng bước để quản lý
  lịch nguồn lực.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Làm việc với các khoảng thời gian khả dụng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Thêm tài nguyên vào dự án và đặt khả năng sẵn sàng trong Aspose.Tasks
url: /vi/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm tài nguyên vào dự án và đặt khả dụng trong Aspose.Tasks

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học **cách thêm tài nguyên vào dự án** và sau đó xác định các khoảng thời gian khả dụng của nó bằng thư viện Aspose.Tasks .NET. Quản lý lịch tài nguyên là điều cần thiết cho các lịch trình dự án thực tế, và các bước dưới đây sẽ hướng dẫn bạn qua toàn bộ quá trình — từ tạo một thể hiện dự án đến in ra chi tiết của từng khoảng thời gian.

## Trả lời nhanh
- **Mục tiêu chính là gì?** Thêm một tài nguyên vào dự án và cấu hình các khoảng thời gian khả dụng.  
- **Thư viện nào được yêu cầu?** Aspose.Tasks cho .NET.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại.  
- **Các phiên bản .NET được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Thời gian thực hiện?** Thông thường dưới 15 phút cho các kịch bản cơ bản.

## “Thêm tài nguyên vào dự án” là gì?

Thêm một tài nguyên vào dự án tạo ra một chỗ giữ cho người, thiết bị hoặc vật liệu có thể được gán cho các công việc. Khi tài nguyên đã tồn tại, bạn có thể **đặt khả dụng cho tài nguyên**, xác định lịch làm việc của nó, và cho phép bộ lập lịch tôn trọng các ràng buộc đó.

## Tại sao cấu hình lịch làm việc và các khoảng thời gian khả dụng?

- **Lập kế hoạch chính xác:** Các công việc chỉ được lên lịch khi tài nguyên thực sự rảnh.  
- **Kiểm soát chi phí:** Đơn vị khả dụng phản ánh nỗ lực bán thời gian, giúp bạn tính toán chi phí nhân công một cách chính xác.  
- **Cân bằng tài nguyên:** Công cụ có thể tự động cân bằng các quá tải khi biết lịch của từng tài nguyên.

## Yêu cầu trước

1. Visual Studio (hoặc bất kỳ IDE nào tương thích với .NET).  
2. Aspose.Tasks cho .NET – tải xuống từ [here](https://releases.aspose.com/tasks/net/).  
3. Kiến thức cơ bản về C#.

## Nhập không gian tên

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Cách thêm tài nguyên vào dự án?

### Bước 1: Tạo một thể hiện `Project` mới

```csharp
var project = new Project();
```

Đối tượng này đại diện cho toàn bộ tệp dự án trong bộ nhớ.

### Bước 2: Thêm một tài nguyên vào dự án

```csharp
var resource = project.Resources.Add("Work Resource");
```

Lệnh này tạo một **tài nguyên** có tên *Work Resource* mà bạn có thể gán cho các công việc sau này.

### Bước 3: Xác định các khoảng thời gian khả dụng

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` là một phương thức trợ giúp (cài đặt không được hiển thị) trả về một tập hợp các đối tượng `AvailabilityPeriod`. Mỗi khoảng thời gian chỉ định ngày bắt đầu, ngày kết thúc và đơn vị (phần trăm nỗ lực toàn thời gian) mà tài nguyên có sẵn.

### Bước 4: Thêm các khoảng thời gian vào tài nguyên

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Ở đây chúng ta **đặt khả dụng cho tài nguyên** bằng cách lặp qua tập hợp và thêm mỗi khoảng thời gian vào lịch của tài nguyên.

### Bước 5: Hiển thị chi tiết khả dụng

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Đầu ra console cho phép bạn xác nhận rằng các khoảng thời gian đã được lưu đúng.

## Những lỗi thường gặp & Mẹo

- **Độ chính xác ngày:** `AvailableFrom` và `AvailableTo` là các giá trị `DateTime`; đảm bảo chúng được đặt vào lúc nửa đêm nếu bạn muốn khoảng thời gian toàn ngày.  
- **Phạm vi đơn vị:** Giá trị hợp lệ là 0‑100 %; các giá trị ngoài phạm vi này sẽ gây ra ngoại lệ.  
- **Các khoảng thời gian chồng lấn:** Các khoảng thời gian chồng lấn sẽ được hợp nhất tự động, nhưng nên giữ chúng riêng biệt để rõ ràng hơn.

## Câu hỏi thường gặp

### Q1: Tôi có thể sử dụng Aspose.Tasks cho .NET trong các dự án thương mại không?
A1: Có, Aspose.Tasks cho .NET có thể được sử dụng trong các dự án thương mại. Bạn có thể mua giấy phép [here](https://purchase.aspose.com/buy).

### Q2: Có bản dùng thử miễn phí cho Aspose.Tasks cho .NET không?
A2: Có, bạn có thể nhận bản dùng thử miễn phí của Aspose.Tasks cho .NET [here](https://releases.aspose.com/).

### Q3: Tôi có thể tìm tài liệu cho Aspose.Tasks cho .NET ở đâu?
A3: Bạn có thể tìm tài liệu [here](https://reference.aspose.com/tasks/net/).

### Q4: Làm thế nào để tôi nhận được hỗ trợ cho Aspose.Tasks cho .NET?
A4: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng [here](https://forum.aspose.com/c/tasks/15).

### Q5: Bạn có cung cấp giấy phép tạm thời cho Aspose.Tasks cho .NET không?
A5: Có, giấy phép tạm thời có sẵn [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-04-06  
**Tested With:** Đã kiểm tra với: Aspose.Tasks cho .NET (phiên bản ổn định mới nhất)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}