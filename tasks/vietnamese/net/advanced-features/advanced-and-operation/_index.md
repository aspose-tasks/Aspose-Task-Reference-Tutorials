---
date: 2026-03-16
description: Tìm hiểu cách kết hợp nhiều điều kiện và lọc các nhiệm vụ dự án bằng
  thao tác AND nâng cao trong Aspose.Tasks cho .NET.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: Cách kết hợp nhiều điều kiện với thao tác AND nâng cao trong Aspose.Tasks
url: /vi/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoạt Động AND Nâng Cao trong Aspose.Tasks

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá **cách kết hợp nhiều điều kiện** bằng *hoạt động AND nâng cao* trong Aspose.Tasks cho .NET. Khi kết thúc, bạn sẽ có thể **lọc các task của dự án** dựa trên nhiều tiêu chí—điều này rất quan trọng khi bạn cần **cách lọc task** như các mục tổng hợp, các mục không null, hoặc các cờ tùy chỉnh trong một lần xử lý duy nhất.

## Câu trả lời nhanh
- **Hoạt động AND nâng cao làm gì?** Nó hợp nhất hai hoặc nhiều điều kiện lọc sao cho chỉ những task đáp ứng *tất cả* tiêu chí mới được trả về.  
- **Lớp nào kết hợp các điều kiện?** `Util.And<T>` (được hiển thị dưới dạng `And<T>` trong API).  
- **Tôi có cần giấy phép đặc biệt không?** Cần một giấy phép Aspose.Tasks thường cho môi trường sản xuất; bản dùng thử miễn phí có sẵn.  
- **Tôi có thể nối chuỗi hơn hai điều kiện không?** Có—`And<T>` chấp nhận bất kỳ số lượng điều kiện nào.  
- **Phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## “Kết hợp nhiều điều kiện” trong Aspose.Tasks là gì?

Kết hợp nhiều điều kiện có nghĩa là tạo một bộ lọc tổng hợp đánh giá mỗi task dựa trên nhiều quy tắc đồng thời. Cách tiếp cận này hiệu quả hơn rất nhiều so với việc lặp lại danh sách task nhiều lần vì thư viện áp dụng logic trong một lần duyệt.

## Tại sao nên sử dụng hoạt động AND nâng cao?

- **Hiệu năng:** Giảm số lần duyệt qua bộ sưu tập task.  
- **Độ dễ đọc:** Giữ logic lọc ở dạng khai báo và dễ bảo trì.  
- **Linh hoạt:** Bạn có thể kết hợp các điều kiện tích hợp (ví dụ, `SummaryCondition`) với các predicate tùy chỉnh.  

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. Kiến thức cơ bản về lập trình C#.  
2. Aspose.Tasks cho .NET đã được cài đặt. Nếu chưa tải, hãy lấy **[tại đây](https://releases.aspose.com/tasks/net/)**.  
3. Một IDE như Visual Studio (bất kỳ phiên bản nào cũng được).  

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cung cấp mô hình task và các lớp tiện ích:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## Bước 1: Khởi tạo Project và Thu thập Tasks

Chúng ta sẽ tạo một thể hiện `Project` và sử dụng `ChildTasksCollector` để thu thập mọi task trong file. Điều này minh họa **cách sử dụng collector** để lấy danh sách phẳng các task.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Bước 2: Định nghĩa các Điều kiện Lọc

Ở đây chúng ta định nghĩa các điều kiện riêng lẻ muốn áp dụng. Trong ví dụ này, chúng ta **lọc các task tổng hợp** và đồng thời đảm bảo đối tượng task không null.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Bước 3: Kết hợp các Điều kiện với Hoạt động AND

Bây giờ chúng ta **kết hợp nhiều điều kiện** bằng lớp `And<T>`. Đây là phần cốt lõi của **hoạt động AND nâng cao**.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Bước 4: Áp dụng Điều kiện và Lọc Tasks

Với điều kiện tổng hợp đã sẵn sàng, chúng ta gọi `Filter` để **lọc các task của dự án** dựa trên logic đã kết hợp.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Bước 5: Xuất các Tasks Đã Lọc

Cuối cùng, chúng ta hiển thị các task thỏa mãn **tất cả** các điều kiện. Bạn có thể thay thế các lệnh `Console.WriteLine` bằng bất kỳ xử lý tùy chỉnh nào bạn cần.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Các vấn đề thường gặp và Giải pháp

| Vấn đề | Tại sao lại xảy ra | Khắc phục nhanh |
|-------|-------------------|-----------------|
| Phương thức `Filter` không tìm thấy | Thiếu `using Aspose.Tasks.Util;` | Đảm bảo đã nhập không gian tên Util (xem Nhập không gian tên). |
| Không có task nào được trả về | Các điều kiện quá hạn chế (ví dụ, lọc task tổng hợp khi không có) | Kiểm tra dự án thực sự chứa các task tổng hợp hoặc điều chỉnh các điều kiện. |
| NullReferenceException | `coll.Tasks` chứa các mục null | `NotNullCondition` đã bảo vệ khỏi trường hợp này; giữ nó trong chuỗi AND. |

## Câu hỏi thường gặp

### Q1: Aspose.Tasks cho .NET là gì?

A: Aspose.Tasks cho .NET là một API mạnh mẽ cho phép các nhà phát triển thao tác các file Microsoft Project một cách lập trình trong các ứng dụng .NET.

### Q2: Tôi có thể áp dụng hơn hai điều kiện bằng Util.And không?

A: Có, Util.And có thể được dùng để kết hợp bất kỳ số lượng điều kiện nào nhằm tạo ra tiêu chí lọc phức tạp.

### Q3: Có bản dùng thử miễn phí cho Aspose.Tasks cho .NET không?

A: Có, bạn có thể tải bản dùng thử miễn phí **[tại đây](https://releases.aspose.com/)**.

### Q4: Tôi có thể tìm tài liệu cho Aspose.Tasks cho .NET ở đâu?

A: Bạn có thể tìm tài liệu **[tại đây](https://reference.aspose.com/tasks/net/)**.

### Q5: Làm sao để nhận hỗ trợ cho Aspose.Tasks cho .NET?

A: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks **[tại đây](https://forum.aspose.com/c/tasks/15)**.

**Câu hỏi & Trả lời bổ sung**

**Hỏi: Làm sao để lọc task theo giá trị trường tùy chỉnh?**  
Đáp: Tạo một `CustomFieldCondition` (hoặc triển khai `ICondition<Task>`) và thêm nó vào chuỗi `And<T>`.

**Hỏi: Tôi có thể dùng cùng cách tiếp cận này để lọc tài nguyên không?**  
Đáp: Có—thay `Task` bằng `Resource` và sử dụng các lớp điều kiện tương ứng.

## Kết luận

Bằng cách thực hiện các bước trên, bạn đã biết **cách kết hợp nhiều điều kiện** bằng **hoạt động AND nâng cao** trong Aspose.Tasks cho .NET. Kỹ thuật này cho phép bạn **lọc các task của dự án** một cách hiệu quả, dù bạn đang nhắm tới các mục tổng hợp, các mục không null, hoặc bất kỳ tiêu chí tùy chỉnh nào bạn định nghĩa.

---

**Cập nhật lần cuối:** 2026-03-16  
**Đã kiểm tra với:** Aspose.Tasks cho .NET (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}