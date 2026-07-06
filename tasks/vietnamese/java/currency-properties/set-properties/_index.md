---
date: 2026-02-07
description: Tìm hiểu cách đặt mã tiền tệ java trong các dự án Aspose.Tasks, thay
  đổi ký hiệu tiền tệ và áp dụng định dạng tiền tệ tùy chỉnh cho các tệp Microsoft
  Project.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Mã tiền tệ Java – Cách thiết lập trong các dự án Aspose.Tasks
url: /vi/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Mã Tiền Tệ trong Aspose.Tasks – Hướng Dẫn Java

## Introduction
Trong hướng dẫn này, bạn sẽ học **cách đặt mã tiền tệ java** cho tệp Microsoft Project bằng API Aspose.Tasks cho Java. Cho dù bạn cần *thay đổi tiền tệ* cho các nhóm quốc tế, điều chỉnh *ký hiệu tiền tệ*, hoặc áp dụng **định dạng tiền tệ tùy chỉnh**, các bước dưới đây sẽ hướng dẫn bạn qua quá trình với giải thích rõ ràng và mã sẵn sàng chạy.

## Quick Answers
- **Thư viện nào được yêu cầu?** Aspose.Tasks for Java.  
- **Tôi có thể thay đổi ký hiệu tiền tệ không?** Có – sử dụng `CurrencySymbolPositionType` và `Prj.CURRENCY_SYMBOL`.  
- **Các định dạng tệp nào được hỗ trợ?** XML, MPP và nhiều định dạng khác qua `SaveFileFormat`.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; cần giấy phép cho môi trường sản xuất.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 5‑10 phút cho cấu hình cơ bản.

## How to Set Currency Code Java in Aspose.Tasks
Tiền tệ của một Project xác định cách hiển thị các giá trị chi phí — mã (ví dụ, `AUD`), số chữ số thập phân, ký hiệu (`$`), và vị trí của ký hiệu. Việc thiết lập các thuộc tính này đảm bảo mọi trường liên quan đến chi phí (giá trị tài nguyên, ngân sách công việc, v.v.) phản ánh định dạng tiền tệ chính xác cho người dùng của bạn.

## Why Use Aspose.Tasks to Change Currency?
- **Không cần cài đặt Microsoft Project** – thao tác với các tệp trên bất kỳ máy chủ nào.  
- **Bao phủ đầy đủ API** – tất cả các trường liên quan đến tiền tệ được cung cấp qua các hằng số `Prj`.  
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS với bất kỳ IDE nào hỗ trợ Java.  
- **Hiệu suất cao** – xử lý các tệp dự án lớn nhanh chóng và đáng tin cậy.  
- **Hỗ trợ định dạng tiền tệ tùy chỉnh** – bạn có thể định nghĩa ký hiệu, chữ số thập phân và vị trí để phù hợp với tiêu chuẩn khu vực.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Bộ công cụ phát triển Java (JDK)** – phiên bản 8 trở lên.  
2. **Aspose.Tasks cho Java** – tải JAR mới nhất từ [trang tải xuống Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Một IDE** – Eclipse, IntelliJ IDEA, hoặc bất kỳ trình soạn thảo nào bạn thích.  
4. **Thư mục có quyền ghi** – nơi tệp dự án được tạo sẽ được lưu.

## Import Packages
First, import the classes that provide access to project properties and file handling.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
Specify the folder that contains your source files and where the output will be written.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
Instantiate a fresh `Project` object. This object represents an in‑memory Microsoft Project file.

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
Here’s where we **how to set currency** details such as code, digits, symbol, and symbol position.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Mẹo chuyên nghiệp:** Nếu bạn cần **thay đổi tiền tệ dự án** cho một tệp hiện có, chỉ cần tải nó bằng `new Project("file.mpp")` trước khi áp dụng các cài đặt trên.

### Step 4: Save the Updated Project
Write the project back to disk in the desired format. In this example we use the XML format, but you can also choose `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
Print a friendly message so you know the operation completed without errors.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` không phải là đường dẫn hợp lệ hoặc thiếu quyền ghi. | Đảm bảo thư mục tồn tại và quá trình Java của bạn có quyền ghi. |
| **Ký hiệu tiền tệ không hiển thị** | Vị trí ký hiệu được đặt không đúng cho địa phương của bạn. | Sử dụng `CurrencySymbolPositionType.Before` nếu ký hiệu nên đứng trước số tiền. |
| **Tệp dự án không mở được trong MS Project** | Lưu ở định dạng cũ với các cài đặt không tương thích. | Lưu bằng `SaveFileFormat.MPP` để tương thích đầy đủ với các phiên bản MS Project mới nhất. |

## Frequently Asked Questions

**Hỏi: Tôi có thể đặt nhiều tiền tệ trong một dự án duy nhất bằng Aspose.Tasks không?**  
**Đáp:** Có, Aspose.Tasks cho phép bạn quản lý nhiều tiền tệ trong một tệp dự án bằng cách thiết lập các thuộc tính tiền tệ cho từng tài nguyên hoặc từng công việc.

**Hỏi: Aspose.Tasks có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
**Đáp:** Hoàn toàn. Thư viện hỗ trợ các tệp MPP từ Project 2000 đến các phiên bản mới nhất, cũng như XML và các định dạng khác.

**Hỏi: Aspose.Tasks có hỗ trợ định dạng tiền tệ tùy chỉnh không?**  
**Đáp:** Có, bạn có thể định nghĩa ký hiệu, chữ số thập phân và vị trí tùy chỉnh để đáp ứng bất kỳ yêu cầu khu vực nào.

**Hỏi: Tôi có thể tích hợp Aspose.Tasks với các thư viện hoặc framework Java khác không?**  
**Đáp:** Chắc chắn. API thuần Java, vì vậy nó hoạt động liền mạch với Spring, Hibernate, Maven, Gradle và các hệ sinh thái khác.

**Hỏi: Tôi có thể tìm hỗ trợ hoặc trợ giúp bổ sung cho Aspose.Tasks ở đâu?**  
**Đáp:** Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận trợ giúp cộng đồng, hoặc tham khảo tài liệu chính thức để có các tham chiếu API chi tiết.

## Conclusion
Bạn hiện đã biết **cách đặt mã tiền tệ java**, cách **thay đổi giá trị tiền tệ**, và cách **thay đổi ký hiệu tiền tệ** bằng Aspose.Tasks cho Java. Những khả năng này cho phép bạn tùy chỉnh dữ liệu chi phí cho các đội ngũ toàn cầu, tạo báo cáo theo địa phương, và giữ cho các tệp dự án của bạn nhất quán trên các biên giới.

---

**Cập nhật lần cuối:** 2026-02-07  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}