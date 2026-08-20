---
date: 2026-03-14
description: Tìm hiểu cách lọc các tác vụ không phải là hoạt động trong Aspose.Tasks
  cho .NET và khám phá cách sử dụng bộ lọc NOT với điều kiện áp dụng NOT để thực hiện
  các truy vấn tác vụ linh hoạt.
linktitle: Working with NOT Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Lọc các tác vụ không phải là hoạt động trong Aspose.Tasks
url: /vi/net/advanced-concepts/not-operation/
weight: 20
---

}}

All good.

Now produce final content with translations. Ensure markdown formatting preserved.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# lọc tác vụ không hoạt động trong Aspose.Tasks

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học **cách lọc tác vụ không hoạt động** bằng Aspose.Tasks cho .NET. Phép NOT cho phép bạn đảo ngược một điều kiện lọc để có thể chọn mọi tác vụ **không** đáp ứng một tiêu chí cụ thể. Khả năng này rất quan trọng khi bạn cần loại trừ một số mục—như các tác vụ không có giá trị—hoặc khi bạn muốn xây dựng các truy vấn phức tạp mà không phải viết thêm mã.

## Câu trả lời nhanh
- **NOT operation làm gì?** Nó đảo ngược một điều kiện lọc, trả về các mục không đáp ứng kiểm tra ban đầu.  
- **Tại sao sử dụng lọc tác vụ không hoạt động?** Nó đơn giản hoá logic loại trừ và giữ cho mã của bạn dễ đọc.  
- **Namespace nào cung cấp lớp NOT?** `Aspose.Tasks.Util`.  
- **Tôi có cần giấy phép cho môi trường production không?** Có, cần giấy phép Aspose.Tasks hợp lệ cho việc sử dụng không phải thử nghiệm.  
- **Tôi có thể kết hợp NOT với các điều kiện khác không?** Chắc chắn—có thể kết hợp với `AndCondition`, `OrCondition`, v.v.

## Lọc tác vụ không hoạt động là gì?
**Lọc tác vụ không hoạt động** là một phép phủ định logic được áp dụng lên bộ lọc tác vụ. Thay vì chọn các tác vụ khớp với một điều kiện, nó chọn những tác vụ *không* khớp. Điều này rất hữu ích khi bạn muốn bỏ qua các tác vụ có trường trống, trạng thái cụ thể, hoặc bất kỳ thuộc tính nào bạn muốn loại trừ.

## Tại sao áp dụng điều kiện NOT khi lọc tác vụ?
Áp dụng **điều kiện NOT** giảm nhu cầu thực hiện nhiều lần duyệt dữ liệu dự án. Nó cho phép bạn viết mã ngắn gọn, dễ bảo trì và cải thiện hiệu năng bằng cách giao việc đánh giá cho engine tối ưu của Aspose.Tasks.

## Yêu cầu trước

1. **Visual Studio:** Bạn cần cài đặt Visual Studio hoạt động để theo dõi các ví dụ mã.  
2. **Aspose.Tasks for .NET:** Tải xuống và cài đặt thư viện Aspose.Tasks cho .NET từ [website](https://releases.aspose.com/tasks/net/).  
3. **Kiến thức cơ bản về C#:** Hiểu biết về ngôn ngữ lập trình C# sẽ hữu ích trong việc nắm bắt các ví dụ mã.

## Nhập các Namespace

Đầu tiên, hãy nhập các namespace cần thiết cho mã của chúng ta:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Bước 1: Thiết lập Dự án và Các tác vụ

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

Chúng ta bắt đầu bằng cách tải một tệp dự án có tên **Project2.mpp** bằng lớp `Project` do Aspose.Tasks cung cấp. Đảm bảo tệp dự án tồn tại trong thư mục đã chỉ định.

## Bước 2: Thu thập các tác vụ của dự án

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

Ở đây, chúng ta tạo một đối tượng `ChildTasksCollector` để thu thập tất cả các tác vụ trong dự án. Sau đó sử dụng `TaskUtils.Apply` để duyệt qua cây phân cấp tác vụ của dự án và thu thập mọi tác vụ con.

## Bước 3: Định nghĩa Điều kiện Lọc

```csharp
var filter = new NullCondition();
```

Chúng ta định nghĩa một điều kiện lọc bằng lớp tùy chỉnh `NullCondition`. Điều kiện này chọn các tác vụ có giá trị **null**.  

> **Pro tip:** Thay thế `NullCondition` bằng bất kỳ điều kiện nào khác (ví dụ: `EqualsCondition`) để nhắm tới các thuộc tính khác nhau.

## Bước 4: Áp dụng phép NOT

```csharp
var condition = new Not<Task>(filter);
```

Chúng ta áp dụng **phép NOT** lên điều kiện lọc bằng lớp `Not<T>` do Aspose.Tasks cung cấp. Điều này đảo ngược điều kiện gốc, vì vậy bộ lọc hiện nay sẽ chọn các tác vụ **không** có giá trị null. Đây là cốt lõi của kỹ thuật **cách sử dụng bộ lọc NOT**.

## Bước 5: Lọc các tác vụ

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

Chúng ta lọc các tác vụ đã thu thập dựa trên điều kiện đã áp dụng bằng phương thức tùy chỉnh `Filter`. Phương thức nhận một tập hợp các tác vụ có thể lặp lại và một điều kiện lọc, trả về danh sách các tác vụ thỏa mãn **điều kiện áp dụng NOT**.

## Bước 6: Xử lý các tác vụ đã lọc

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Work with other properties...
}
```

Cuối cùng, chúng ta duyệt qua các tác vụ đã lọc và thực hiện bất kỳ thao tác nào mong muốn. Trong ví dụ này, chúng ta chỉ in tên các tác vụ ra console, nhưng bạn có thể mở rộng khối này để cập nhật trường, di chuyển tác vụ, hoặc tạo báo cáo.

## Các trường hợp sử dụng phổ biến

- **Loại trừ các tác vụ đã hoàn thành** khi tạo danh sách công việc đang chờ.  
- **Tìm các tác vụ thiếu trường tùy chỉnh** (ví dụ: cột “Owner” null).  
- **Kết hợp với các điều kiện khác** để xây dựng các truy vấn phức tạp, chẳng hạn “các tác vụ không null và có ngày bắt đầu trước hôm nay”.

## Khắc phục sự cố & Mẹo

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| Không có tác vụ nào được trả về | Điều kiện gốc có thể quá hạn chế. | Kiểm tra logic của điều kiện hoặc thử với bộ lọc đơn giản hơn như `new TrueCondition()`. |
| `NullReferenceException` | Đường dẫn `DataDir` không đúng. | Đảm bảo `DataDir` trỏ tới thư mục chứa *Project2.mpp*. |
| Kết quả không mong đợi | Kết hợp `Not<T>` với các điều kiện khác không đúng cách. | Sử dụng dấu ngoặc: `new AndCondition(new Not<Task>(filter), otherCondition)`. |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks với các framework .NET khác không?**  
A: Có, Aspose.Tasks hỗ trợ .NET Core, .NET Standard và .NET Framework truyền thống.

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks không?**  
A: Có, bạn có thể tải bản dùng thử miễn phí từ [website](https://releases.aspose.com/).

**Q: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Tasks?**  
A: Bạn có thể truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để đặt câu hỏi hỗ trợ hoặc nhận trợ giúp kỹ thuật.

**Q: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks không?**  
A: Có, bạn có thể mua giấy phép tạm thời từ [trang mua hàng](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm tài liệu đầy đủ cho Aspose.Tasks ở đâu?**  
A: Bạn có thể truy cập tài liệu đầy đủ trên [trang tài liệu Aspose.Tasks](https://reference.aspose.com/tasks/net/).

## Kết luận

Bằng cách nắm vững **lọc tác vụ không hoạt động** và học **cách sử dụng bộ lọc NOT** với **điều kiện áp dụng NOT**, bạn sẽ có khả năng kiểm soát chi tiết việc lựa chọn tác vụ trong Aspose.Tasks. Điều này giúp bạn viết mã sạch hơn, tránh việc loại trừ thủ công và xây dựng các công cụ quản lý dự án mạnh mẽ.

---

**Cập nhật lần cuối:** 2026-03-14  
**Kiểm tra với:** Aspose.Tasks 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}