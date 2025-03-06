---
title: Thang tỷ lệ đọc và ghi cho các bài tập tài nguyên trong Aspose.Tasks
linktitle: Thang tỷ lệ đọc và ghi cho các bài tập tài nguyên trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách quản lý thang tỷ lệ phân bổ tài nguyên một cách hiệu quả trong Aspose.Tasks cho Java với hướng dẫn toàn diện này.
weight: 20
url: /vi/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thang tỷ lệ đọc và ghi cho các bài tập tài nguyên trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc quản lý thang tỷ lệ phân công tài nguyên bằng Aspose.Tasks cho Java, một thư viện mạnh mẽ để làm việc với các tệp Microsoft Project theo chương trình. Bằng cách làm theo các bước này, bạn sẽ có thể thao tác hiệu quả các cài đặt thang tỷ lệ cho việc gán tài nguyên trong các ứng dụng Java của mình.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Môi trường phát triển Java: Đảm bảo bạn đã cài đặt Bộ công cụ phát triển Java (JDK) trên hệ thống của mình.
2.  Aspose.Tasks for Java Library: Tải xuống và cài đặt thư viện Aspose.Tasks for Java từ[đây](https://releases.aspose.com/tasks/java/).

## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết để làm việc với các chức năng của Aspose.Tasks. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Bước 1: Thiết lập dự án của bạn
Bắt đầu bằng cách thiết lập dự án Java của bạn và đưa thư viện Aspose.Tasks vào phần phụ thuộc của bạn.
## Bước 2: Tải tệp dự án
Tải tệp Dự án mà bạn muốn làm việc vào ứng dụng Java của mình.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Bước 3: Thêm tác vụ
Thêm một nhiệm vụ mới vào dự án của bạn.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Bước 4: Xác định tài nguyên
Xác định các nguồn lực vật chất và phi vật chất và chỉ định loại của chúng.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Bước 5: Gán tài nguyên cho nhiệm vụ
Gán các tài nguyên được xác định trước đó cho nhiệm vụ cùng với các loại thang tỷ lệ của chúng.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Bước 6: Lưu dự án
Lưu dự án với các bài tập tài nguyên đã sửa đổi.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Bước 7: Truy xuất các bài tập tài nguyên
Tải lại dự án đã lưu và truy xuất các bài tập tài nguyên để xác minh cài đặt thang tỷ lệ.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Phần kết luận
Quản lý thang tỷ lệ phân bổ tài nguyên trong Aspose.Tasks cho Java là rất quan trọng để quản lý dự án hiệu quả. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể thao tác liền mạch các cài đặt thang tỷ lệ cho việc gán tài nguyên trong các ứng dụng Java của mình.
## Câu hỏi thường gặp
### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks cho Java với bất kỳ IDE Java nào không?
Trả lời: Có, Aspose.Tasks cho Java tương thích với tất cả các IDE Java chính, bao gồm IntelliJ IDEA, Eclipse và NetBeans.
### Câu hỏi 2: Aspose.Tasks có hỗ trợ các định dạng tệp khác ngoài MPP không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp khác nhau, bao gồm MPP, XML và HTML.
### Câu hỏi 3: Aspose.Tasks có phù hợp để quản lý dự án cấp doanh nghiệp không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks cung cấp các tính năng toàn diện để quản lý dự án ở mọi quy mô, khiến nó phù hợp với việc quản lý dự án cấp doanh nghiệp.
### Câu hỏi 4: Tôi có thể tùy chỉnh việc phân bổ nguồn lực hơn nữa ngoài phạm vi tỷ lệ không?
Trả lời: Có, Aspose.Tasks cung cấp các khả năng mở rộng để tùy chỉnh các nhiệm vụ tài nguyên, bao gồm điều chỉnh chi phí, công việc và thời lượng.
### Câu hỏi 5: Có diễn đàn cộng đồng nào hỗ trợ Aspose.Tasks không?
 Trả lời: Có, bạn có thể tìm thấy sự hỗ trợ và tương tác với những người dùng khác trên diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
