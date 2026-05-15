---
date: 2026-01-13
description: Tìm hiểu cách lặp lại các tài nguyên không phải gốc trong các tệp Microsoft
  Project bằng cách sử dụng Aspose.Tasks cho Java.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Duyệt các tài nguyên không phải gốc với Aspose.Tasks cho Java
url: /vi/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Duyệt các tài nguyên không gốc bằng Aspose.Tasks cho Java

## Giới thiệu
Aspose.Tasks cho Java là một thư viện mạnh mẽ cung cấp cho các nhà phát triển cách làm việc với các tệp Microsoft Project một cách sạch sẽ, hướng đối tượng. Trong hướng dẫn này, bạn sẽ học **cách duyệt các tài nguyên không phải gốc** để có thể đọc, sửa đổi hoặc phân tích dữ liệu tài nguyên mà không phải xử lý nút placeholder gốc. Dù bạn đang xây dựng công cụ báo cáo, script di chuyển dữ liệu, hay bộ lập lịch tùy chỉnh, việc nắm vững kỹ thuật này sẽ giúp mã của bạn chính xác và hiệu quả hơn.

## Trả lời nhanh
- **“tài nguyên không gốc” có nghĩa là gì?** Một tài nguyên không phải là placeholder mặc định “Project” (nút gốc).  
- **Tại sao phải lọc bỏ tài nguyên gốc?** Nút gốc không có dữ liệu lập lịch hữu ích và có thể làm rối các báo cáo.  
- **Lớp Aspose.Tasks nào cung cấp bộ sưu tập tài nguyên?** `Project.getResources()`.  
- **Tôi có cần giấy phép cho đoạn mã này không?** Bản dùng thử miễn phí đủ cho việc phát triển; cần giấy phép thương mại cho môi trường sản xuất.  
- **Có thể dùng với Java 17 không?** Có – Aspose.Tasks hỗ trợ Java 8 trở lên.

## Yêu cầu trước
Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

1. **Java Development Kit (JDK)** – Cài đặt JDK mới nhất từ [trang web Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Thư viện Aspose.Tasks cho Java** – Tải JAR mới nhất từ [trang tải về](https://releases.aspose.com/tasks/java/).  

## Nhập khẩu các gói
Trong dự án Java của bạn, nhập các lớp cần thiết của Aspose.Tasks:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Bước 1: Thiết lập thư mục dữ liệu
```java
String dataDir = "Your Data Directory";
```
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối nơi lưu các tệp `.mpp` của bạn.

## Bước 2: Tải tệp dự án
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Đoạn mã này tạo một thể hiện `Project` bằng cách tải **ResourceCosts.mpp** từ thư mục bạn đã chỉ định.

## Bước 3: Duyệt các tài nguyên không gốc
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Vòng lặp sẽ duyệt qua mọi đối tượng `Resource` trong dự án. Kiểm tra `isRoot()` sẽ bỏ qua tài nguyên gốc được tích hợp sẵn, và câu lệnh `System.out.println` sẽ in ra tên của mỗi **tài nguyên không gốc**.

## Cách duyệt các tài nguyên không gốc
Đoạn mã trên minh họa mẫu cơ bản:

1. Lấy toàn bộ bộ sưu tập bằng `prj.getResources()`.  
2. Dùng `isRoot()` để lọc bỏ placeholder.  
3. Truy cập bất kỳ trường nào của tài nguyên (ví dụ: `Rsc.NAME`, `Rsc.COST`) khi cần.

Bạn có thể mở rộng mẫu này để tổng hợp chi phí, xuất ra CSV, hoặc áp dụng các quy tắc kinh doanh tùy chỉnh.

## Những lỗi thường gặp & Mẹo
- **Kiểm tra null** – Một số tài nguyên có thể có các trường tùy chọn; luôn kiểm tra `null` trước khi gọi `get()`.  
- **Hiệu năng** – Đối với các dự án rất lớn, cân nhắc duyệt bằng vòng lặp dựa trên chỉ mục để tránh tạo các bộ sưu tập trung gian.  
- **Giấy phép** – Chạy mã mà không có giấy phép hợp lệ sẽ thêm watermark vào các tệp xuất; hãy kích hoạt giấy phép sớm trong ứng dụng.

## Kết luận
Sau khi thực hiện các bước trên, bạn đã biết **cách duyệt các tài nguyên không gốc** bằng Aspose.Tasks cho Java. Kỹ thuật này giúp bạn tập trung vào các tài nguyên thực tế của dự án, làm sạch dữ liệu trích xuất và xây dựng các giải pháp quản lý dự án đáng tin cậy hơn.

## Câu hỏi thường gặp
### Tôi có thể dùng Aspose.Tasks cho Java để tạo tệp dự án mới không?
Có, Aspose.Tasks cung cấp đầy đủ khả năng CRUD (Create, Read, Update, Delete) cho các định dạng dự án MPP, MPT và XML.  

### Aspose.Tasks có hỗ trợ tất cả các phiên bản tệp Microsoft Project không?
Chắc chắn rồi. Thư viện xử lý các tệp Project 2003‑2019, bao gồm các đặc tả MPP mới nhất.  

### Aspose.Tasks có tương thích với các framework Java như Spring không?
Có, bạn có thể tiêm thư viện vào các bean Spring hoặc sử dụng trong bất kỳ ứng dụng Java tiêu chuẩn nào.  

### Tôi có thể tùy chỉnh các trường dữ liệu dự án bằng Aspose.Tasks không?
Có thể. API cho phép bạn thêm, sửa hoặc xóa các trường tùy chỉnh trên task, resource và assignment.  

### Aspose.Tasks có cung cấp hỗ trợ và tài liệu cho nhà phát triển không?
Sản phẩm bao gồm tài liệu API chi tiết, các mẫu mã, và diễn đàn hỗ trợ chuyên biệt để giúp bạn nhanh chóng giải quyết vấn đề.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-01-13  
**Kiểm thử với:** Aspose.Tasks cho Java 24.12  
**Tác giả:** Aspose  

---