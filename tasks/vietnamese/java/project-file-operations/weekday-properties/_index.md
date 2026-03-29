---
date: 2026-03-29
description: Học cách thay đổi số ngày trong tháng và quản lý các thuộc tính ngày
  trong tuần khác trong Aspose.Tasks cho Java. Tùy chỉnh ngày bắt đầu tuần, chỉnh
  sửa lịch dự án và lưu dự án dưới dạng XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Thay đổi số ngày trong tháng bằng thuộc tính Weekday của Aspose.Tasks
url: /vi/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thay Đổi Số Ngày Mỗi Tháng Với Thuộc Tính Ngày Trong Tuần Của Aspose.Tasks

## Giới thiệu
Aspose.Tasks for Java cho phép bạn **thay đổi số ngày mỗi tháng** và tinh chỉnh các cài đặt ngày trong tuần khác mà không cần cài đặt Microsoft Project. Dù bạn đang điều chỉnh lịch dự án cho một tháng tài chính không chuẩn hoặc chỉ cần thay đổi ngày bắt đầu tuần, hướng dẫn này sẽ đưa bạn qua các kịch bản phổ biến nhất—lấy ngày bắt đầu tuần hiện tại, tùy chỉnh ngày bắt đầu tuần, sửa đổi lịch dự án và lưu dự án dưới dạng XML.

## Câu trả lời nhanh
- **Có thể thay đổi số ngày mỗi tháng không?** Có, sử dụng `Prj.DAYS_PER_MONTH` trên đối tượng `Project`.  
- **Làm thế nào để tùy chỉnh ngày bắt đầu tuần?** Đặt `Prj.WEEK_START_DAY` thành một giá trị `DayType` (ví dụ, `DayType.Monday`).  
- **Định dạng nào tôi có thể sử dụng để xuất dự án?** Ví dụ lưu tệp dưới dạng XML với `SaveFileFormat.Xml`.  
- **Cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần một giấy phép Aspose.Tasks hợp lệ cho các triển khai không phải thử nghiệm.  
- **IDE nào được hỗ trợ?** Bất kỳ IDE Java nào như IntelliJ IDEA, Eclipse hoặc NetBeans đều hoạt động.

## “Thay đổi số ngày mỗi tháng” trong Aspose.Tasks là gì?
Thay đổi số ngày mỗi tháng có nghĩa là cập nhật thuộc tính `Prj.DAYS_PER_MONTH` của một thể hiện `Project`. Thuộc tính này cho engine biết bao nhiêu ngày làm việc cần được tính cho mỗi tháng, ảnh hưởng trực tiếp đến việc lên lịch nhiệm vụ và tính toán chi phí.

## Tại sao cần sửa đổi các thuộc tính lịch dự án?
Tùy chỉnh lịch dự án—như đặt ngày bắt đầu tuần khác hoặc thay đổi số phút mỗi ngày—giúp bạn:

- Căn chỉnh lịch trình với tuần làm việc khu vực.  
- Mô hình các mô hình làm việc không chuẩn (ví dụ, tuần 4 ngày).  
- Đảm bảo báo cáo chính xác cho các hợp đồng sử dụng lịch tùy chỉnh.

## Yêu cầu trước
- **Java Development Kit (JDK)** – Cài đặt JDK mới nhất từ Oracle.  
- **Aspose.Tasks for Java library** – Tải xuống từ trang chính thức [here](https://releases.aspose.com/tasks/java/).  
- **IDE of your choice** – IntelliJ IDEA, Eclipse hoặc NetBeans.

## Nhập các gói
Đầu tiên, nhập các lớp Aspose.Tasks cần thiết:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Bước 1: Tải tệp dự án
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Điều này tải một tệp Microsoft Project hiện có (`project.mpp`) từ thư mục bạn chỉ định.

## Bước 2: Hiển thị các thuộc tính ngày trong tuần
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Ở đây chúng ta lấy và in ra các cài đặt ngày trong tuần hiện tại, bao gồm **ngày bắt đầu tuần** và **số ngày mỗi tháng**.

## Bước 3: Đặt các thuộc tính ngày trong tuần
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Trong bước này chúng ta **thay đổi số ngày mỗi tháng** thành 24, đặt tuần bắt đầu vào Thứ Hai và điều chỉnh số phút mỗi ngày/tuần. Điều này minh họa cách **sửa đổi lịch dự án** bằng lập trình.

## Bước 4: Lưu dự án
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Dự án đã sửa đổi được lưu bằng định dạng **save project as XML**, tiện cho việc tích hợp với các công cụ khác hoặc lưu trữ có kiểm soát phiên bản.

## Bước 5: Hiển thị kết quả
```java
System.out.println("Process completed Successfully");
```
Một xác nhận đơn giản rằng các thao tác đã hoàn thành mà không có lỗi.

## Cách tùy chỉnh ngày bắt đầu tuần
Nếu tổ chức của bạn sử dụng lịch bắt đầu vào Chủ Nhật, thay `DayType.Monday` bằng `DayType.Sunday`. Thuộc tính (`Prj.WEEK_START_DAY`) vẫn được sử dụng, nên việc thay đổi rất đơn giản.

## Cách lấy ngày bắt đầu tuần
Bạn có thể gọi `project.get(Prj.WEEK_START_DAY)` bất kỳ lúc nào để **lấy thông tin ngày bắt đầu tuần**, như đã minh họa ở Bước 2.

## Cách sửa đổi lịch dự án
Ngoài ngày bắt đầu tuần, bạn cũng có thể điều chỉnh `Prj.MINUTES_PER_DAY` và `Prj.MINUTES_PER_WEEK` để phản ánh giờ làm việc tùy chỉnh hoặc mô hình ca làm việc.

## Các vấn đề thường gặp và giải pháp
- **Giá trị loại ngày không đúng** – Đảm bảo bạn sử dụng enum `DayType` (ví dụ, `DayType.Monday`).  
- **Lỗi đường dẫn tệp** – Kiểm tra `dataDir` kết thúc bằng ký tự phân tách tệp thích hợp (`/` hoặc `\`).  
- **Chưa thiết lập giấy phép** – Nếu bạn thấy cảnh báo giấy phép, đăng ký giấy phép Aspose.Tasks trước khi tạo đối tượng `Project`.

## Câu hỏi thường gặp

**Q: Aspose.Tasks for Java có thể xử lý các cấu trúc dự án phức tạp không?**  
A: Có, Aspose.Tasks for Java cung cấp hỗ trợ toàn diện để xử lý các cấu trúc dự án phức tạp một cách dễ dàng.

**Q: Aspose.Tasks for Java có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
A: Chắc chắn, Aspose.Tasks for Java hỗ trợ nhiều phiên bản tệp Microsoft Project, đảm bảo tính tương thích trên các nền tảng.

**Q: Tôi có thể tích hợp Aspose.Tasks for Java vào các ứng dụng Java hiện có của mình không?**  
A: Có, Aspose.Tasks for Java cung cấp khả năng tích hợp liền mạch, cho phép bạn nâng cao các ứng dụng Java với các tính năng quản lý dự án mạnh mẽ.

**Q: Aspose.Tasks for Java có cung cấp tài liệu và hỗ trợ không?**  
A: Có, bạn có thể truy cập tài liệu chi tiết và hỗ trợ cộng đồng cho Aspose.Tasks for Java trên [website](https://releases.aspose.com/).

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks for Java không?**  
A: Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Tasks for Java từ [website](https://reference.aspose.com/tasks/java/) để khám phá các tính năng trước khi mua.

---

**Cập nhật lần cuối:** 2026-03-29  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}