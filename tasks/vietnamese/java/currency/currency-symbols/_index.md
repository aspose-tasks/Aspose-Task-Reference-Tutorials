---
date: 2026-02-10
description: Học cách trích xuất và cập nhật các thuộc tính dự án Java như ký hiệu
  tiền tệ bằng Aspose.Tasks for Java. Thay đổi tiền tệ của dự án và dễ dàng lấy ký
  hiệu tiền tệ.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: thuộc tính dự án java – Trích xuất ký hiệu tiền tệ từ MPP bằng Aspose.Tasks
  cho Java
url: /vi/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trích xuất ký hiệu tiền tệ mpp bằng Aspose.Tasks cho Java

## Introduction
Trong tutorial này bạn sẽ học cách làm việc với **java project properties**—cụ thể là cách trích xuất ký hiệu tiền tệ từ một tệp Microsoft Project (MPP) và cách **change currency symbol java** hoặc **retrieve currency symbol java** bằng thư viện Aspose.Tasks. Cho dù bạn đang xây dựng công cụ báo cáo, tích hợp dữ liệu Project vào hệ thống tài chính, hay chỉ cần hiển thị ký hiệu tiền tệ đúng trong UI, việc nắm vững nhiệm vụ nhỏ nhưng quan trọng này sẽ làm cho các ứng dụng Java của bạn mạnh mẽ hơn và thân thiện với người dùng.

## Quick Answers
- **What does “extract currency symbol mpp” mean?** Nó có nghĩa là đọc ký hiệu tiền tệ được lưu trong tệp MPP (Microsoft Project).  
- **Which library handles this?** Aspose.Tasks for Java cung cấp một API đơn giản cho công việc này.  
- **Do I need a license?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **How long does it take?** Với đoạn mã dưới đây, bạn có thể lấy ký hiệu trong chưa đầy một phút.  
- **Can I also change the symbol?** Có – bạn có thể đặt giá trị mới bằng cách sử dụng cùng thuộc tính `Prj.CURRENCY_SYMBOL`.

## What is “extract currency symbol mpp”?
Microsoft Project lưu ký hiệu tiền tệ (ví dụ: $, €, £) trong phần đầu của tệp dự án. Thao tác **extract currency symbol mpp** đọc giá trị đó để bạn có thể hiển thị hoặc thao tác nó một cách lập trình.

## Why update currency symbol in java project properties?
Các dự án thường trải rộng nhiều khu vực. Khả năng **change project currency** hoặc **update currency symbol** tại thời gian chạy cho phép bạn điều chỉnh báo cáo, hoá đơn hoặc bảng điều khiển cho thị trường địa phương mà không cần tạo lại toàn bộ tệp dự án. Sự linh hoạt này là một phần cốt lõi của việc quản lý java project properties một cách hiệu quả.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Java Development Kit (JDK)** – phiên bản 8 trở lên.  
2. **Aspose.Tasks for Java** – tải JAR mới nhất từ [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. Một tệp **project.mpp** hợp lệ được đặt trong thư mục bạn có thể tham chiếu từ mã của mình.

## Import Packages
Đầu tiên, nhập các lớp chúng ta sẽ cần để làm việc với các tệp Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step 1: Define the Data Directory
Cho ứng dụng biết vị trí tệp *.mpp* của bạn.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Sử dụng `System.getProperty("user.dir")` để xây dựng đường dẫn tuyệt đối hoạt động trên bất kỳ máy nào.

## Step 2: Load the MS Project File
Tạo một đối tượng `Project` đại diện cho tệp MPP trong bộ nhớ.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Step 3: Retrieve (and optionally change) the Currency Symbol
Bây giờ chúng ta **retrieve currency symbol java** bằng cách đọc thuộc tính `Prj.CURRENCY_SYMBOL`. Bạn cũng có thể **change currency symbol java** (hoặc **change project currency**) bằng cách gán một chuỗi mới cho cùng thuộc tính đó.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Lệnh `System.out.println` sẽ in ký hiệu (ví dụ: `$`) ra console, xác nhận việc trích xuất đã thành công.

## Common Issues & How to Fix Them
| Triệu chứng | Nguyên nhân có thể | Giải pháp |
|------------|--------------------|-----------|
| `NullPointerException` on `project.get(...)` | Đường dẫn tệp sai hoặc không tìm thấy tệp | Xác minh `dataDir` và tên tệp; sử dụng `new File(dataDir).exists()` để gỡ lỗi |
| Ký hiệu không mong muốn (ví dụ: `?`) | Dự án được tạo với locale không chuẩn | Đảm bảo tệp MPP nguồn thực sự định nghĩa ký hiệu tiền tệ; bạn có thể đặt một ký hiệu bằng cách lập trình như đã minh họa ở trên |
| Lỗi giấy phép | Sử dụng bản dùng thử mà không có tệp giấy phép hợp lệ | Tải giấy phép của bạn bằng `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` trước khi tạo đối tượng `Project` |

## Frequently Asked Questions

**Q: Tôi có thể thao tác các thuộc tính dự án khác ngoài ký hiệu tiền tệ bằng Aspose.Tasks không?**  
A: Có, Aspose.Tasks cho phép bạn chỉnh sửa nhiệm vụ, nguồn lực, phân công, lịch, và nhiều thuộc tính dự án khác.

**Q: Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp MS Project không?**  
A: Chắc chắn. Nó hỗ trợ các định dạng MPP, MPT và XML từ Project 98 đến các phiên bản mới nhất.

**Q: Aspose.Tasks có cung cấp tài liệu và hỗ trợ cho nhà phát triển không?**  
A: Tài liệu API đầy đủ, các ví dụ mã, và diễn đàn hỗ trợ riêng có sẵn trên trang web Aspose.Tasks.

**Q: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?**  
A: Có – bản dùng thử đầy đủ chức năng có thể tải xuống từ [Aspose website](https://purchase.aspose.com/buy).

**Q: Làm thế nào tôi có thể nhận giấy phép tạm thời cho Aspose.Tasks?**  
A: Giấy phép tạm thời được cung cấp trên [trang giấy phép tạm thời của Aspose](https://purchase.aspose.com/temporary-license/) để đánh giá.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}