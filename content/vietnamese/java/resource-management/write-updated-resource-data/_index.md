---
title: Viết dữ liệu tài nguyên được cập nhật trong Aspose.Tasks
linktitle: Viết dữ liệu tài nguyên được cập nhật trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách cập nhật dễ dàng dữ liệu tài nguyên trong tệp MS Project bằng Aspose.Tasks cho Java.
type: docs
weight: 21
url: /vi/java/resource-management/write-updated-resource-data/
---
## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cập nhật dữ liệu tài nguyên Microsoft Project bằng Aspose.Tasks cho Java. Aspose.Tasks là một API Java mạnh mẽ cho phép bạn thao tác với các tệp Microsoft Project mà không yêu cầu cài đặt Microsoft Project trên hệ thống của bạn.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
2.  Aspose.Tasks cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).
3. Kiến thức cơ bản về lập trình Java.

## Gói nhập khẩu

Trước tiên, bạn cần nhập các gói cần thiết để làm việc với Aspose.Tasks trong mã Java của mình. Thêm các câu lệnh nhập sau vào tệp Java của bạn:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Bước 1: Thiết lập thư mục dữ liệu của bạn

Xác định thư mục chứa tệp dữ liệu của bạn:

```java
String dataDir = "Your Data Directory";
```

## Bước 2: Chỉ định tệp đầu vào và đầu ra

Xác định đường dẫn cho tệp MS Project đầu vào và tệp cập nhật kết quả:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Kiểm tra tệp với một rsc để cập nhật
String resultFile = dataDir + "OutputMPP.mpp"; // File viết dự án thử nghiệm
```

## Bước 3: Tải dự án

 Tải tệp MS Project vào một`Project` sự vật:

```java
Project project = new Project(file);
```

## Bước 4: Thêm tài nguyên và đặt thuộc tính

Thêm tài nguyên mới vào dự án và đặt các thuộc tính của nó như tỷ lệ tiêu chuẩn, tỷ lệ làm thêm giờ và nhóm:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Bước 5: Lưu dự án

Lưu dự án đã cập nhật với dữ liệu tài nguyên đã sửa đổi:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách cập nhật dữ liệu tài nguyên MS Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn có thể thao tác hiệu quả thông tin tài nguyên trong tệp MS Project của mình theo chương trình.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể cập nhật nhiều tài nguyên trong cùng một dự án bằng Aspose.Tasks cho Java không?

Câu trả lời 1: Có, bạn có thể cập nhật nhiều tài nguyên bằng cách duyệt qua chúng và đặt thuộc tính cho phù hợp.

### Câu hỏi 2: Aspose.Tasks có hỗ trợ các định dạng tệp khác ngoài MS Project không?

Câu trả lời 2: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp khác nhau bao gồm XML, MPP, v.v.

### Câu hỏi 3: Aspose.Tasks có tương thích với các phiên bản Java khác nhau không?

Câu trả lời 3: Aspose.Tasks tương thích với Java phiên bản 6 trở lên.

### Câu hỏi 4: Tôi có thể thực hiện các thao tác khác trên tệp MS Project bằng Aspose.Tasks không?

Câu trả lời 4: Có, bạn có thể thực hiện nhiều thao tác như đọc, viết và thao tác các tác vụ, tài nguyên và lịch.

### Câu hỏi 5: Tôi có thể tìm thêm trợ giúp hoặc hỗ trợ cho Aspose.Tasks ở đâu?

 A5: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) cho bất kỳ sự trợ giúp hoặc thắc mắc.
