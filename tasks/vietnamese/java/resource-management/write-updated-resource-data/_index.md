---
date: 2026-01-15
description: Tìm hiểu cách thêm nguồn lực vào dự án, cập nhật dữ liệu nguồn lực và
  lưu dự án dưới dạng MPP bằng Aspose.Tasks cho Java.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Thêm tài nguyên vào dự án bằng Aspose.Tasks cho Java
url: /vi/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm tài nguyên vào dự án bằng Aspose.Tasks cho Java

## Giới thiệu
Trong tutorial thực hành này, bạn sẽ khám phá **cách thêm tài nguyên vào dự án** một cách lập trình bằng API Aspose.Tasks cho Java. Chúng tôi sẽ hướng dẫn cách tải một tệp XML MS Project hiện có, chèn một tài nguyên mới, cập nhật các thuộc tính của nó, và cuối cùng **lưu dự án dưới dạng MPP**. Khi kết thúc, bạn sẽ có một mẫu rõ ràng, có thể tái sử dụng để tích hợp vào bất kỳ công cụ báo cáo hoặc tự động hoá nào dựa trên Java.

## Câu trả lời nhanh
- **“add resource to project” có nghĩa là gì?** Nó tạo một mục tài nguyên mới (người, thiết bị, vật liệu) trong một tệp Microsoft Project.  
- **Thư viện nào xử lý việc này?** Aspose.Tasks cho Java – không cần cài đặt Microsoft Project.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể chuyển đổi XML sang MPP không?** Có – tải tệp XML và **lưu dự án dưới dạng MPP** bằng cách sử dụng `project.save(...)`.  
- **Yêu cầu phiên bản Java nào?** Java 6 trở lên (đề nghị Java 8+).

## “add resource to project” là gì?
Thêm một tài nguyên vào dự án có nghĩa là chèn một hàng mới vào bảng Resources của tệp MS Project. Hàng này lưu trữ các chi tiết như tên, mức phí, nhóm và các trường tùy chỉnh mà các nhiệm vụ có thể tham chiếu sau này.

## Tại sao nên sử dụng Aspose.Tasks cho Java?
- **Không phụ thuộc vào Microsoft Project** – hoạt động trên bất kỳ hệ điều hành hoặc máy chủ CI nào.  
- **Độ chính xác đầy đủ** – giữ nguyên tất cả các tính năng gốc của Project khi chuyển đổi giữa các định dạng.  
- **API phong phú** – cho phép bạn đọc, ghi và thao tác các nhiệm vụ, tài nguyên, lịch và nhiều hơn nữa.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. Java Development Kit (JDK) 8 hoặc mới hơn đã được cài đặt.  
2. Thư viện Aspose.Tasks cho Java – tải xuống từ [here](https://releases.aspose.com/tasks/java/).  
3. Kiến thức cơ bản về cú pháp Java và cấu hình dự án Maven/Gradle.

## Nhập gói
Thêm các lớp Aspose.Tasks cần thiết vào tệp nguồn Java của bạn:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Bước 1: Thiết lập thư mục dữ liệu của bạn
Xác định vị trí lưu trữ các tệp XML nguồn và các tệp MPP kết quả:

```java
String dataDir = "Your Data Directory";
```

## Bước 2: Chỉ định tệp đầu vào và đầu ra
Chỉ đến tệp XML bạn muốn chuyển đổi (**convert XML to MPP**) và tệp MPP đích sẽ chứa tài nguyên mới:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Bước 3: Tải dự án
Tạo một đối tượng `Project` từ nguồn XML:

```java
Project project = new Project(file);
```

## Bước 4: Thêm tài nguyên và thiết lập thuộc tính
Đây là nơi chúng ta **add resource to project** và cấu hình mức phí và nhóm của nó:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Mẹo chuyên nghiệp:* Bạn có thể lặp lại lời gọi `add` trong một vòng lặp để **cập nhật nhiều tài nguyên** trong một lần chạy.

## Bước 5: Lưu dự án
Cuối cùng, **save project as MPP** để lưu các thay đổi:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Kết luận
Bạn vừa học được **cách add resource to project**, cập nhật các thuộc tính của nó, và **save project as MPP** bằng Aspose.Tasks cho Java. Cách tiếp cận này lý tưởng cho các pipeline báo cáo tự động, nhập khẩu tài nguyên hàng loạt, hoặc bất kỳ kịch bản nào cần thao tác tệp MS Project mà không cần ứng dụng desktop.

## Câu hỏi thường gặp

**Q1: Tôi có thể cập nhật nhiều tài nguyên trong cùng một dự án bằng Aspose.Tasks cho Java không?**  
A: Có, lặp qua `project.getResources()` hoặc gọi `add` nhiều lần, thiết lập các trường của mỗi tài nguyên theo nhu cầu.

**Q2: Aspose.Tasks có hỗ trợ các định dạng tệp khác ngoài MS Project không?**  
A: Chắc chắn – XML, MPP, MPX, Primavera và nhiều định dạng khác đều được hỗ trợ.

**Q3: Aspose.Tasks có tương thích với các phiên bản Java khác nhau không?**  
A: Thư viện hoạt động với Java 6 trở lên; Java 8+ được khuyến nghị mạnh mẽ để đạt hiệu suất tốt nhất.

**Q4: Tôi có thể thực hiện các thao tác khác trên tệp MS Project bằng Aspose.Tasks không?**  
A: Có, bạn có thể đọc/ghi các nhiệm vụ, lịch, phân công, trường tùy chỉnh và thậm chí tạo báo cáo.

**Q5: Tôi có thể tìm trợ giúp hoặc hỗ trợ bổ sung cho Aspose.Tasks ở đâu?**  
A: Truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để nhận hỗ trợ từ cộng đồng và hỗ trợ chính thức.

---

**Cập nhật lần cuối:** 2026-01-15  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}