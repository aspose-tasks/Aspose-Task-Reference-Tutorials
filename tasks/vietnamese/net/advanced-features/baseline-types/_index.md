---
date: 2026-04-30
description: Tìm hiểu cách thiết lập baseline và thao tác với các baseline dự án một
  cách hiệu quả bằng cách sử dụng Aspose.Tasks cho .NET.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Các loại baseline khác nhau trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cách thiết lập Baseline trong Aspose.Tasks – Các loại Baseline khác nhau
url: /vi/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Các loại baseline khác nhau trong Aspose.Tasks

## Giới thiệu

Trong quản lý dự án, **cách thiết lập baseline** đúng có thể tạo ra sự khác biệt giữa một dự án duy trì đúng tiến độ và một dự án mất kiểm soát. Aspose.Tasks cho .NET cung cấp cho bạn một API đầy đủ tính năng để tạo, cập nhật và so sánh các baseline, cho phép bạn **theo dõi tiến độ dự án** so với kế hoạch ban đầu. Trong hướng dẫn này, bạn sẽ học cách thiết lập một baseline, làm việc với nhiều loại baseline, và sử dụng dữ liệu để phân tích **baseline so với lịch trình thực tế** của dự án.

## Câu trả lời nhanh
- **Baseline là gì?** Một bản chụp nhanh của lịch trình, chi phí và dữ liệu công việc được lấy tại một thời điểm cụ thể trong dự án.  
- **Aspose.Tasks có thể lưu bao nhiêu baseline?** Tối đa 11 baseline riêng biệt cho mỗi dự án.  
- **Tại sao cần thiết lập baseline?** Để so sánh hiệu suất thực tế với kế hoạch ban đầu và xác định các sai lệch.  
- **Có cần giấy phép để thử không?** Bản dùng thử miễn phí có sẵn; giấy phép cần thiết cho việc sử dụng trong môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “Cách thiết lập baseline” trong Aspose.Tasks là gì?
Thiết lập một baseline có nghĩa là gọi phương thức `SetBaseline` trên một đối tượng `Project`. API cho phép bạn chọn từ nhiều giá trị `BaselineType` (Baseline, Baseline1 … Baseline10) để bạn có thể giữ các bản chụp lịch sử khi dự án phát triển.

## Tại sao quản lý baseline dự án?
- **Đo lường sai lệch:** Nhanh chóng xem các công việc có đang tiến trước hay trễ so với lịch trình.  
- **Kiểm soát chi phí:** So sánh chi phí baseline với chi phí thực tế.  
- **Báo cáo cho các bên liên quan:** Xuất dữ liệu baseline ra PDF, XLSX hoặc các định dạng khác để giao tiếp rõ ràng.  
- **Lập kế hoạch kịch bản:** Lưu nhiều baseline để đánh giá các lịch trình “nếu‑vậy”.

## Yêu cầu trước

### 1. Hiểu biết về C# và .NET Framework
Cần có kiến thức cơ bản về các lớp C#, phương thức và các khái niệm lập trình hướng đối tượng.

### 2. Cài đặt Aspose.Tasks cho .NET
Đảm bảo thư viện đã được thêm vào dự án của bạn. Bạn có thể tải xuống từ [trang web Aspose.Tasks](https://releases.aspose.com/tasks/net/) hoặc cài đặt qua NuGet.

### 3. Môi trường phát triển tích hợp (IDE)
Visual Studio (hoặc bất kỳ IDE tương thích nào) được khuyến nghị để viết, biên dịch và gỡ lỗi mã C#.

## Nhập không gian tên

Trước khi chúng ta bắt đầu làm việc với Aspose.Tasks trong dự án C# của mình, chúng ta cần nhập các không gian tên cần thiết để truy cập các lớp và phương thức yêu cầu. Thực hiện các bước sau:

```csharp

```

Bây giờ chúng ta đã thiết lập các yêu cầu trước và nhập các không gian tên cần thiết, hãy đi sâu vào việc thiết lập các loại baseline khác nhau bằng Aspose.Tasks cho .NET. Chúng tôi sẽ chia mỗi ví dụ thành nhiều bước để dễ hiểu và rõ ràng.

## Cách thiết lập baseline trong Aspose.Tasks

### Bước 1: Tải tệp dự án
Đầu tiên, chúng ta cần tải tệp dự án mà chúng ta dự định thiết lập baseline. Bước này bao gồm việc khởi tạo một đối tượng `Project` và tải tệp dự án. Dưới đây là cách thực hiện:

```csharp
var project = new Project("Project2.mpp");
```

### Bước 2: Thiết lập baseline
Sau khi dự án đã được tải, chúng ta có thể tiến hành thiết lập baseline. Baseline cung cấp một bản chụp nhanh của lịch trình ban đầu của dự án, đóng vai trò là điểm tham chiếu để so sánh khi dự án tiến triển. Sử dụng phương thức `SetBaseline` để thiết lập baseline. Ví dụ, để thiết lập baseline cho toàn bộ dự án, sử dụng liệt kê `BaselineType.Baseline`:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### Bước 3: Làm việc với các baseline của dự án
Sau khi thiết lập baseline, bạn có thể làm việc với các trường baseline của dự án để phân tích và theo dõi tiến độ dự án một cách chính xác. Bước này bao gồm việc truy cập dữ liệu baseline như ngày bắt đầu, ngày kết thúc, thời lượng và chi phí. Đây là nơi bạn có thể tận dụng bộ tính năng phong phú do Aspose.Tasks cung cấp để thao tác dữ liệu baseline theo yêu cầu của mình.

## Các vấn đề thường gặp và giải pháp
- **Baseline không được áp dụng:** Đảm bảo tệp dự án được lưu sau khi gọi `SetBaseline`. Sử dụng `project.Save("output.mpp");` nếu bạn cần lưu các thay đổi.  
- **Xung đột khi có nhiều baseline:** Khi thiết lập hơn một baseline, chỉ định `BaselineType` đúng (ví dụ, `Baseline1`, `Baseline2`).  
- **Không khớp phiên bản:** Xác minh rằng phiên bản DLL của Aspose.Tasks phù hợp với môi trường .NET mục tiêu.

## Câu hỏi thường gặp

**Q: Tôi có thể thiết lập nhiều baseline cho một dự án duy nhất bằng Aspose.Tasks cho .NET không?**  
A: Có, Aspose.Tasks cho phép bạn thiết lập tối đa 11 baseline cho một dự án, cung cấp khả năng theo dõi toàn diện.

**Q: Aspose.Tasks có tương thích với các định dạng tệp dự án khác nhau không?**  
A: Chắc chắn! Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án như MPP, XML và MPX, đảm bảo khả năng tương thích trên các nền tảng khác nhau.

**Q: Làm sao tôi có thể trực quan hóa dữ liệu baseline trong dự án của mình?**  
A: Bạn có thể sử dụng Aspose.Tasks để xuất dữ liệu dự án ra các định dạng phổ biến như PDF hoặc XLSX, giúp dễ dàng trực quan hóa và chia sẻ thông tin baseline.

**Q: Aspose.Tasks có hỗ trợ tích hợp với các công cụ quản lý dự án không?**  
A: Aspose.Tasks cung cấp tài liệu chi tiết và diễn đàn hỗ trợ để giúp các nhà phát triển tích hợp các tính năng của nó một cách liền mạch với các công cụ và nền tảng quản lý dự án phổ biến.

**Q: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?**  
A: Có, bạn có thể khám phá Aspose.Tasks qua bản dùng thử miễn phí có trên trang web, cho phép bạn trải nghiệm các khả năng của nó trực tiếp.

---

**Cập nhật lần cuối:** 2026-04-30  
**Kiểm tra với:** Aspose.Tasks cho .NET (phiên bản ổn định mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}