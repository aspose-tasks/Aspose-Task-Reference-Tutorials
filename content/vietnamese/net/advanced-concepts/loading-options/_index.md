---
title: Tùy chọn tải trong Aspose.Tasks
linktitle: Tùy chọn tải trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách khai thác sức mạnh của Aspose.Tasks dành cho .NET để quản lý hiệu quả các tài liệu Microsoft Project với hướng dẫn từng bước.
type: docs
weight: 16
url: /vi/net/advanced-concepts/loading-options/
---
## Giới thiệu

Aspose.Tasks for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác với các tài liệu Microsoft Project theo chương trình. Cho dù bạn cần tạo, đọc, ghi hay chuyển đổi tệp Dự án, Aspose.Tasks đều cung cấp nhiều chức năng để hợp lý hóa các nhiệm vụ của bạn. Trong hướng dẫn này, chúng ta sẽ đi sâu vào các yếu tố cần thiết của việc sử dụng Aspose.Tasks cho .NET, chia nhỏ các quy trình chính thành các bước đơn giản, có thể thực hiện được.

## Điều kiện tiên quyết

Trước khi đi sâu vào Aspose.Tasks cho .NET, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:

1. Visual Studio: Cài đặt Visual Studio hoặc bất kỳ IDE nào khác mà bạn chọn.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[trang mạng](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản về C#: Làm quen với các nguyên tắc cơ bản của ngôn ngữ lập trình C#.

Bây giờ chúng ta đã nắm được các điều kiện tiên quyết, hãy cùng khám phá các không gian tên thiết yếu và đi sâu vào hướng dẫn từng bước.

## Nhập không gian tên

Trong dự án C# của bạn, hãy nhập các vùng tên cần thiết để truy cập các chức năng của Aspose.Tasks:

1. Aspose.Tasks: Không gian tên này cung cấp các lớp và giao diện cốt lõi để làm việc với các tài liệu Project.

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

Bây giờ, hãy chia nhỏ các nhiệm vụ khác nhau thành các hướng dẫn từng bước.

## Bước 1: Tải dự án được bảo vệ bằng mật khẩu

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Khởi tạo FileStream để tải file dự án
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Tạo phiên bản LoadOptions
        var options = new LoadOptions
        {
            Password = "password" // Đặt mật khẩu
        };

        // Tải dự án với các tùy chọn được chỉ định
        var project = new Project(stream, options);

        // Hiển thị tên dự án
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## Bước 2: Tải dự án Primavera với các tùy chọn tùy chỉnh

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Tạo phiên bản LoadOptions
    var loadOptions = new LoadOptions();

    // Định cấu hình tùy chọn đọc Primavera
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Đặt UID dự án
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Đặt tùy chọn đọc Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Tải dự án Primavera với các tùy chọn được chỉ định
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Hiển thị tên dự án
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Thực hiện các hoạt động tiếp theo với dự án đã tải
}
```

## Bước 3: Chỉ định mã hóa tệp

```csharp
public void SpecifyFileEncoding()
{
    // Tạo phiên bản LoadOptions
    LoadOptions lo = new LoadOptions();

    // Chỉ định mã hóa khi mở dự án từ tệp Primavera XER
    lo.Encoding = Encoding.GetEncoding(1251);

    // Tải dự án với mã hóa được chỉ định
    var project = new Project("encoding1251.xer", lo);

    // Thực hiện các hoạt động tiếp theo với dự án đã tải
}
```

## Bước 4: Tải các dự án Primavera có xử lý lỗi

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Tạo phiên bản LoadOptions
    var loadOptions = new LoadOptions();

    // Định cấu hình tùy chọn đọc Primavera
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Đặt UID dự án
    };

    // Đặt tùy chọn đọc Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //Đặt xử lý lỗi tùy chỉnh
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Tải dự án Primavera với các tùy chọn được chỉ định và xử lý lỗi
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Thực hiện các hoạt động tiếp theo với dự án đã tải
}

// Phương pháp xử lý lỗi tùy chỉnh
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Triển khai logic xử lý lỗi tùy chỉnh
}
```

Bằng cách làm theo các bước này, bạn có thể sử dụng hiệu quả các tùy chọn tải trong Aspose.Tasks dành cho .NET để thao tác các tài liệu Dự án theo yêu cầu của bạn.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá các nguyên tắc cơ bản khi làm việc với các tùy chọn tải trong Aspose.Tasks dành cho .NET. Từ việc tải các dự án được bảo vệ bằng mật khẩu đến chỉ định xử lý lỗi tùy chỉnh, việc nắm vững các kỹ thuật này sẽ giúp bạn quản lý hiệu quả các tệp Dự án trong ứng dụng .NET của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks dành cho .NET có tương thích với tất cả các phiên bản Microsoft Project không?

Trả lời 1: Có, Aspose.Tasks for .NET hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.

### Câu hỏi 2: Tôi có thể tích hợp Aspose.Tasks cho .NET với các thư viện bên thứ ba khác không?

Câu trả lời 2: Hoàn toàn có thể, Aspose.Tasks dành cho .NET tích hợp liền mạch với các thư viện .NET khác, cung cấp chức năng nâng cao và tính linh hoạt.

### Câu hỏi 3: Aspose.Tasks cho .NET có cung cấp tài liệu và tài nguyên hỗ trợ không?

 A3: Có, bạn có thể tham khảo toàn diện[tài liệu](https://reference.aspose.com/tasks/net/) và truy cập hỗ trợ thông qua[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Câu hỏi 4: Có bất kỳ tùy chọn cấp phép nào dành cho Aspose.Tasks dành cho .NET không?

 Câu trả lời 4: Có, bạn có thể khám phá các tùy chọn cấp phép khác nhau, bao gồm cả bản dùng thử miễn phí và giấy phép tạm thời, trên[Trang web Aspose.Tasks](https://purchase.aspose.com/buy).

### Câu hỏi 5: Tần suất phát hành các bản cập nhật và tính năng mới cho Aspose.Tasks cho .NET là bao nhiêu?

Câu trả lời 5: Aspose.Tasks dành cho .NET nhận được các bản cập nhật thường xuyên và cải tiến tính năng để đảm bảo hiệu suất và khả năng tương thích tối ưu với các công nghệ đang phát triển.