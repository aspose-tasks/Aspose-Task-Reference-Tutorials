---
date: 2025-12-20
description: Tìm hiểu cách lấy mã phác thảo của MS Project một cách lập trình bằng
  Aspose.Tasks cho Java. Nâng cao khả năng quản lý dự án của bạn.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Truy xuất mã Outline của MS Project trong Aspose.Tasks
url: /vi/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Truy xuất Mã Đề mục MS Project trong Aspose.Tasks

## Giới thiệu
Trong tutorial này, bạn sẽ khám phá **cách truy xuất mã đề mục ms project** bằng cách sử dụng Aspose.Tasks cho Java. Mã đề mục trong MS Project cung cấp cho bạn một cách mạnh mẽ để phân loại công việc, nguồn lực và phân công, và việc truy cập chúng bằng chương trình cho phép bạn xây dựng các báo cáo tùy chỉnh, tự động hoá hoặc các giải pháp tích hợp. Chúng tôi sẽ hướng dẫn qua một ví dụ đầy đủ, từng bước mà bạn có thể sao chép vào dự án của mình.

## Câu trả lời nhanh
- **Code này làm gì?** Nó tải một tệp Project và in ra mọi định nghĩa mã đề mục, các mặt nạ và các giá trị của chúng.  
- **Thư viện nào được yêu cầu?** Aspose.Tasks cho Java (bất kỳ phiên bản gần đây nào).  
- **Tôi có cần giấy phép không?** Bản dùng thử hoạt động cho phát triển; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc cao hơn.  
- **Tôi có thể chỉnh sửa các mã sau khi truy xuất không?** Có – cùng API cho phép bạn thêm, chỉnh sửa hoặc xóa mã đề mục.

## Mã đề mục ms project là gì?
Mã đề mục là các trường tùy chỉnh cho phép các nhà quản lý dự án nhóm và lọc công việc vượt ra ngoài cấu trúc phân cấp mặc định. Chúng có thể là các giá trị số đơn giản, chuỗi ký tự, hoặc thậm chí là các mã tùy chỉnh toàn doanh nghiệp được định nghĩa ở cấp tổ chức. Bằng cách đọc các mã này, bạn có thể điều khiển bảng điều khiển, xuất dữ liệu, hoặc tự động áp dụng quy tắc đặt tên.

## Tại sao phải truy xuất mã đề mục ms project bằng Aspose.Tasks?
- **Tự động hoá:** Tạo báo cáo hoặc kích hoạt quy trình làm việc mà không cần xuất thủ công.  
- **Tích hợp:** Đồng bộ mã đề mục với ERP, PPM hoặc công cụ BI.  
- **Tùy chỉnh:** Áp dụng quy tắc kinh doanh dựa trên giá trị mã (ví dụ: phân bổ chi phí).  
- **Đa nền tảng:** Hoạt động trên Windows, Linux và macOS, độc lập với giao diện Microsoft Project.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã thiết lập các yêu cầu trước sau:

### 1. Môi trường phát triển Java
Đảm bảo bạn đã cài đặt Java Development Kit (JDK) trên hệ thống của mình. Bạn có thể tải và cài đặt JDK từ trang web của Oracle.

### 2. Thư viện Aspose.Tasks
Tải và đưa thư viện Aspose.Tasks vào dự án Java của bạn. Bạn có thể tải thư viện từ [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/).

## Nhập các gói
Đầu tiên, nhập các gói cần thiết từ Aspose.Tasks trong mã Java của bạn:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Bây giờ chúng ta sẽ phân tích mã ví dụ được cung cấp thành nhiều bước:

## Bước 1: Tải dự án
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
Trong bước này, chúng ta tải tệp Microsoft Project vào một đối tượng `Project` bằng cách sử dụng tên tệp đã cung cấp.

## Bước 2: Truy xuất mã đề mục
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Chúng ta lặp qua mỗi định nghĩa mã đề mục trong dự án.

## Bước 3: Truy cập thuộc tính mã đề mục
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Chúng ta lấy và in ra các thuộc tính khác nhau của định nghĩa mã đề mục như Alias, Field ID và Field Name.

## Bước 4: Kiểm tra mã tùy chỉnh doanh nghiệp
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Chúng ta kiểm tra xem mã đề mục có phải là mã tùy chỉnh doanh nghiệp không và in kết quả tương ứng.

## Bước 5: Hiển thị mặt nạ mã đề mục
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Chúng ta lặp qua mỗi mặt nạ liên quan đến mã đề mục và in ra cấp độ và giá trị mặt nạ.

## Bước 6: Hiển thị giá trị mã đề mục
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Chúng ta lặp qua mỗi giá trị mã đề mục và in ra mô tả, ID giá trị, giá trị và loại.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| **Không có đầu ra** | Đường dẫn tệp dự án không đúng | Xác minh `projectName` trỏ tới một tệp `.mpp` hợp lệ. |
| **Giá trị null** | Mã đề mục không được định nghĩa trong tệp | Đảm bảo tệp Project thực sự chứa các mã đề mục (kiểm tra trong giao diện MS Project). |
| **LicenseException** | Sử dụng bản dùng thử mà không kích hoạt đúng cách | Áp dụng giấy phép tạm thời hoặc đầy đủ bằng cách sử dụng `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java để chỉnh sửa mã đề mục trong tệp Project không?**  
A: Có, Aspose.Tasks cho Java cung cấp API để chỉnh sửa mã đề mục bằng chương trình. Bạn có thể thêm, sửa hoặc xóa các định nghĩa bằng cùng một đối tượng `Project`.

**Q: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể tải phiên bản dùng thử miễn phí của Aspose.Tasks cho Java từ [trang web Aspose.Tasks](https://releases.aspose.com/).

**Q: Làm thế nào tôi có thể nhận hỗ trợ kỹ thuật cho Aspose.Tasks cho Java?**  
A: Bạn có thể nhận hỗ trợ kỹ thuật bằng cách truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) và đăng câu hỏi của mình ở đó.

**Q: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java từ [trang mua hàng](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm tài liệu đầy đủ cho Aspose.Tasks cho Java ở đâu?**  
A: Bạn có thể tham khảo [tài liệu](https://reference.aspose.com/tasks/java/) để biết thông tin chi tiết về cách sử dụng Aspose.Tasks cho Java.

## Kết luận
Trong tutorial này, chúng ta đã học cách truy xuất **mã đề mục ms project** bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước đã cung cấp, bạn có thể hiệu quả truy cập và thao tác các mã đề mục trong các ứng dụng Java của mình, cho phép các khả năng quản lý dự án nâng cao như báo cáo tùy chỉnh, tự động hoá và tích hợp với các hệ thống doanh nghiệp khác.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}