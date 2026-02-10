---
date: 2026-02-10
description: Tìm hiểu cách lấy mã tiền tệ từ các tệp MS Project bằng Aspose.Tasks
  cho Java – cách nhanh chóng để có được mã tiền tệ mà các nhà phát triển Java cần.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách truy xuất tiền tệ từ MS Project bằng Aspose.Tasks
url: /vi/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lấy tiền tệ từ MS Project với Aspise.Tasks

## Introduction
Chào mừng! Trong hướng dẫn này, bạn sẽ khám phá **cách lấy tiền tệ** từ các mã tiền tệ trong tệp MS Project bằng cách sử dụng Aspose.Tasks Java API. Cho dù bạn đang tạo báo cáo tài chính đa tiền tệ, hợp nhất các dự án từ các khu vực khác nhau, hoặc chỉ cần các ký hiệu tiền tệ đúng cho quá trình xử lý tiếp theo, hướng dẫn này sẽ dẫn bạn qua từng bước — từ thiết lập môi trường đến việc trích xuất mã tiền tệ một cách lập trình. Khi hoàn thành, bạn sẽ tự tin đọc các tệp MS Project và sử dụng lệnh **get currency code java** để lấy định danh tiền tệ ISO.

## Quick Answers
- **API làm gì?** Nó đọc các tệp MS Project và cung cấp các thuộc tính như mã tiền tệ.  
- **Ngôn ngữ nào được sử dụng?** Java, thông qua thư viện Aspose.Tasks cho Java.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể lấy mã trong một dòng không?** Có — `prj.get(Prj.CURRENCY_CODE)` trả về chuỗi mã tiền tệ.  
- **Có tương thích với mọi phiên bản Project không?** Aspose.Tasks hỗ trợ cả định dạng cũ (MPP) và mới (XML, XER).

## What is **read ms project file**?
Đọc một tệp MS Project có nghĩa là mở một tài liệu dự án *.mpp* (hoặc các định dạng được hỗ trợ khác) một cách lập trình và truy cập vào các cấu trúc dữ liệu của nó — nhiệm vụ, nguồn lực, lịch, và các cài đặt tài chính — mà không cần tương tác thủ công với Microsoft Project.

## Why use Aspose.Tasks to **read msproject** files?
- **Hỗ trợ đầy đủ các định dạng** – hoạt động với các tệp từ Project 98 đến các phiên bản Office mới nhất.  
- **Không cần cài đặt COM hoặc Office** – thuần Java, lý tưởng cho tự động hoá phía máy chủ.  
- **API phong phú** – cung cấp truy cập trực tiếp tới các thuộc tính như `Prj.CURRENCY_CODE`, cho phép bạn **cách lấy tiền tệ** ngay lập tức.  
- **Hiệu năng** – phân tích nhẹ, lý tưởng cho xử lý hàng loạt nhiều dự án.

## Prerequisites
Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn có những thứ sau:

### Java Development Kit (JDK) Installed
Đảm bảo một JDK mới đã được cài đặt trên máy của bạn. Bạn có thể tải và cài đặt phiên bản JDK mới nhất từ [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java Library
Tải và thiết lập thư viện Aspose.Tasks cho Java. Tài liệu chi tiết và các binary mới nhất có sẵn [here](https://reference.aspose.com/tasks/java/).

## Import Packages
Để bắt đầu, hãy nhập các gói cần thiết vào dự án Java của bạn:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step‑by‑step guide

### Step 1: Set Up Data Directory
Xác định thư mục chứa tệp *.mpp* của bạn. Điều chỉnh đường dẫn cho phù hợp với môi trường của bạn.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
Tạo một thể hiện `Project` bằng cách tải tệp MS Project. Đây là thời điểm bạn **đọc msproject** dữ liệu vào bộ nhớ.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Currency Code
Bây giờ dự án đã được tải, bạn có thể **cách lấy tiền tệ** thông tin bằng một lệnh duy nhất. Điều này minh họa cách sử dụng **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Kết quả sẽ là mã tiền tệ ISO ba chữ (ví dụ, `USD`, `EUR`, `GBP`) mà dự án được cấu hình sử dụng.

### Step 4: How to Retrieve Currency Code in Java (Additional Context)
Nếu bạn cần lưu giá trị để sử dụng sau, chỉ cần gán nó vào một biến:

*No extra code block is required* – just keep the string returned by `prj.get(Prj.CURRENCY_CODE)` and pass it to any financial service, reporting engine, or UI component.

### Step 5: (Optional) Use the Currency Code
Bạn có thể muốn áp dụng mã đã lấy ở nơi khác — chẳng hạn định dạng giá trị chi phí trong báo cáo tùy chỉnh hoặc truyền nó tới một API tài chính. Các kịch bản điển hình bao gồm:

- **Tạo báo cáo** – đặt mã trước các cột chi phí (`USD 1,200`).  
- **Tích hợp API** – gửi mã ISO tới các cổng thanh toán yêu cầu định danh tiền tệ.  
- **Hợp nhất dữ liệu** – nhóm nhiều dự án theo tiền tệ để phân tích danh mục.

## Common Issues and Solutions
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| **Kết quả null** | Tệp dự án không xác định tiền tệ (mặc định là trống). | Đặt tiền tệ trong Microsoft Project hoặc gán nó bằng `prj.set(Prj.CURRENCY_CODE, "USD");` trước khi đọc. |
| **Không tìm thấy tệp** | Đường dẫn `dataDir` không đúng. | Kiểm tra lại đường dẫn và đảm bảo tên tệp khớp chính xác, bao gồm phân biệt chữ hoa/thường. |
| **Phiên bản tệp không được hỗ trợ** | Tệp *.mpp* quá cũ hoặc bị hỏng. | Sử dụng phiên bản Aspose.Tasks mới nhất hoặc chuyển đổi tệp sang định dạng mới hơn trong Microsoft Project trước. |

## Frequently Asked Questions

**Hỏi: Aspose.Tasks có thể xử lý cấu trúc dự án phức tạp không?**  
**Đáp:** Có, API có thể đọc và thao tác các cây nhiệm vụ đa cấp, pool nguồn lực và các trường tùy chỉnh mà không gặp vấn đề.

**Hỏi: Aspose.Tasks có tương thích với các phiên bản tệp MS Project khác nhau không?**  
**Đáp:** Hoàn toàn. Nó hỗ trợ MPP, XML, XER và các định dạng khác trên nhiều phiên bản Microsoft Project.

**Hỏi: Aspose.Tasks có cung cấp tài liệu và hỗ trợ không?**  
**Đáp:** Tài liệu đầy đủ, ví dụ mã và hỗ trợ chuyên dụng có sẵn trên trang web Aspose.

**Hỏi: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?**  
**Đáp:** Một bản dùng thử miễn phí được cung cấp để bạn đánh giá tất cả các tính năng, bao gồm đọc mã tiền tệ.

**Hỏi: Tôi có thể lấy giấy phép tạm thời cho Aspose.Tasks ở đâu?**  
**Đáp:** Giấy phép tạm thời có thể được lấy từ [website](https://purchase.aspose.com/temporary-license/) để đánh giá ngắn hạn.

---

**Cập nhật lần cuối:** 2026-02-10  
**Đã kiểm tra với:** Aspose.Tasks for Java (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}