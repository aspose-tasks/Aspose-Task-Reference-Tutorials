---
date: 2025-12-25
description: Khám phá hướng dẫn Aspose Tasks Java này để tìm hiểu cách xác định phiên
  bản dự án của các tệp MS Project. Hướng dẫn từng bước kèm ví dụ mã.
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Hướng dẫn Aspose Tasks Java: Xác định phiên bản MS Project'
url: /vi/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hướng Dẫn Aspose Tasks Java: Xác Định Phiên Bản MS Project

## Introduction
Trong **aspose tasks java tutorial** này, bạn sẽ khám phá cách tìm phiên bản của tệp Microsoft Project một cách lập trình bằng thư viện Aspose.Tasks cho Java. Biết được phiên bản tệp giúp bạn xử lý các vấn đề tương thích, thực thi các chính sách nâng cấp, hoặc chỉ đơn giản là ghi lại phiên bản Project đã tạo tệp. Chúng tôi sẽ hướng dẫn từng bước—từ việc thiết lập môi trường đến việc in ra phiên bản và ngày lưu lần cuối—để bạn có thể tích hợp kiểm tra này vào bất kỳ ứng dụng Java nào một cách tự tin.

## Quick Answers
- **What does this tutorial cover?** Nội dung của hướng dẫn này là gì?  
  Xác định phiên bản tệp MS Project bằng Aspose.Tasks cho Java.  
- **Do I need Microsoft Project installed?** Có cần cài đặt Microsoft Project không?  
  Không, Aspose.Tasks hoạt động độc lập.  
- **Which file formats are supported?** Các định dạng tệp nào được hỗ trợ?  
  Các tệp Project dựa trên XML (MPP, XML, v.v.).  
- **How long does the implementation take?** Thời gian thực hiện khoảng bao lâu?  
  Khoảng 5‑10 phút cho một kiểm tra cơ bản.  
- **Is a license required?** Có cần giấy phép không?  
  Bản dùng thử miễn phí đủ cho việc đánh giá; cần giấy phép cho môi trường sản xuất.

## What is Aspose Tasks Java Tutorial?
Một **aspose tasks java tutorial** cung cấp hướng dẫn thực hành để sử dụng API Aspose.Tasks trong các dự án Java. Nó chỉ cho bạn cách đọc, sửa đổi và phân tích dữ liệu Microsoft Project mà không cần Microsoft Project.

## Why use Aspose.Tasks to determine project version?
- **No dependency on Microsoft Project** – Không phụ thuộc vào Microsoft Project – lý tưởng cho tự động hoá phía máy chủ.  
- **Accurate version metadata** – Siêu dữ liệu phiên bản chính xác – lấy các trường SAVE_VERSION và LAST_SAVED một cách chính xác.  
- **Cross‑platform** – Đa nền tảng – hoạt động trên bất kỳ hệ điều hành nào hỗ trợ Java.  
- **High performance** – Hiệu năng cao – phân tích nhẹ phù hợp cho xử lý hàng loạt.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn bạn có những thứ sau:

1. **Java Development Kit (JDK)** – bất kỳ JDK nào mới (phiên bản 8 trở lên).  
2. **Aspose.Tasks for Java JAR** – tải xuống từ [website](https://releases.aspose.com/tasks/java/) và thêm vào classpath của dự án.  
3. **MS Project file** – một tệp Project dựa trên XML (ví dụ, `input.xml`) mà bạn muốn kiểm tra.  

> **Pro tip:** Giữ tệp Project trong thư mục `data` riêng để đơn giản hoá việc xử lý đường dẫn.

## Import Packages
Đầu tiên, nhập các lớp Aspose.Tasks cần thiết:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step 1: Set Up the Project Directory
Xác định thư mục chứa tệp Project của bạn.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối hoặc tương đối nơi chứa `input.xml`.

## Step 2: Load the Project
Tạo một thể hiện `Project` bằng cách tải tệp XML.

```java
Project project = new Project(dataDir + "input.xml");
```

Nếu tệp của bạn có tên khác, hãy điều chỉnh `"input.xml"` cho phù hợp.

## Step 3: How to Determine Project Version
Lấy thông tin phiên bản và thời gian lưu lần cuối.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Thuộc tính `Prj.SAVE_VERSION` cho biết phiên bản Microsoft Project đã được sử dụng để lưu tệp (ví dụ, 12 cho Project 2010). `Prj.LAST_SAVED` trả về ngày/giờ của lần lưu gần nhất.

## Step 4: Display Result
Thông báo hoàn thành thành công kiểm tra phiên bản.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| `NullPointerException` on `project.get(...)` | Không tìm thấy tệp hoặc đường dẫn không đúng | Kiểm tra `dataDir` và tên tệp; sử dụng đường dẫn tuyệt đối để thử nghiệm. |
| Unexpected version number (e.g., 0) | Đang tải tệp XML không phải của Project | Đảm bảo tệp là tệp Microsoft Project hợp lệ (MPP/XML). |
| License exception | Sử dụng bản dùng thử mà không có giấy phép hợp lệ trong môi trường sản xuất | Áp dụng giấy phép Aspose.Tasks của bạn (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently Asked Questions

### Q: Can I use Aspose.Tasks with other programming languages?
A: Có, Aspose.Tasks hỗ trợ nhiều ngôn ngữ bao gồm .NET, Java và C++.

### Q: Is Aspose.Tasks suitable for large‑scale projects?
A: Chắc chắn, Aspose.Tasks được thiết kế để xử lý các dự án có quy mô bất kỳ một cách dễ dàng.

### Q: Can I customize project data using Aspose.Tasks?
A: Có, bạn có thể thao tác dữ liệu dự án, sửa đổi nhiệm vụ, nguồn lực và nhiều hơn nữa bằng Aspose.Tasks.

### Q: Does Aspose.Tasks require Microsoft Project installation?
A: Không, Aspose.Tasks hoạt động độc lập và không yêu cầu cài đặt Microsoft Project.

### Q: Is technical support available for Aspose.Tasks?
A: Có, bạn có thể nhận hỗ trợ kỹ thuật từ diễn đàn Aspose.Tasks tại [here](https://forum.aspose.com/c/tasks/15).

## Additional Q&A

**Q: How do I retrieve other project properties (e.g., author, company)?**  
A: Sử dụng `project.get(Prj.AUTHOR)` hoặc `project.get(Prj.COMPANY)` tương tự như ví dụ về phiên bản.

**Q: Can I check the version of an MPP file (binary format)?**  
A: Có, Aspose.Tasks có thể tải trực tiếp các tệp `.mpp`; thuộc tính `Prj.SAVE_VERSION` vẫn hoạt động.

**Q: Is there a way to programmatically upgrade an older project file to a newer version?**  
A: Tải tệp cũ, sau đó lưu lại bằng `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks sẽ ghi nó ở định dạng mới nhất theo mặc định.

## Conclusion
Bạn đã hoàn thành một **aspose tasks java tutorial** ngắn gọn, cho thấy **cách xác định phiên bản dự án** của các tệp MS Project bằng Aspose.Tasks cho Java. Tích hợp đoạn mã này vào các quy trình tự động hoá lớn hơn, công cụ báo cáo hoặc tiện ích di chuyển để luôn biết chính xác phiên bản Project bạn đang làm việc.

---

**Last Updated:** 2025-12-25  
**Cập nhật lần cuối:** 2025-12-25  
**Tested With:** Aspose.Tasks for Java 24.11  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}