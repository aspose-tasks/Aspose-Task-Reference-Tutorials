---
title: Thu thập số liệu thống kê về mục rủi ro của dự án MS trong Aspose.Tasks
linktitle: Thu thập số liệu thống kê về mục rủi ro trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thu thập số liệu thống kê về mục rủi ro từ các tệp MS Project bằng Aspose.Tasks cho .NET. Nâng cao khả năng quản lý dự án của bạn.
weight: 22
url: /vi/net/resource-risk-analysis/risk-item-statistics-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thu thập số liệu thống kê về mục rủi ro của dự án MS trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách thu thập số liệu thống kê về mục rủi ro từ các tệp MS Project bằng Aspose.Tasks cho .NET. Thư viện này cung cấp các chức năng mạnh mẽ để phân tích dữ liệu dự án, bao gồm đánh giá rủi ro và phân tích thống kê.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks. Bạn có thể lấy nó từ[trang tải xuống](https://releases.aspose.com/tasks/net/).
2. Môi trường phát triển: Có môi trường phát triển được thiết lập cho lập trình .NET.

## Nhập không gian tên
Trước khi bắt đầu viết mã, hãy đảm bảo nhập các không gian tên cần thiết trong dự án của bạn:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Bước 1: Tải tệp dự án
Trước tiên, bạn cần tải tệp MS Project vào ứng dụng của mình. Đây là cách bạn có thể đạt được nó:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Bước 2: Xác định cài đặt phân tích rủi ro
Khởi tạo cài đặt phân tích rủi ro, bao gồm số lần lặp, như minh họa bên dưới:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Bước 3: Khởi tạo mẫu rủi ro
Thiết lập mô hình rủi ro để phân tích, chỉ định loại phân phối, tỷ lệ phần trăm lạc quan và bi quan cũng như mức độ tin cậy:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Bước 4: Thực hiện phân tích rủi ro
 Khởi tạo`RiskAnalyzer` lớp và phân tích dự án:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Bước 5: Truy xuất số liệu thống kê
Truy xuất số liệu thống kê về hạng mục rủi ro, chẳng hạn như kết thúc sớm, từ kết quả phân tích:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Bước 6: In số liệu thống kê
Lặp lại số liệu thống kê và in chi tiết:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //In các số liệu thống kê liên quan khác...
}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.Tasks cho .NET để thu thập số liệu thống kê về mục rủi ro từ các tệp MS Project. Bằng cách làm theo các bước này, bạn có thể phân tích dữ liệu dự án một cách hiệu quả và đánh giá các rủi ro tiềm ẩn, hỗ trợ đưa ra quyết định và quản lý dự án tốt hơn.

## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có thể xử lý các tệp MS Project lớn không?
Trả lời: Có, Aspose.Tasks có khả năng xử lý các tệp MS Project lớn một cách hiệu quả, mang lại hiệu suất và khả năng mở rộng đáng tin cậy.
### Câu hỏi: Aspose.Tasks có hỗ trợ các định dạng tệp dự án khác ngoài .mpp không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án khác nhau, bao gồm XML và MPT.
### Câu hỏi: Aspose.Tasks có phù hợp với các ứng dụng quản lý dự án cấp doanh nghiệp không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks được thiết kế để đáp ứng nhu cầu của các ứng dụng quản lý dự án cấp doanh nghiệp, cung cấp các tính năng mạnh mẽ và tài liệu phong phú.
### Câu hỏi: Tôi có thể tùy chỉnh cài đặt phân tích rủi ro trong Aspose.Tasks không?
Trả lời: Có, Aspose.Tasks mang đến sự linh hoạt trong việc định cấu hình cài đặt phân tích rủi ro để phù hợp với các yêu cầu và kịch bản dự án cụ thể của bạn.
### Câu hỏi: Người dùng Aspose.Tasks có được hỗ trợ kỹ thuật không?
 Trả lời: Có, người dùng Aspose.Tasks có thể truy cập hỗ trợ kỹ thuật thông qua Aspose[diễn đàn](https://forum.aspose.com/c/tasks/15), nơi họ có thể đặt câu hỏi, báo cáo vấn đề và tương tác với cộng đồng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
