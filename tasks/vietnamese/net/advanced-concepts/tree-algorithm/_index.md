---
date: 2026-03-19
description: Tìm hiểu cách thêm nguồn lực vào dự án, tính thời gian thực hiện nhiệm
  vụ bằng Thuật toán Cây của Aspose.Tasks và gán nguồn lực cho các nhiệm vụ trong
  .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Thêm tài nguyên vào dự án bằng thuật toán cây trong Aspose.Tasks
url: /vi/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm tài nguyên vào dự án với thuật toán cây trong Aspose.Tasks

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá **cách thêm tài nguyên vào dự án** bằng cách tận dụng Thuật toán Cây mạnh mẽ được cung cấp bởi Aspose.Tasks cho .NET. Chúng tôi sẽ hướng dẫn cách tạo cấu trúc nhiệm vụ, tính thời lượng nhiệm vụ và gán tài nguyên cho các nhiệm vụ — tất cả theo cách rõ ràng, từng bước mà bạn có thể sao chép vào giải pháp của mình.

## Câu trả lời nhanh
- **Thuật toán Cây làm gì?** Nó duyệt qua cấu trúc nhiệm vụ để tổng hợp giá trị công việc một cách hiệu quả.  
- **Hoạt động chính mà hướng dẫn này đề cập là gì?** Thêm tài nguyên vào dự án và cập nhật tổng công việc.  
- **Tôi có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất.  
- **Tôi có thể sử dụng với .NET Core không?** Có, Aspose.Tasks hỗ trợ .NET Framework và .NET Core.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một tệp dự án cơ bản.

## “Thêm tài nguyên vào dự án” là gì trong Aspose.Tasks?

Thêm một tài nguyên vào dự án có nghĩa là tạo một đối tượng `Resource`, xác định loại của nó (ví dụ: work), và liên kết nó với một hoặc nhiều nhiệm vụ thông qua `ResourceAssignments`. Điều này cho phép bộ lập lịch tính toán nỗ lực, chi phí và thời lượng tổng thể của dự án.

## Tại sao nên sử dụng Thuật toán Cây cho việc tính toán công việc của tài nguyên?

Thuật toán Cây duyệt cây nhiệm vụ một lần, tích lũy công việc từ các nhiệm vụ lá lên các nhiệm vụ tổng hợp. Cách tiếp cận này hiệu quả hơn rất nhiều so với việc lặp qua từng nhiệm vụ riêng lẻ, đặc biệt trong các dự án lớn có cấu trúc sâu. Nó cũng đảm bảo các giá trị công việc tổng hợp luôn đồng bộ với các nhiệm vụ con.

## Yêu cầu trước

1. **Visual Studio** – bất kỳ phiên bản mới nào (2019, 2022, hoặc mới hơn).  
2. **Aspose.Tasks for .NET** – tải xuống từ [tại đây](https://releases.aspose.com/tasks/net/).  
3. **Kiến thức cơ bản về C#** – bạn nên quen thuộc với các lớp, đối tượng và LINQ đơn giản.

## Nhập không gian tên

Trong dự án C# của bạn, nhập các không gian tên cần thiết để làm việc với các chức năng của Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Bây giờ, chúng ta sẽ phân tích từng ví dụ thành nhiều bước:

## Bước 1: Tải tệp dự án

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Tải tệp dự án vào bộ nhớ bằng cách sử dụng lớp `Project`.

## Bước 2: Định nghĩa cấu trúc nhiệm vụ

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Định nghĩa cấu trúc nhiệm vụ bằng cách thêm các nhiệm vụ cha và con.

## Bước 3: Đặt thuộc tính nhiệm vụ (bao gồm **tính thời lượng nhiệm vụ**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Ở đây chúng ta **tính thời lượng nhiệm vụ** bằng cách chuyển đổi giờ làm việc thành một đối tượng `Duration` và sau đó suy ra ngày hoàn thành.

## Bước 4: Thêm tài nguyên (**gán tài nguyên cho nhiệm vụ**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Đoạn mã này **thêm một tài nguyên vào dự án** và **gán tài nguyên cho các nhiệm vụ** để bộ lập lịch biết ai chịu trách nhiệm cho công việc.

## Bước 5: Áp dụng Thuật toán Cây

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Khởi tạo lớp `WorkAccumulator` và áp dụng Thuật toán Cây để thu thập công việc chung trên toàn bộ cấu trúc.

## Bước 6: Cập nhật công việc nhiệm vụ

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Cập nhật các giá trị công việc cho các nhiệm vụ dựa trên thông tin đã thu thập.

## Các vấn đề thường gặp & Mẹo

- **Thiếu cài đặt lịch:** Nếu ngày hoàn thành không đúng, hãy đảm bảo lịch dự án được cấu hình chính xác trước khi gọi `GetFinishDateByStartAndWork`.  
- **Không khớp loại tài nguyên:** Luôn đặt `Rsc.Type` thành `ResourceType.Work` cho các tài nguyên dựa trên nỗ lực; nếu không, việc tích lũy công việc có thể trả về 0.  
- **Mẹo chuyên nghiệp:** Sau khi cập nhật công việc, gọi `project.Save("UpdatedProject.mpp")` để lưu các thay đổi.

## Kết luận

Bằng cách thực hiện các bước này, bạn đã biết cách **thêm tài nguyên vào dự án**, **tính thời lượng nhiệm vụ**, và **gán tài nguyên cho nhiệm vụ** bằng Thuật toán Cây của Aspose.Tasks. Phương pháp này giúp quản lý cấu trúc một cách hiệu quả và giữ cho các giá trị công việc tổng hợp luôn chính xác với ít mã nhất.

## Câu hỏi thường gặp

### Q1: Aspose.Tasks cho .NET là gì?

A1: Aspose.Tasks cho .NET là một API mạnh mẽ cho phép các nhà phát triển thao tác các tệp Microsoft Project một cách lập trình bằng C#.

### Q2: Tôi có thể tải bản dùng thử miễn phí của Aspose.Tasks cho .NET không?

A2: Có, bạn có thể tải bản dùng thử miễn phí của Aspose.Tasks cho .NET từ [tại đây](https://releases.aspose.com/).

### Q3: Tôi có thể tìm tài liệu cho Aspose.Tasks cho .NET ở đâu?

A3: Bạn có thể tìm tài liệu cho Aspose.Tasks cho .NET [tại đây](https://reference.aspose.com/tasks/net/).

### Q4: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Tasks cho .NET?

A4: Để được hỗ trợ liên quan đến Aspose.Tasks cho .NET, bạn có thể truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Có giấy phép tạm thời nào cho mục đích thử nghiệm không?

A5: Có, bạn có thể nhận giấy phép tạm thời cho mục đích thử nghiệm từ [tại đây](https://purchase.aspose.com/temporary-license/).

## Các câu hỏi thường gặp

**Q: Tôi có thể sử dụng cách tiếp cận này với một tệp dự án lớn hiện có không?**  
A: Chắc chắn. Thuật toán Cây hoạt động trên bất kỳ đối tượng `Project` nào, bất kể kích thước.

**Q: Thuật toán có cập nhật giá trị chi phí không?**  
A: Ví dụ tập trung vào công việc, nhưng bạn có thể mở rộng để tính chi phí bằng cách tích lũy `Tsk.Cost` theo cách tương tự.

**Q: Các phiên bản .NET nào được hỗ trợ?**  
A: Aspose.Tasks hỗ trợ .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ và .NET 6+.

**Q: Làm sao tôi xử lý nhiều tài nguyên cho một nhiệm vụ?**  
A: Thêm mỗi tài nguyên bằng `project.ResourceAssignments.Add(task, resource)`; bộ tích lũy sẽ tự động cộng tổng công việc của chúng.

---

**Cập nhật lần cuối:** 2026-03-19  
**Đã kiểm tra với:** Aspose.Tasks 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}