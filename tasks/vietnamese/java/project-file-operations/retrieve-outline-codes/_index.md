---
date: 2026-03-27
description: Học cách truy xuất mã phác thảo của MS Project một cách lập trình bằng
  Aspose.Tasks cho Java. Nâng cao khả năng quản lý dự án của bạn.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lấy mã đề cương MS Project trong Aspose.Tasks
url: /vi/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Truy xuất MS Project Outline Codes trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách truy xuất ms project outline codes** bằng cách sử dụng Aspose.Tasks cho Java. Mã đề cương trong MS Project cung cấp cho bạn một cách mạnh mẽ để phân loại công việc, nguồn lực và phân công, và việc truy cập chúng một cách lập trình cho phép bạn xây dựng các báo cáo tùy chỉnh, tự động hoá hoặc giải pháp tích hợp. Chúng tôi sẽ hướng dẫn qua một ví dụ đầy đủ, từng bước mà bạn có thể sao chép vào dự án của mình.

## Câu trả lời nhanh
- **What does the code do?** Nó tải một tệp Project và in ra mọi định nghĩa mã đề cương, các mặt nạ và các giá trị của chúng.  
- **Which library is required?** Aspose.Tasks for Java (bất kỳ phiên bản mới nào).  
- **Do I need a license?** Bản dùng thử hoạt động cho phát triển; cần giấy phép đầy đủ cho môi trường sản xuất.  
- **What Java version is supported?** Java 8 hoặc cao hơn.  
- **Can I modify the codes after retrieving them?** Có – cùng API cho phép bạn thêm, chỉnh sửa hoặc xóa mã đề cương.

## ms project outline codes là gì?
Mã đề cương là các trường tùy chỉnh cho phép các quản lý dự án nhóm và lọc công việc vượt ra ngoài cấu trúc phân cấp mặc định. Chúng có thể là các giá trị số đơn giản, chuỗi, hoặc thậm chí là các mã tùy chỉnh toàn doanh nghiệp được định nghĩa ở cấp tổ chức. Bằng cách đọc các mã này, bạn có thể điều khiển bảng điều khiển, xuất dữ liệu, hoặc tự động thực thi quy tắc đặt tên.

## Tại sao phải truy xuất ms project outline codes bằng Aspose.Tasks?
- **Automation:** Tạo báo cáo hoặc kích hoạt quy trình làm việc mà không cần xuất thủ công.  
- **Integration:** Đồng bộ mã đề cương với ERP, PPM hoặc công cụ BI.  
- **Customization:** Áp dụng quy tắc kinh doanh dựa trên giá trị mã (ví dụ: phân bổ chi phí).  
- **Cross‑platform:** Hoạt động trên Windows, Linux và macOS, độc lập với giao diện Microsoft Project.

## Cách đọc tệp MPP để lấy mã đề cương?
Đọc tệp MPP (Microsoft Project) là bước đầu tiên để trích xuất mã đề cương. Aspose.Tasks trừu tượng hoá định dạng tệp, vì vậy bạn không cần tự phân tích cấu trúc nhị phân. Lớp `Project` thực hiện phần công việc nặng, cho phép bạn tập trung vào dữ liệu thực sự cần thiết.

## Trường tùy chỉnh trong MS Project
Mã đề cương là một loại **custom fields** trong MS Project. Trong khi các trường tiêu chuẩn bao gồm ngày, thời lượng và nguồn lực, các trường tùy chỉnh cho phép bạn lưu trữ thông tin đặc thù của tổ chức. Truy cập chúng qua Aspose.Tasks mang lại cho bạn cùng mức độ linh hoạt lập trình.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã thiết lập các yêu cầu trước sau:

### 1. Môi trường phát triển Java
Đảm bảo bạn đã cài đặt Java Development Kit (JDK) trên hệ thống. Bạn có thể tải và cài đặt JDK từ trang web của Oracle.

### 2. Thư viện Aspose.Tasks
Tải và bao gồm thư viện Aspose.Tasks vào dự án Java của bạn. Bạn có thể tải thư viện từ [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/).

## Nhập các gói
Đầu tiên, nhập các gói cần thiết từ Aspose.Tasks trong mã Java của bạn:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Bây giờ chúng ta sẽ phân tích mã ví dụ đã cung cấp thành nhiều bước:

## Bước 1: Tải dự án
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
Trong bước này, chúng ta tải tệp Microsoft Project vào một đối tượng `Project` bằng cách sử dụng tên tệp đã cung cấp.

## Bước 2: Truy xuất mã đề cương
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Chúng ta lặp qua mỗi định nghĩa mã đề cương trong dự án.

## Bước 3: Truy cập thuộc tính mã đề cương
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Chúng ta lấy và in ra các thuộc tính khác nhau của định nghĩa mã đề cương như Alias, Field ID và Field Name.

## Bước 4: Kiểm tra mã tùy chỉnh doanh nghiệp
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Chúng ta kiểm tra xem mã đề cương có phải là mã tùy chỉnh doanh nghiệp không và in kết quả tương ứng.

## Bước 5: Hiển thị mặt nạ mã đề cương
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Chúng ta lặp qua mỗi mặt nạ liên quan đến mã đề cương và in ra mức độ và giá trị mặt nạ.

## Bước 6: Hiển thị giá trị mã đề cương
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Chúng ta lặp qua mỗi giá trị mã đề cương và in ra mô tả, ID giá trị, giá trị và loại.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| **No output** | Đường dẫn tệp dự án không đúng | Xác minh `projectName` trỏ tới một tệp `.mpp` hợp lệ. |
| **Null values** | Mã đề cương không được định nghĩa trong tệp | Đảm bảo tệp Project thực sự chứa mã đề cương (kiểm tra trong giao diện MS Project). |
| **LicenseException** | Sử dụng bản dùng thử mà chưa kích hoạt đúng | Áp dụng giấy phép tạm thời hoặc đầy đủ bằng cách sử dụng `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java để sửa đổi mã đề cương trong tệp Project không?**  
A: Có, Aspose.Tasks cho Java cung cấp API để sửa đổi mã đề cương một cách lập trình. Bạn có thể thêm, chỉnh sửa hoặc xóa các định nghĩa bằng cùng một đối tượng `Project`.

**Q: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể tải phiên bản dùng thử miễn phí của Aspose.Tasks cho Java từ [trang web Aspose.Tasks](https://releases.aspose.com/).

**Q: Làm thế nào tôi có thể nhận hỗ trợ kỹ thuật cho Aspose.Tasks cho Java?**  
A: Bạn có thể nhận hỗ trợ kỹ thuật bằng cách truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) và đăng câu hỏi của mình ở đó.

**Q: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java từ [trang mua hàng](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm tài liệu đầy đủ cho Aspose.Tasks cho Java ở đâu?**  
A: Bạn có thể tham khảo [tài liệu](https://reference.aspose.com/tasks/java/) để biết thông tin chi tiết về cách sử dụng Aspose.Tasks cho Java.

## Kết luận
Trong hướng dẫn này, chúng ta đã học cách truy xuất **ms project outline codes** bằng Aspose.Tasks cho Java. Bằng cách thực hiện các bước đã cung cấp, bạn có thể hiệu quả truy cập và thao tác với mã đề cương trong các ứng dụng Java của mình, cho phép các khả năng quản lý dự án nâng cao như báo cáo tùy chỉnh, tự động hoá và tích hợp với các hệ thống doanh nghiệp khác.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}