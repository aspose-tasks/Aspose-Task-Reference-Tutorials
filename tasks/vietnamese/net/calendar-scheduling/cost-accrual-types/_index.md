---
date: 2026-07-05
description: Tìm hiểu cách theo dõi ngân sách dự án và quản lý chi phí dự án bằng
  Aspose.Tasks cho .NET. Xác định các loại tích lũy chi phí để theo dõi chi phí một
  cách chính xác.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Các loại tích lũy chi phí trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Theo dõi ngân sách dự án với các loại tích lũy chi phí trong Aspose.Tasks
url: /vi/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Theo dõi ngân sách dự án với các loại tích luỹ chi phí trong Aspose.Tasks

## Giới thiệu

Việc **theo dõi ngân sách dự án** một cách chính xác là nền tảng cho việc triển khai dự án thành công. Khi thông tin chi phí được ghi lại vào những thời điểm thích hợp, bạn có thể dự báo vượt chi phí, điều chỉnh nguồn lực và thông báo cho các bên liên quan. Aspose.Tasks cho .NET cung cấp cho nhà phát triển khả năng kiểm soát chi tiết việc tích luỹ chi phí, cho phép bạn quyết định *khi nào* chi phí được ghi nhận—đó có thể là khi bắt đầu công việc, liên tục, hoặc chỉ khi công việc hoàn thành. Hướng dẫn này sẽ đưa bạn qua các khái niệm, chỉ cách thiết lập loại tích luỹ, và trình bày các thực tiễn tốt nhất để theo dõi ngân sách một cách đáng tin cậy.

## Câu trả lời nhanh
- **Mục đích chính của các loại tích luỹ chi phí là gì?** Chúng xác định thời điểm trong vòng đời của một nhiệm vụ khi chi phí được công nhận, cho phép theo dõi ngân sách một cách chính xác.  
- **Giá trị enum nào trì hoãn chi phí cho đến khi công việc hoàn thành?** `CostAccrualType.End`.  
- **Tôi có cần giấy phép để chạy mã không?** Có, cần một giấy phép Aspose.Tasks hợp lệ để sử dụng trong môi trường sản xuất.  
- **Tôi có thể thay đổi loại tích luỹ cho nhiều tài nguyên cùng lúc không?** Có—lặp qua bộ sưu tập `Resources` và gán loại mong muốn.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Loại tích luỹ chi phí là gì?
Một **loại tích luỹ chi phí** cho Aspose.Tasks biết khi nào áp dụng chi phí của tài nguyên vào ngân sách dự án. Nó được biểu diễn bằng enumeration `CostAccrualType` và có thể được đặt cho từng tài nguyên hoặc từng nhiệm vụ. Việc chọn loại phù hợp đảm bảo dữ liệu chi phí phù hợp với chính sách thanh toán của tổ chức bạn, cho dù bạn cần chi phí được ghi nhận khi bắt đầu công việc, tính theo tỷ lệ trong suốt thời gian, hoặc chỉ sau khi hoàn thành.

## Tại sao cần theo dõi ngân sách dự án bằng các loại tích luỹ chi phí?
Aspose.Tasks hỗ trợ **bốn** tùy chọn tích luỹ—`Start`, `Prorated`, `Duration`, và `End`—bao phủ toàn bộ các kịch bản kế toán dự án thường gặp. Lựa chọn tùy chọn phù hợp cho phép bạn đồng bộ việc công nhận chi phí với chu kỳ thanh toán hợp đồng, giảm biến động trong báo cáo tài chính, và tạo báo cáo chi phí tích hợp mượt mà với hệ thống ERP, đồng thời giữ mức sử dụng bộ nhớ thấp cho các dự án lớn.

## Các yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã đáp ứng các yêu cầu sau:

### 1. Cài đặt Aspose.Tasks cho .NET
Để bắt đầu, bạn cần cài đặt Aspose.Tasks cho .NET trong môi trường phát triển của mình. Bạn có thể tải thư viện từ [trang tải xuống](https://releases.aspose.com/tasks/net/) và làm theo hướng dẫn cài đặt được cung cấp.

### 2. Kiến thức cơ bản về .NET Framework
Bạn cần có kiến thức cơ bản về .NET framework và ngôn ngữ lập trình C# để theo dõi các ví dụ trong hướng dẫn này.

## Cách thiết lập Loại tích luỹ chi phí cho một tài nguyên?

Tải dự án, xác định tài nguyên mục tiêu, và gán `CostAccrualType` mong muốn. Mẫu hai dòng dưới đây là cách tiếp cận tiêu chuẩn: tạo một thể hiện `Project`, lấy tài nguyên theo ID, sau đó đặt `CostAccrualType`. Chuỗi ngắn gọn này đảm bảo bạn **theo dõi ngân sách dự án** một cách chính xác ngay từ khi tài nguyên được thêm vào.

### Bước 1: Nhập các namespace
Hãy bắt đầu bằng việc nhập các namespace cần thiết để truy cập chức năng Aspose.Tasks trong dự án .NET của chúng ta:

```csharp

```

Bây giờ chúng ta đã có các namespace sẵn sàng, chúng ta có thể tiếp tục tải tệp dự án.

### Bước 2: Tải tệp dự án
Lớp `Project` đại diện cho một tệp Microsoft Project và cung cấp quyền truy cập vào các nhiệm vụ, tài nguyên và dữ liệu khác.

```csharp
var project = new Project("Project2.mpp");
```

Đầu tiên, chúng ta cần tải tệp dự án vào ứng dụng. Chúng ta tạo một đối tượng `Project` mới và khởi tạo nó với đường dẫn tới tệp dự án của chúng ta.

### Bước 3: Truy cập tài nguyên
Bộ sưu tập `Resources` chứa tất cả các tài nguyên được định nghĩa trong dự án. Phương thức `GetById` lấy một tài nguyên theo định danh duy nhất của nó.

```csharp
var resource = project.Resources.GetById(1);
```

Tiếp theo, chúng ta truy cập tài nguyên mà chúng ta muốn áp dụng loại tích luỹ chi phí. Chúng ta sử dụng phương thức `GetById` của bộ sưu tập `Resources` và truyền ID tài nguyên làm đối số. Điều này minh họa **truy cập tài nguyên theo id**, một yêu cầu phổ biến khi tự động cập nhật chi phí.

### Bước 4: Đặt Loại tích luỹ chi phí
Phương thức `Set` gán một giá trị cho trường của tài nguyên.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Ở đây, chúng ta đặt loại tích luỹ chi phí cho tài nguyên. Trong ví dụ này, chúng ta đặt nó thành `CostAccrualType.End`, có nghĩa là chi phí sẽ không được tích luỹ cho đến khi công việc còn lại bằng không. Chọn `End` là lý tưởng khi bạn muốn **theo dõi ngân sách dự án** chỉ sau khi một nhiệm vụ được hoàn thành đầy đủ.

### Bước 5: Tiếp tục làm việc với dự án
Sau khi đặt loại tích luỹ chi phí, bạn có thể tiếp tục làm việc với dự án theo nhu cầu, thực hiện các thao tác hoặc tính toán bổ sung như tạo báo cáo chi phí, cập nhật phân công, hoặc xuất tệp.

## Các lỗi thường gặp và mẹo chuyên nghiệp
- **Mẹo chuyên nghiệp:** Luôn gọi `project.Save` sau khi thay đổi loại tích luỹ để lưu các thay đổi.  
- **Cạm bẫy:** Đặt `CostAccrualType.Start` cho một tài nguyên không bao giờ bắt đầu công việc sẽ làm tăng báo cáo ngân sách—hãy kiểm tra lịch trình nhiệm vụ trước.  
- **Mẹo chuyên nghiệp:** Sử dụng `project.Resources.ToList()` khi bạn cần cập nhật hàng loạt nhiều tài nguyên; điều này tránh việc tra cứu bộ sưu tập lặp lại và cải thiện hiệu suất trên các dự án lớn.

## Câu hỏi thường gặp

**Q: Tôi có thể thay đổi loại tích luỹ chi phí cho nhiều tài nguyên cùng lúc không?**  
A: Có, lặp qua `project.Resources` và gán `CostAccrualType` mong muốn cho mỗi tài nguyên trong một vòng lặp `foreach`.

**Q: Các loại tích luỹ chi phí khác ngoài `End` là gì?**  
A: Aspose.Tasks cung cấp `Start`, `Prorated`, và `Duration`—mỗi loại phù hợp với một chiến lược thanh toán khác nhau.

**Q: Làm sao tôi có thể xác định loại tích luỹ chi phí hiện tại cho một tài nguyên cụ thể?**  
A: Lấy giá trị bằng `resource.Get(TskResource.CostAccrualType)`; nó trả về enum đại diện cho cài đặt hiện tại.

**Q: Có thể áp dụng các loại tích luỹ chi phí khác nhau cho các nhiệm vụ khác nhau trong cùng một dự án không?**  
A: Chắc chắn. Cả nhiệm vụ và tài nguyên đều có thuộc tính `CostAccrualType`, cho phép cấu hình độc lập cho mỗi thực thể.

**Q: Aspose.Tasks có hỗ trợ các loại tích luỹ chi phí tùy chỉnh không?**  
A: Không, thư viện hiện chỉ hỗ trợ bốn loại tích luỹ có sẵn; logic tùy chỉnh phải được triển khai bên ngoài nếu cần.

---

**Cập nhật lần cuối:** 2026-07-05  
**Kiểm tra với:** Aspose.Tasks 24.8 for .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Lịch và Lập lịch Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Xử lý mức giá MS Project với Aspose.Tasks cho .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Quản lý tài nguyên MS Project một cách dễ dàng với Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}