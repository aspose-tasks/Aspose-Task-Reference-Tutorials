---
date: 2026-04-01
description: Tìm hiểu cách lưu XML, thiết lập năm tài chính và chuyển đổi MPP sang
  XML bằng Aspose.Tasks cho Java. Hướng dẫn từng bước kèm ví dụ mã.
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: Cách lưu XML & quản lý năm tài chính trong Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách lưu XML & quản lý năm tài chính trong Aspose.Tasks
url: /vi/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lưu XML & Quản lý năm tài chính trong Aspose.Tasks

## Giới thiệu
Nếu bạn cần **how to save xml** các tệp được tạo từ dữ liệu Microsoft Project, Aspose.Tasks for Java cung cấp cho bạn một cách sạch sẽ, không cần giấy phép để thực hiện. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách tải tệp MPP, hiển thị thông tin năm tài chính, thiết lập các thuộc tính năm tài chính, và cuối cùng **how to save xml** đầu ra. Bạn cũng sẽ thấy cách **how to set fiscal** chi tiết và **how to convert mpp** các tệp mà không cần mở Microsoft Project.

## Câu trả lời nhanh
- **Quản lý năm tài chính có nghĩa là gì trong Aspose.Tasks?** Nó cho phép bạn xác định tháng bắt đầu năm tài chính và bật đánh số năm tài chính cho một dự án.  
- **Làm thế nào để đặt tháng bắt đầu năm tài chính?** Sử dụng thuộc tính `Prj.FY_START_DATE` với giá trị enum `Month` (ví dụ, `Month.JULY`).  
- **Tôi có thể tải tệp MPP không?** Có, chỉ cần tạo một thể hiện `Project` với đường dẫn tới tệp *.mpp*.  
- **Làm thế nào để chuyển đổi MPP sang XML?** Gọi `project.save(..., SaveFileFormat.Xml)` sau khi đã thiết lập các thuộc tính mong muốn.  
- **Tôi có cần giấy phép không?** Một bản dùng thử miễn phí có sẵn; giấy phép thương mại là bắt buộc cho việc sử dụng trong môi trường sản xuất.  

## Quản lý năm tài chính là gì trong các tệp dự án?
Quản lý năm tài chính có nghĩa là cấu hình lịch mà dự án của bạn tuân theo cho báo cáo tài chính. Điều này bao gồm việc đặt tháng bắt đầu của năm tài chính và tùy chọn bật đánh số năm tài chính, điều này ảnh hưởng đến cách tính và hiển thị ngày trong các báo cáo.

## Tại sao nên sử dụng Aspose.Tasks để xử lý năm tài chính?
- **Không cần Microsoft Project** – làm việc với các tệp dự án trực tiếp trong Java.  
- **Kiểm soát đầy đủ** – đặt tháng bắt đầu năm tài chính, bật đánh số, và chuyển đổi định dạng bằng chương trình.  
- **API mạnh mẽ** – xử lý đáng tin cậy các tệp MPP lớn và xuất XML liền mạch.  

## Yêu cầu trước
1. Java Development Kit (JDK) đã được cài đặt trên hệ thống của bạn.  
2. Aspose.Tasks for Java JAR – tải xuống từ [here](https://releases.aspose.com/tasks/java/) và thêm vào classpath của dự án.  

## Nhập gói
Để bắt đầu, nhập các lớp cần thiết vào tệp nguồn Java của bạn:
```java
import com.aspose.tasks.*;
```

## Cách tải tệp MPP và hiển thị thông tin năm tài chính
Dưới đây chúng tôi sẽ phân tích quy trình thành các bước rõ ràng, có đánh số.

### Bước 1: Tải tệp dự án
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Ở đây chúng tôi **load an MPP file** (`project.mpp`) từ thư mục đã chỉ định. Đây là bước đầu tiên trong bất kỳ thao tác nào liên quan đến năm tài chính.

### Bước 2: Hiển thị thuộc tính năm tài chính
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
Các thuộc tính `Prj.FY_START_DATE` và `Prj.FISCAL_YEAR_START` cho phép bạn **display fiscal year** chi tiết, trả lời câu hỏi “cấu hình năm tài chính hiện tại là gì?”.  

### Bước 3: Đặt tháng bắt đầu năm tài chính và bật đánh số
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Trong bước này chúng tôi **how to set fiscal** các cài đặt:
- `Month.JULY` xác định tháng bắt đầu năm tài chính.  
- `NullableBool(true)` bật đánh số năm tài chính.  
- Cuối cùng, dự án được **converted MPP to XML** bằng cách sử dụng `SaveFileFormat.Xml`.  

### Bước 4: Xác nhận thao tác
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
Một thông báo console đơn giản xác nhận rằng năm tài chính đã được cấu hình và tệp đã được lưu.

## Tại sao điều này quan trọng
Lưu dự án dưới dạng XML cung cấp cho bạn một đại diện dạng văn bản, di động, có thể dễ dàng phân tích, kiểm soát phiên bản, hoặc tích hợp với các hệ thống khác. Khi cài đặt năm tài chính đúng, các báo cáo tài chính và bảng điều khiển downstream sẽ phù hợp với các kỳ kế toán của tổ chức bạn.

## Các trường hợp sử dụng phổ biến
- **Báo cáo tài chính** – Đồng bộ lịch trình dự án với lịch tài chính trước khi xuất ra công cụ BI.  
- **Di chuyển dữ liệu** – Chuyển đổi các tệp *.mpp* cũ sang XML để nhập vào các nền tảng quản lý dự án dựa trên đám mây.  
- **Kiểm toán tự động** – Kiểm tra bằng chương trình rằng mọi dự án đều sử dụng tháng bắt đầu năm tài chính đúng.  

## Mẹo khắc phục sự cố & Những cạm bẫy phổ biến
| Vấn đề | Giải pháp |
|-------|----------|
| **Giá trị tháng không đúng** | Đảm bảo bạn sử dụng enum `Month` (ví dụ, `Month.JANUARY`). |
| **Không tìm thấy tệp** | Xác minh `dataDir` trỏ tới thư mục đúng và tên tệp khớp. |
| **Lưu thất bại** | Kiểm tra quyền ghi trên thư mục đích và rằng `SaveFileFormat` được hỗ trợ. |
| **Năm tài chính không hiển thị trong XML** | Sau khi lưu, mở XML và xác nhận các nút `<FiscalYearStart>` và `<FiscalYearNumbering>` chứa giá trị mong đợi. |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java để thao tác các thuộc tính dự án khác không?**  
A: Có, Aspose.Tasks cung cấp chức năng toàn diện để quản lý nhiều thuộc tính dự án ngoài cài đặt năm tài chính.

**Q: Aspose.Tasks cho Java có tương thích với các định dạng tệp dự án khác nhau không?**  
A: Có, nó hỗ trợ nhiều định dạng bao gồm MPP, XML và các định dạng khác.

**Q: Làm thế nào để tôi nhận được hỗ trợ nếu gặp vấn đề khi sử dụng Aspose.Tasks cho Java?**  
A: Bạn có thể tìm kiếm trợ giúp từ cộng đồng Aspose.Tasks trên [forum](https://forum.aspose.com/c/tasks/15) hoặc liên hệ trực tiếp với đội ngũ hỗ trợ của họ.

**Q: Aspose.Tasks có cung cấp phiên bản dùng thử miễn phí không?**  
A: Có, bạn có thể truy cập phiên bản dùng thử miễn phí của Aspose.Tasks từ [here](https://releases.aspose.com/).

**Q: Tôi có thể mua giấy phép cho Aspose.Tasks cho Java ở đâu?**  
A: Bạn có thể mua giấy phép cho Aspose.Tasks cho Java từ [here](https://purchase.aspose.com/buy).

## Kết luận
Quản lý các thuộc tính năm tài chính trong Aspose.Tasks for Java rất đơn giản. Bằng cách thực hiện các bước trên, bạn có thể **how to save xml**, **load mpp file**, **display fiscal year**, **set fiscal year**, và **convert mpp to xml** một cách tự tin. Sử dụng các kỹ thuật này để giữ lịch trình dự án phù hợp với lịch tài chính của tổ chức và tạo ra các đại diện XML di động cho việc xử lý downstream.

---

**Last Updated:** 2026-04-01  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}