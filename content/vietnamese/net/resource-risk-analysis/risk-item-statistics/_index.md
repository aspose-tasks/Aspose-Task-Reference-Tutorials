---
title: Thống kê các mục rủi ro trong Aspose.Tasks
linktitle: Thống kê các mục rủi ro trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khai phá sức mạnh của phân tích rủi ro trong tệp MS Project bằng Aspose.Tasks for .NET. Thu thập thông tin chi tiết, giảm thiểu sự không chắc chắn và thúc đẩy thành công của dự án một cách dễ dàng.
type: docs
weight: 21
url: /vi/net/resource-risk-analysis/risk-item-statistics/
---
## Giới thiệu
Bạn đang tìm cách nâng cao năng lực quản lý dự án của mình bằng Aspose.Tasks cho .NET? Đi sâu vào lĩnh vực phân tích rủi ro với hướng dẫn từng bước của chúng tôi về cách thu thập số liệu thống kê về các mục rủi ro trong tệp MS Project. Bằng cách tận dụng các khả năng mạnh mẽ của Aspose.Tasks, bạn có thể có được những hiểu biết sâu sắc vô giá về những điều không chắc chắn của dự án và đưa ra quyết định sáng suốt để giảm thiểu rủi ro một cách hiệu quả.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu cuộc hành trình này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện từ[Aspose.Tasks cho tài liệu .NET](https://reference.aspose.com/tasks/net/). Thư viện này trang bị cho bạn các công cụ mạnh mẽ để thao tác các tệp MS Project theo chương trình.
2. Môi trường phát triển .NET: Thiết lập môi trường phát triển .NET của bạn, bao gồm Visual Studio hoặc bất kỳ IDE nào khác mà bạn chọn, để tạo điều kiện tích hợp liền mạch Aspose.Tasks vào các dự án của bạn.

## Nhập không gian tên
Kết hợp các không gian tên cần thiết vào dự án của bạn để khai thác các chức năng của Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Bước 1: Xác định thư mục dữ liệu
```csharp
String DataDir = "Your Document Directory";
```
 Đảm bảo thay thế`"Your Document Directory"` với đường dẫn đến thư mục tài liệu nơi chứa các tệp MS Project của bạn.
## Bước 2: Định cấu hình cài đặt phân tích rủi ro
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Điều chỉnh`IterationsCount`tham số dựa trên yêu cầu dự án của bạn để kiểm soát độ chính xác của phân tích rủi ro.
## Bước 3: Tải tệp dự án MS
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Tải tệp MS Project mong muốn vào`project` đối tượng để phân tích sâu hơn.
## Bước 4: Xác định nhiệm vụ và khởi tạo mô hình rủi ro
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Chỉ định nhiệm vụ phân tích rủi ro và định cấu hình mô hình rủi ro với các tham số thích hợp như loại phân phối, khoảng thời gian lạc quan và bi quan cũng như mức độ tin cậy.
## Bước 5: Phân tích rủi ro dự án
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Bắt đầu quá trình phân tích rủi ro bằng cách sử dụng các cài đặt và dữ liệu dự án đã xác định.
## Bước 6: Truy xuất và hiển thị số liệu thống kê
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Truy xuất và hiển thị các số liệu thống kê khác nhau liên quan đến các mục rủi ro trong tệp MS Project, bao gồm giá trị mong đợi, độ lệch chuẩn, phần trăm, giá trị tối thiểu và tối đa.

## Phần kết luận
Tóm lại, việc nắm vững phân tích rủi ro trong các tệp MS Project bằng Aspose.Tasks cho .NET sẽ mở ra nhiều khả năng cho người quản lý dự án và các bên liên quan. Bằng cách làm theo hướng dẫn toàn diện của chúng tôi, bạn có thể tự tin vượt qua những điều không chắc chắn, đảm bảo kết quả dự án thành công.
## Câu hỏi thường gặp
### Tôi có thể tích hợp Aspose.Tasks với các thư viện .NET khác để có chức năng mở rộng không?
Tuyệt đối! Aspose.Tasks tích hợp liền mạch với nhiều thư viện .NET khác nhau, cho phép bạn khuếch đại khả năng của nó theo yêu cầu dự án của bạn.
### Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?
 Có, bạn có thể khám phá các tính năng của Aspose.Tasks bằng cách truy cập[dùng thử miễn phí](https://releases.aspose.com/) có sẵn trên trang web của chúng tôi.
### Tần suất phát hành các bản cập nhật và cải tiến cho Aspose.Tasks như thế nào?
Chúng tôi cố gắng liên tục cải tiến Aspose.Tasks bằng cách phát hành các bản cập nhật và cải tiến định kỳ, đảm bảo rằng bạn luôn có quyền truy cập vào các tính năng và tối ưu hóa mới nhất.
### Tôi có thể nhận được hỗ trợ kỹ thuật cho Aspose.Tasks không?
Chắc chắn! Nhóm hỗ trợ tận tâm của chúng tôi luôn sẵn sàng trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để hỗ trợ bạn với bất kỳ thắc mắc hoặc thách thức nào bạn có thể gặp phải trong quá trình triển khai.
### Bạn có cung cấp giấy phép tạm thời cho các dự án ngắn hạn không?
 Có, nếu bạn yêu cầu Aspose.Tasks cho một dự án ngắn hạn, bạn có thể tận dụng dịch vụ tiện lợi của chúng tôi[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) tùy chọn để đáp ứng nhu cầu cấp phép của bạn mà không cần bất kỳ cam kết dài hạn nào.