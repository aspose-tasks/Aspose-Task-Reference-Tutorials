---
date: 2026-02-28
description: Tìm hiểu cách quản lý ngân sách, công việc và chi phí cho các nhiệm vụ
  trong dự án Java bằng Aspose.Tasks. Hướng dẫn này cũng chỉ cách tính chi phí nhiệm
  vụ một cách hiệu quả.
linktitle: Budget, Work, and Cost Management for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách quản lý ngân sách, công việc và chi phí trong Aspose.Tasks Java
url: /vi/java/task-properties/task-budget-work-cost/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Quản Lý Ngân Sách, Công Việc và Chi Phí trong Aspose.Tasks Java

Quản lý tài chính của dự án là một trách nhiệm cốt lõi của bất kỳ quản lý dự án nào. Trong hướng dẫn này, bạn sẽ khám phá **cách quản lý ngân sách** cho các công việc, work và tài nguyên bằng cách sử dụng Aspose.Tasks Java API, và cũng sẽ thấy cách **tính chi phí công việc** khi bạn cần báo cáo tài chính chính xác. Khi kết thúc hướng dẫn, bạn sẽ có thể đọc, hiển thị và thao tác các trường liên quan đến ngân sách trực tiếp từ các tệp Microsoft Project của mình.

## Câu trả lời nhanh
- **What does “budget work” represent?** Số lượng work (theo giờ) được phân bổ cho một task hoặc resource.  
- **Can I retrieve budget cost programmatically?** Có, bằng cách sử dụng trường `BUDGET_COST` trên các task, resource hoặc assignment.  
- **Do I need a license for Aspose.Tasks?** Cần có giấy phép cho môi trường production; một bản dùng thử miễn phí có sẵn.  
- **Which Java version is supported?** Aspose.Tasks hoạt động với Java 8 và các phiên bản mới hơn.  
- **Is it possible to calculate task cost from assignments?** Chắc chắn – cộng tổng các giá trị `BUDGET_COST` của các assignment.

## Quản Lý Ngân Sách trong Aspose.Tasks?
Aspose.Tasks lưu trữ thông tin ngân sách trong các trường riêng biệt (`BUDGET_WORK`, `BUDGET_COST`) cho task, resource và assignment. Các trường này cho phép bạn lên kế hoạch nỗ lực và chi phí tiền tệ dự kiến trước khi bất kỳ work nào được thực hiện, giúp dự báo chính xác và phân tích chênh lệch.

## Tại sao cần tính chi phí công việc?
- Theo dõi hiệu suất tài chính so với ước tính ban đầu.
- Tạo báo cáo dựa trên chi phí cho các bên liên quan.
- Xác định sớm các task vượt quá ngân sách.

## Yêu cầu trước
Trước khi chúng ta bắt đầu với mã, hãy chắc chắn rằng bạn có:

- Môi trường phát triển Java (JDK 8+).
- Thư viện Aspose.Tasks cho Java – tải xuống **[tại đây](https://releases.aspose.com/tasks/java/)**.
- Một tệp Microsoft Project mẫu (ví dụ, `BudgetWorkAndCost.mpp`) được đặt trong một thư mục đã biết.

## Nhập các gói
Trong dự án Java của bạn, bắt đầu bằng việc nhập các gói cần thiết. Điều này đảm bảo bạn có quyền truy cập vào chức năng của Aspose.Tasks. Bao gồm các dòng sau ở đầu tệp Java của bạn:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Bước 1: Đặt Thư mục Tài liệu
Bắt đầu bằng cách đặt đường dẫn tới thư mục tài liệu của bạn. Đây là nơi các tệp dự án của bạn được lưu trữ.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Bước 2: Tải Dự Án
Tải tệp dự án bằng thư viện Aspose.Tasks. Thay thế `"BudgetWorkAndCost.mpp"` bằng tên tệp dự án của bạn.
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```

## Bước 3: Lấy Ngân Sách Dự Án và Tài Nguyên
Lấy và hiển thị ngân sách ở mức dự án và mức tài nguyên. Bước này cho bạn thấy cách **tính chi phí công việc** bằng cách đọc các giá trị đã lưu.
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```

## Bước 4: Hiển Thị Ngân Sách Phân Công
Duyệt qua các assignment của summary task (hoặc bất kỳ task nào) và hiển thị thông tin ngân sách của mỗi assignment. Điều này cho phép bạn xem chi phí được phân bổ cho mỗi resource.
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```

## Các vấn đề thường gặp & Mẹo chuyên nghiệp
- **Null values:** Nếu một trường ngân sách trả về `null`, tệp dự án có thể không chứa dữ liệu đó. Hãy sử dụng kiểm tra `project.getRootTask().get(Tsk.BUDGET_WORK) != null` trước khi in.
- **Incorrect UID:** Đảm bảo UID resource bạn truy vấn (`getByUid(2)`) tồn tại; nếu không bạn sẽ gặp `NullPointerException`.
- **Currency formatting:** `BUDGET_COST` trả về một giá trị double thô. Định dạng nó bằng `NumberFormat.getCurrencyInstance()` để có đầu ra thân thiện với người dùng.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java với các framework Java khác không?**  
A: Có, Aspose.Tasks cho Java tương thích với nhiều framework Java, đảm bảo tính linh hoạt trong việc tích hợp.

**Q: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Tasks cho Java **[tại đây](https://releases.aspose.com/)**.

**Q: Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Tasks cho Java ở đâu?**  
A: Khám phá diễn đàn cộng đồng Aspose.Tasks **[tại đây](https://forum.aspose.com/c/tasks/15)** để được hỗ trợ và thảo luận.

**Q: Làm thế nào tôi có thể nhận giấy phép tạm thời cho Aspose.Tasks cho Java?**  
A: Nhận giấy phép tạm thời **[tại đây](https://purchase.aspose.com/temporary-license/)** để thử nghiệm và đánh giá.

**Q: Có tài nguyên bổ sung nào cho Aspose.Tasks cho Java không?**  
A: Tham khảo tài liệu **[tại đây](https://reference.aspose.com/tasks/java/)** để có thông tin chi tiết và các ví dụ.

---

**Cập nhật lần cuối:** 2026-02-28  
**Được kiểm tra với:** Aspose.Tasks for Java 24.10  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}