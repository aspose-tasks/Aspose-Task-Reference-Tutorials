---
date: 2026-04-06
description: Tìm hiểu cách xóa tất cả các baseline và quản lý các bộ sưu tập baseline
  trong Aspose.Tasks cho .NET với các ví dụ mã từng bước.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Xóa tất cả các baseline bằng bộ sưu tập Baseline của Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Xóa tất cả các baseline bằng bộ sưu tập Baseline của Aspose.Tasks
url: /vi/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xóa Tất Cả Các Baseline với Bộ Sưu Tập Baseline của Aspose.Tasks

## Giới thiệu

Aspose.Tasks for .NET cho phép bạn thao tác với các tệp Microsoft Project trực tiếp từ các ứng dụng .NET của mình. Một trong những tính năng mạnh mẽ nhất là khả năng **delete all baselines** cho một tài nguyên, điều này rất cần thiết khi bạn cần đặt lại dữ liệu theo dõi của dự án hoặc bắt đầu một giai đoạn baseline mới. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn toàn bộ quy trình — từ việc tải tệp dự án đến việc loại bỏ mọi baseline gắn với một tài nguyên cụ thể — bằng các giải thích rõ ràng, thân thiện và mã C# sẵn sàng chạy.

## Câu trả lời nhanh
- **“delete all baselines” làm gì?** Nó loại bỏ mọi bản ghi baseline đã lưu cho tài nguyên đã chọn, xóa dữ liệu chi phí và công việc lịch sử.  
- **Tại sao tôi cần điều này?** Để đặt lại việc theo dõi sau một thay đổi lớn của dự án hoặc khi các baseline gốc không còn phù hợp.  
- **Thư viện nào cung cấp khả năng này?** Aspose.Tasks for .NET.  
- **Tôi có cần giấy phép không?** Cần một giấy phép Aspose.Tasks hợp lệ cho việc sử dụng trong môi trường sản xuất; một bản dùng thử miễn phí có sẵn.  
- **Mã có tương thích với .NET 6+ không?** Có, API hoạt động với .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6.

## Baseline là gì và Tại sao phải Xóa Tất Cả Baseline?

Một baseline ghi lại kế hoạch gốc cho chi phí, công việc và lịch trình tại một thời điểm cụ thể. Trong suốt vòng đời của dự án, bạn có thể tạo ra nhiều baseline (Baseline 1, Baseline 2, v.v.) để so sánh tiến độ thực tế với các snapshot kế hoạch khác nhau. Tuy nhiên, có những trường hợp — chẳng hạn như việc thay đổi phạm vi dự án hoặc khởi đầu mới — khi việc giữ các baseline lịch sử trở nên gây nhầm lẫn. Xóa tất cả baseline sẽ cho bạn một khởi đầu sạch sẽ, cho phép bạn thiết lập các baseline mới phản ánh thực tế hiện tại.

## Yêu cầu trước

1. **Visual Studio** – bất kỳ phiên bản gần đây nào (Community, Professional, hoặc Enterprise).  
2. **Aspose.Tasks for .NET** – tải xuống từ [download link](https://releases.aspose.com/tasks/net/).  
3. **Kiến thức cơ bản về C#** – bạn nên quen thuộc với biến, vòng lặp và xuất console.  
4. **Tệp Microsoft Project** (`.mpp`) – một tệp mẫu có tên *WorkWithBaselineCollection.mpp* sẽ được sử dụng trong các ví dụ.

## Nhập các Namespace

Đầu tiên, đưa các namespace cần thiết vào phạm vi để trình biên dịch biết nơi tìm các lớp chúng ta sẽ sử dụng.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Bước 1: Tải tệp Project

Chúng ta bắt đầu bằng việc tải một tệp Project hiện có. Điều chỉnh `DataDir` để trỏ tới thư mục chứa tệp `.mpp` của bạn.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Bước 2: Lấy tài nguyên mục tiêu

Để minh họa, chúng ta lấy tài nguyên có UID = 1. Trong thực tế, bạn sẽ xác định tài nguyên bằng tên hoặc định danh khác.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Bước 3: Hiển thị thông tin Baseline hiện có

Trước khi xóa bất kỳ thứ gì, việc xem các baseline hiện đang gắn với tài nguyên sẽ hữu ích. Điều này giúp bạn chắc chắn rằng mình đang xóa đúng dữ liệu.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Bước 4: Duyệt qua tất cả Baseline

Ở đây chúng ta lặp qua mỗi baseline, in ra các chỉ số chính như chi phí, công việc và giá trị thu được (BCWP/BCWS). Bước này là tùy chọn nhưng hữu ích cho việc ghi log hoặc kiểm toán.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Xóa Tất Cả Baseline

Bây giờ chúng ta thực hiện hành động chính: **delete all baselines** cho tài nguyên đã chọn. Đầu tiên chúng ta sao chép bộ sưu tập vào một danh sách để tránh sửa đổi bộ sưu tập trong khi lặp, sau đó loại bỏ từng baseline một.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Sau khi khối này chạy, `resource.Baselines.Count` sẽ là `0`, xác nhận rằng tất cả bản ghi baseline đã được xóa.

## Vấn đề thường gặp và Mẹo

- **NullReferenceException** – Đảm bảo tệp dự án thực sự chứa tài nguyên bạn đang nhắm tới; nếu không `GetByUid` sẽ trả về `null`.  
- **Licensing** – Nếu không có giấy phép Aspose.Tasks hợp lệ, bạn sẽ thấy watermark trong đầu ra và chức năng bị giới hạn.  
- **Performance** – Đối với các dự án rất lớn, cân nhắc lặp với `Parallel.ForEach` để tăng tốc quá trình xóa, nhưng nhớ rằng bộ sưu tập nền không an toàn với đa luồng.

## Câu hỏi thường gặp

**Q: Có thể Aspose.Tasks xử lý các tệp dự án lớn không?**  
A: Có, Aspose.Tasks được tối ưu hoá cho hiệu năng và có thể xử lý các tệp `.mpp` đa gigabyte một cách hiệu quả.

**Q: Thư viện có tương thích với tất cả các phiên bản Microsoft Project không?**  
A: Aspose.Tasks hỗ trợ Project 2000 đến Project 2024, bao gồm cả các định dạng `.mpp` cũ và các tệp dựa trên XML mới hơn.

**Q: Tôi có thể tùy chỉnh baseline trước khi xóa không?**  
A: Chắc chắn. Bạn có thể đọc hoặc sửa đổi bất kỳ thuộc tính nào của baseline (chi phí, công việc, ngày) trước khi quyết định xóa.

**Q: Aspose.Tasks có hoạt động trên các nền tảng đám mây không?**  
A: Có, API chạy trên bất kỳ môi trường nào tương thích với .NET, bao gồm Azure App Service, AWS Lambda (qua .NET Core), và các container Docker.

**Q: Tôi có thể hỏi cộng đồng để được giúp đỡ ở đâu?**  
A: Truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để kết nối với các nhà phát triển khác và nhân viên Aspose.

## Kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách **delete all baselines** từ một tài nguyên bằng Aspose.Tasks cho .NET. Bằng cách làm theo mã từng bước, bạn có thể đặt lại dữ liệu baseline, giữ cho việc theo dõi dự án của bạn sạch sẽ, và chuẩn bị lịch trình cho một chu kỳ lập kế hoạch mới. Hãy thoải mái thử nghiệm tạo các baseline mới sau khi xóa để xem thư viện cập nhật tệp dự án như thế nào.

---

**Cập nhật lần cuối:** 2026-04-06  
**Kiểm tra với:** Aspose.Tasks 24.12 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}