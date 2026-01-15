---
date: 2026-01-15
description: Tìm hiểu cách làm việc với công việc chi phí ngân sách được lên lịch
  trong các tệp Microsoft Project bằng Aspose.Tasks cho Java. Hãy làm theo hướng dẫn
  từng bước của chúng tôi.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Công việc chi phí dự toán đã lên lịch với Aspose.Tasks cho Java
url: /vi/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chi phí công việc đã lên kế hoạch (budgeted cost work scheduled) với Aspose.Tasks cho Java

## Giới thiệu

Quản lý **budgeted cost work scheduled** (BCWS) là yếu tố quan trọng để duy trì dự án trên đúng lộ trình và đảm bảo dự báo tài chính phù hợp với công việc đã lên kế hoạch. Trong Microsoft Project, BCWS biểu thị số tiền nên đã được chi cho công việc đã lên lịch đến một ngày cụ thể. Aspose.Tasks cho Java cung cấp cho bạn quyền kiểm soát lập trình đầy đủ đối với các giá trị này, cho phép bạn đọc, sửa đổi và báo cáo chi phí nguồn lực mà không cần mở file .mpp thủ công. Trong hướng dẫn này, chúng ta sẽ đi qua một ví dụ hoàn chỉnh cho thấy cách tải dự án, duyệt qua các nguồn lực và hiển thị budgeted cost work scheduled cùng các chỉ số chi phí quan trọng khác.

## Trả lời nhanh
- **BCWS có nghĩa là gì?** Budgeted Cost Work Scheduled – chi phí dự kiến cho công việc đã lên lịch đến hiện tại.  
- **Thuộc tính API nào trả về BCWS?** `Rsc.BCWS` trên đối tượng `Resource`.  
- **Có cần giấy phép để chạy mẫu không?** Giấy phép dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Có thể sửa giá trị BCWS không?** Có, bạn có thể đặt `Rsc.BCWS` giống như bất kỳ trường số nào khác.  
- **Các phiên bản Project được hỗ trợ?** Tất cả các phiên bản Microsoft Project từ 2000 đến định dạng .mpp mới nhất.

## Budgeted Cost Work Scheduled là gì?

**Budgeted Cost Work Scheduled (BCWS)** là một chỉ số hiệu suất phản ánh chi phí lẽ ra phải phát sinh cho công việc đã lên kế hoạch đến một thời điểm nhất định. Đây là nền tảng của Earned Value Management (EVM) và giúp các nhà quản lý dự án so sánh chi phí dự kiến với chi phí thực tế.

## Yêu cầu trước

Trước khi bắt đầu với mã, hãy chắc chắn rằng bạn đã có:

1. Kiến thức vững về các nguyên tắc cơ bản của Java.  
2. Aspose.Tasks cho Java đã được thêm vào dự án của bạn (Maven/Gradle hoặc JAR).  
3. Một file Microsoft Project (`.mpp`) chứa các nguồn lực có dữ liệu chi phí (ví dụ: *ResourceCosts.mpp*).

## Nhập gói

Đầu tiên, nhập các lớp Aspose.Tasks cần thiết để xử lý dự án và nguồn lực:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Bước 1: Xác định thư mục dữ liệu

```java
String dataDir = "Your Data Directory";
```

Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối hoặc tương đối nơi lưu trữ *ResourceCosts.mpp*.

## Bước 2: Tải file MS Project

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

Constructor `Project` đọc file .mpp và tạo ra một biểu diễn trong bộ nhớ mà bạn có thể truy vấn.

## Bước 3: Duyệt qua các nguồn lực

```java
for (Resource res : prj.getResources()) {
```

Vòng lặp này đi qua mọi nguồn lực được định nghĩa trong dự án, cho phép bạn truy cập vào các trường chi phí của chúng.

## Bước 4: Kiểm tra tên nguồn lực và chi phí

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Trong khối `if` chúng ta:

* In **tổng chi phí** (`Rsc.COST`).  
* In **chi phí thực tế của công việc đã thực hiện** (`Rsc.ACWP`).  
* In **budgeted cost work scheduled** (`Rsc.BCWS`) – chỉ số chính mà chúng ta đang tập trung.  
* In **budgeted cost work performed** (`Rsc.BCWP`).

Bốn giá trị này cung cấp cho bạn một bức tranh nhanh về tình hình tài chính của dự án.

## Tại sao việc giám sát budgeted cost work scheduled lại quan trọng

* **Cảnh báo sớm:** Nếu BCWS cao đáng kể so với chi phí thực tế, bạn có thể đang phân bổ nguồn lực quá mức.  
* **Phân tích Earned Value:** BCWS là đầu vào quan trọng để tính Cost Variance (CV) và Schedule Variance (SV).  
* **Dự báo:** Dữ liệu BCWS chính xác giúp dự đoán nhu cầu dòng tiền trong tương lai và hỗ trợ báo cáo cho các bên liên quan.

## Các vấn đề thường gặp & Khắc phục

| Triệu chứng | Nguyên nhân khả dĩ | Giải pháp |
|------------|---------------------|-----------|
| `null` được in cho BCWS | Nguồn lực không có bảng tỷ lệ chi phí được định nghĩa | Định nghĩa bảng tỷ lệ chi phí cho nguồn lực trong Microsoft Project hoặc thiết lập chương trình bằng `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` khi duyệt nguồn lực | File dự án bị hỏng hoặc chứa các mục nguồn lực rỗng | Kiểm tra file .mpp trong Microsoft Project và loại bỏ các nguồn lực rỗng |
| Giá trị bất thường (ví dụ: BCWS âm) | Các trường tùy chỉnh ghi đè lên các trường chi phí chuẩn | Đảm bảo bạn đang truy cập `Rsc.BCWS` chuẩn chứ không phải trường tùy chỉnh có cùng tên |

## Câu hỏi thường gặp

**H: Tôi có thể cập nhật giá trị BCWS bằng lập trình không?**  
Đ: Có. Sử dụng `res.set(Rsc.BCWS, newValue)` và sau đó lưu dự án bằng `prj.save("Updated.mpp")`.

**H: Aspose.Tasks có hỗ trợ dự án đa tiền tệ không?**  
Đ: Hoàn toàn có. Các trường chi phí tuân theo cài đặt tiền tệ được định nghĩa trong file Project.

**H: Có cách nào xuất các chỉ số chi phí này ra CSV không?**  
Đ: Bạn có thể duyệt qua các nguồn lực và ghi các giá trị vào `StringBuilder` hoặc sử dụng thư viện CSV để tạo file.

**H: BCWS khác BCWP như thế nào?**  
Đ: BCWS là chi phí dự kiến cho công việc đã lên lịch, trong khi BCWP (Budgeted Cost Work Performed) phản ánh chi phí dự kiến cho công việc đã thực tế hoàn thành.

**H: Tôi có cần giấy phép đặc biệt để đọc dữ liệu chi phí không?**  
Đ: Giấy phép dùng thử cung cấp quyền đọc/ghi đầy đủ; giấy phép thương mại cần thiết cho triển khai sản xuất.

## Kết luận

Bằng cách tận dụng Aspose.Tasks cho Java, bạn sẽ có quyền truy cập lập trình chính xác vào **budgeted cost work scheduled** và các chỉ số chi phí quan trọng khác. Điều này cho phép bạn xây dựng bảng điều khiển tùy chỉnh, tự động hoá báo cáo Earned Value và giữ cho dự án của bạn luôn ổn định về mặt tài chính — tất cả mà không cần tương tác thủ công với Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-01-15  
**Kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất)  
**Tác giả:** Aspose