---
title: Truy xuất mã phác thảo dự án MS trong Aspose.Tasks
linktitle: Truy xuất mã phác thảo trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách truy xuất mã phác thảo Microsoft Project theo chương trình bằng cách sử dụng Aspose.Tasks cho Java. Nâng cao khả năng quản lý dự án của bạn.
weight: 15
url: /vi/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Truy xuất mã phác thảo dự án MS trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách truy xuất mã phác thảo Microsoft Project bằng Aspose.Tasks cho Java. Mã phác thảo trong MS Project cung cấp một cách có cấu trúc để phân loại và sắp xếp các nhiệm vụ, tài nguyên và nhiệm vụ của dự án. Aspose.Tasks là một thư viện Java mạnh mẽ cho phép các nhà phát triển thao tác và quản lý các tệp Microsoft Project theo chương trình.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:
### 1. Môi trường phát triển Java
Đảm bảo bạn đã cài đặt Bộ công cụ phát triển Java (JDK) trên hệ thống của mình. Bạn có thể tải xuống và cài đặt JDK từ trang web của Oracle.
### 2. Thư viện Aspose.Tasks
 Tải xuống và đưa thư viện Aspose.Tasks vào dự án Java của bạn. Bạn có thể tải xuống thư viện từ[Trang tải xuống Aspose.Tasks cho Java](https://releases.aspose.com/tasks/java/).
## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết từ Aspose.Tasks vào mã Java của bạn:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Bây giờ hãy chia mã ví dụ được cung cấp thành nhiều bước:
## Bước 1: Tải dự án
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 Trong bước này, chúng ta tải tệp Microsoft Project vào một`Project` đối tượng bằng cách sử dụng tên tệp được cung cấp.
## Bước 2: Truy xuất mã phác thảo
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Chúng tôi lặp lại qua từng định nghĩa mã phác thảo trong dự án.
## Bước 3: Truy cập thuộc tính mã phác thảo
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Chúng tôi truy xuất và in các thuộc tính khác nhau của định nghĩa mã phác thảo, chẳng hạn như Bí danh, ID trường và Tên trường.
## Bước 4: Kiểm tra mã tùy chỉnh doanh nghiệp
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Chúng tôi kiểm tra xem mã phác thảo có phải là mã tùy chỉnh của doanh nghiệp hay không và in kết quả tương ứng.
## Bước 5: Hiển thị mặt nạ mã phác thảo
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Chúng tôi lặp qua từng mặt nạ được liên kết với mã phác thảo và in cấp độ cũng như giá trị mặt nạ của nó.
## Bước 6: Hiển thị giá trị mã phác thảo
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Chúng tôi lặp qua từng giá trị mã phác thảo và in mô tả, ID giá trị, giá trị và loại của nó.
## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách truy xuất mã phác thảo MS Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước được cung cấp, bạn có thể truy cập và thao tác các mã phác thảo một cách hiệu quả trong các ứng dụng Java của mình, cho phép các khả năng quản lý dự án nâng cao.
## Câu hỏi thường gặp
### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks cho Java để sửa đổi mã phác thảo trong tệp Dự án không?
Trả lời: Có, Aspose.Tasks for Java cung cấp các API để sửa đổi mã phác thảo trong tệp MS Project theo chương trình.
### Câu hỏi 2: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
 Đáp: Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Tasks cho Java từ[Trang web Aspose.Tasks](https://releases.aspose.com/).
### Câu hỏi 3: Làm cách nào tôi có thể nhận được hỗ trợ kỹ thuật cho Aspose.Tasks cho Java?
 Đáp: Bạn có thể nhận được hỗ trợ kỹ thuật bằng cách truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) và đăng truy vấn của bạn ở đó.
### Câu hỏi 4: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?
 Đáp: Có, bạn có thể mua giấy phép tạm thời cho Aspose.Tasks for Java từ[trang mua hàng](https://purchase.aspose.com/temporary-license/).
### Câu hỏi 5: Tôi có thể tìm tài liệu đầy đủ về Aspose.Tasks cho Java ở đâu?
 Đáp: Bạn có thể tham khảo[tài liệu](https://reference.aspose.com/tasks/java/) để biết thông tin chi tiết về cách sử dụng Aspose.Tasks cho Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
