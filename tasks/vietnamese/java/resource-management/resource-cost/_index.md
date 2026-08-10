---
date: 2026-06-15
description: Tìm hiểu cách quản lý chi phí trong các tệp MS Project bằng Aspose.Tasks
  cho Java, bao gồm cách tải tệp MPP và đọc actual cost work và budgeted cost schedule.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Xử lý Resource Cost trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách quản lý chi phí trong MS Project với Aspose.Tasks cho Java
url: /vi/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách quản lý chi phí trong MS Project với Aspose.Tasks cho Java

## Giới thiệu

Quản lý ngân sách dự án là một trách nhiệm cốt lõi của bất kỳ quản lý dự án nào, và **cách quản lý chi phí** hiệu quả có thể quyết định thành công hay thất bại của dự án. Aspose.Tasks cho Java cung cấp cho bạn khả năng kiểm soát lập trình các tệp Microsoft Project, cho phép bạn đọc và cập nhật dữ liệu chi phí nguồn lực mà không cần mở tệp .mpp bằng tay. Trong hướng dẫn này, bạn sẽ thấy từng bước cách tải tệp MPP, kiểm tra chi phí thực tế, và trích xuất lịch trình chi phí dự toán cho mỗi nguồn lực.

## Câu trả lời nhanh
- **Aspose.Tasks cho Java làm gì?** Nó đọc và ghi các tệp Microsoft Project (.mpp) mà không cần cài đặt Microsoft Project.  
- **Làm sao tôi có thể tải tệp MPP?** Sử dụng `new Project("path/to/file.mpp")` – API phân tích tệp trong bộ nhớ.  
- **Các trường chi phí nào có sẵn?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS), và Budgeted Cost of Work Performed (BCWP).  
- **Tôi có cần giấy phép cho việc phát triển không?** Một giấy phép tạm thời miễn phí hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Các phiên bản Java nào được hỗ trợ?** Java 8 trở lên, bao gồm Java 17 LTS.

## Cách quản lý chi phí trong MS Project?

Tải dự án của bạn bằng `new Project("yourFile.mpp")`, sau đó lặp qua từng đối tượng `Resource` để đọc các thuộc tính liên quan đến chi phí như ACWP, BCWS và BCWP. Aspose.Tasks tự động chuyển đổi các giá trị chi phí nội bộ sang tiền tệ của dự án, vì vậy bạn có thể hiển thị hoặc lưu trữ chúng trực tiếp. Cách tiếp cận này loại bỏ việc tính toán thủ công trên bảng tính và đảm bảo tính nhất quán dữ liệu trong tất cả các báo cáo dự án.

## Yêu cầu trước

1. Hiểu biết cơ bản về lập trình Java.  
2. Thư viện Aspose.Tasks cho Java đã được thêm vào dự án của bạn (Maven/Gradle hoặc JAR thủ công).  
3. Truy cập vào tệp Microsoft Project (`.mpp`) mà bạn muốn phân tích.  

## Nhập gói

Các lớp `Project` và `Resource` là điểm vào để làm việc với dữ liệu dự án.

Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks, đại diện cho một tệp Microsoft Project duy nhất trong bộ nhớ.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## Bước 1: Xác định thư mục dữ liệu

Đầu tiên, chỉ định thư mục chứa tệp `.mpp` của bạn. Đường dẫn này có thể là tuyệt đối hoặc tương đối so với thư mục làm việc của ứng dụng.  
```text
```java
String dataDir = "Your Data Directory";
```
```

## Bước 2: Tải tệp MS Project

`Project` tải tệp và xây dựng mô hình đối tượng mà bạn có thể truy vấn. API phân tích tệp mà không cần cài đặt Microsoft Project, hỗ trợ hơn 30 định dạng đầu vào.  
```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## Bước 3: Lặp qua các nguồn lực

Các đối tượng `Resource` đại diện cho con người, thiết bị hoặc vật liệu tiêu tốn ngân sách. Bạn có thể lặp qua bộ sưu tập `project.getResources()` để truy cập từng đối tượng.  
```text
```java
for (Resource res : prj.getResources()) {
```
```

## Bước 4: Kiểm tra tên và chi phí của nguồn lực

Đối với mỗi nguồn lực, xác minh rằng tên đã được xác định, sau đó đọc các trường chi phí. Phương thức `getActualCost()` trả về **chi phí thực tế** (ACWP), trong khi `getBudgetedCost()` cung cấp cho bạn **lịch trình chi phí dự toán** (BCWS/BCWP).  
```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## Tại sao nên sử dụng Aspose.Tasks cho Java để tải tệp MPP?

Aspose.Tasks hỗ trợ **hơn 30 định dạng tệp** (bao gồm `.mpp`, `.xml` và `.xlsx`) và có thể xử lý các dự án với **tối đa 10.000 công việc** trong khi sử dụng dưới 200 MB RAM. Thư viện thực hiện tất cả các phép tính trên phía máy chủ, loại bỏ nhu cầu có bản sao có giấy phép của Microsoft Project.

## Các vấn đề thường gặp và giải pháp

- **Tên nguồn lực null:** Một số tệp legacy chứa các nguồn lực placeholder. Luôn kiểm tra `resource.getName() != null` trước khi truy cập các thuộc tính chi phí.  
- **Tệp lớn gây áp lực bộ nhớ:** LoadOptions là một lớp cấu hình cho phép bạn chỉ định dữ liệu dự án nào sẽ được tải. Sử dụng `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` để chỉ tải dữ liệu cần thiết, sau đó bật lại nếu cần.  
- **Không khớp tiền tệ:** API tôn trọng cài đặt tiền tệ của dự án; bạn có thể ghi đè bằng `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` nếu cần. CostRateTableType liệt kê các bảng tỷ lệ chi phí khác nhau có thể áp dụng cho một công việc.

## Câu hỏi thường gặp

**Q: Aspose.Tasks cho Java có thể xử lý cấu trúc dự án phức tạp không?**  
A: Có, nó hoàn toàn hỗ trợ các công việc tổng hợp lồng nhau, nhiều lịch nguồn lực, và các trường tùy chỉnh trên tất cả các phiên bản Project được hỗ trợ.

**Q: Thư viện có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
A: Chắc chắn. Aspose.Tasks đọc và ghi các tệp từ Microsoft Project 2000 đến định dạng mới nhất 2023.

**Q: Tôi có thể tích hợp Aspose.Tasks cho Java với các thư viện Java khác không?**  
A: Có, API trả về các đối tượng Java tiêu chuẩn, cho phép tích hợp liền mạch với các framework ghi log, công cụ ORM, hoặc thư viện báo cáo.

**Q: Aspose.Tasks cho Java có cung cấp hỗ trợ khách hàng không?**  
A: Aspose cung cấp hỗ trợ diễn đàn chuyên dụng, tài liệu chi tiết, và hỗ trợ qua email nhanh chóng cho người dùng có giấy phép.

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks cho Java không?**  
A: Bạn có thể tải về giấy phép đánh giá 30 ngày từ trang web Aspose để khám phá tất cả các tính năng mà không tốn phí.

---

**Cập nhật lần cuối:** 2026-06-15  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Cách tính chênh lệch chi phí và quản lý chi phí giao nhiệm vụ với Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Quản lý ngân sách, công việc và chi phí cho các công việc trong Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Thêm nguồn lực vào dự án với Aspose.Tasks cho Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}