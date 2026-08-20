---
date: 2026-03-08
description: Tìm hiểu cách nhập tệp dự án bằng Aspose.Tasks cho .NET, bao gồm cách
  chỉ định mã hóa tệp và tải tệp Microsoft Project một cách hiệu quả.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Nhập tệp dự án – Các tùy chọn tải trong Aspose.Tasks
url: /vi/net/advanced-concepts/loading-options/
weight: 16
---

Make sure to keep markdown formatting.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nhập Tệp Dự Án – Các Tùy Chọn Tải Trong Aspose.Tasks

## Introduction

Aspose.Tasks for .NET giúp bạn dễ dàng **import project file** dữ liệu từ Microsoft Project, Primavera và các định dạng khác. Cho dù bạn cần đọc một tệp được bảo vệ bằng mật khẩu, thiết lập mã hoá tùy chỉnh, hoặc xử lý lỗi phân tích, thư viện cung cấp cho bạn kiểm soát chi tiết thông qua các tùy chọn tải. Trong hướng dẫn này, chúng tôi sẽ đi qua các kịch bản phổ biến nhất để bạn có thể tự tin **load Microsoft Project file** các đối tượng trong ứng dụng .NET của mình.

## Quick Answers
- **Cách chính để nhập một tệp dự án là gì?** Sử dụng hàm khởi tạo `Project` với một thể hiện `LoadOptions`.  
- **Tôi có thể mở các tệp được bảo vệ bằng mật khẩu không?** Có — đặt thuộc tính `Password` trên `LoadOptions`.  
- **Làm thế nào để chỉ định mã hoá tệp?** Gán một đối tượng `Encoding` cho `LoadOptions.Encoding`.  
- **Xử lý lỗi có thể tùy chỉnh không?** Hoàn toàn có thể — cung cấp một delegate cho `LoadOptions.ErrorHandler`.  
- **Các tùy chọn này có hoạt động với tệp Primavera không?** Có, thông qua `PrimaveraReadOptions` bên trong `LoadOptions`.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Visual Studio** (hoặc bất kỳ IDE .NET nào bạn ưa thích).  
2. **Aspose.Tasks for .NET** – tải xuống từ [trang web](https://releases.aspose.com/tasks/net/).  
3. Kiến thức cơ bản về cú pháp **C#** và cấu trúc dự án.

Bây giờ chúng ta đã sẵn sàng, hãy nhập các namespace cần thiết.

## Importing Namespaces

Trong dự án C# của bạn, thêm các câu lệnh `using` sau để các lớp API có sẵn:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## How to Import Project File with Loading Options

Dưới đây là bốn ví dụ thực tế bao phủ các kịch bản tải thường gặp nhất.

### Step 1: Load a Password‑Protected Project

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Step 2: Load a Primavera Project with Custom Options

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Step 3: **Specify File Encoding** When Importing an XER File

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Step 4: Load a Primavera Project with Custom Error Handling

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Bằng cách làm theo các bước này, bạn có thể chính xác **import project file** dữ liệu, tùy chỉnh quá trình tải theo nhu cầu và giữ cho ứng dụng của mình ổn định.

## Common Issues & Tips

- **Mật khẩu không đúng** – thuộc tính `Password` sẽ ném ra ngoại lệ; hãy xác minh thông tin đăng nhập trước khi tải.  
- **Mã hoá không được hỗ trợ** – đảm bảo trang mã bạn chỉ định tồn tại trên máy mục tiêu (`Encoding.GetEncoding(1251)` hoạt động cho Cyrillic).  
- **Thiếu tùy chọn Primavera** – nếu bạn cần giữ lại UID của nhiệm vụ, đặt `PreserveUids = true`; nếu không, các ID trùng lặp có thể xuất hiện.  
- **Trình xử lý lỗi trả về null** – trả về `null` sẽ báo cho bộ phân tích bỏ qua phần tử gây lỗi; tùy chỉnh theo yêu cầu.

## Frequently Asked Questions

**Q: Aspose.Tasks for .NET có tương thích với tất cả các phiên bản của Microsoft Project không?**  
A: Có, nó hỗ trợ một loạt các phiên bản Microsoft Project, vì vậy bạn có thể **load Microsoft Project file** các định dạng từ các tệp MPP cũ đến các định dạng mới nhất.

**Q: Tôi có thể tích hợp Aspose.Tasks for .NET với các thư viện của bên thứ ba khác không?**  
A: Chắc chắn. Thư viện hoạt động liền mạch với các gói .NET khác, cho phép bạn kết hợp nó với các framework báo cáo, giao diện người dùng hoặc truy cập dữ liệu.

**Q: Có, bạn có thể tham khảo tài liệu toàn diện [documentation](https://reference.aspose.com/tasks/net/) và truy cập hỗ trợ qua [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).**  

**Q: Có, bạn có thể khám phá các tùy chọn cấp phép khác nhau, bao gồm dùng thử miễn phí và giấy phép tạm thời, trên [Aspose.Tasks website](https://purchase.aspose.com/buy).**  

**Q: Aspose.Tasks nhận các bản cập nhật thường xuyên, bổ sung tính năng, cải thiện hiệu suất và duy trì tính tương thích với các phiên bản Microsoft Project mới nhất.**  

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}