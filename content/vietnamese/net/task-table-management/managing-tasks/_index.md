---
title: Quản lý tác vụ trong Aspose.Tasks
linktitle: Quản lý tác vụ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá hướng dẫn toàn diện về cách quản lý tác vụ với Aspose.Tasks cho .NET. Tìm hiểu cách thêm, hiển thị các phần được chia nhỏ, di chuyển, lấy/đặt thuộc tính, v.v.
type: docs
weight: 15
url: /vi/net/task-table-management/managing-tasks/
---
## Giới thiệu
Nếu bạn là nhà phát triển .NET đang tìm cách quản lý hiệu quả các tác vụ trong dự án của mình thì Aspose.Tasks for .NET sẽ cung cấp một giải pháp mạnh mẽ. Hướng dẫn này sẽ hướng dẫn bạn qua các khía cạnh khác nhau của việc quản lý tác vụ bằng Aspose.Tasks, cung cấp hướng dẫn từng bước và ví dụ về mã. Cho dù bạn đang thêm nhiệm vụ, hiển thị các phần được chia nhỏ, di chuyển nhiệm vụ trong cùng một phần gốc, nhận/đặt thuộc tính nhiệm vụ, lặp lại các nhiệm vụ nhiệm vụ, đọc đường cơ sở của nhiệm vụ hoặc xóa nhiệm vụ, hướng dẫn này sẽ giúp bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Tasks for .NET Library: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Tasks for .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/net/).
2. Thư mục tài liệu: Thiết lập một thư mục nơi tài liệu dự án của bạn sẽ được lưu trữ.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy bao gồm các vùng tên cần thiết để hoạt động với Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Thêm nhiệm vụ vào dự án
```csharp
// Tạo một dự án mới
var project = new Project();
// Thêm nhiệm vụ
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Lưu dự án
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Hiển thị các phần chia nhỏ của nhiệm vụ
```csharp
// Tải một dự án với các nhiệm vụ được phân chia
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//Truy cập một nhiệm vụ
var task = project.RootTask.Children.GetById(4);
// Hiển thị các phần được chia
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Di chuyển một nhiệm vụ dưới cùng một phụ huynh
```csharp
try
{
    // Tải một dự án
    var project = new Project(DataDir + "MoveTask.mpp");
    // Di chuyển tác vụ có id 5 trước tác vụ có id 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Lưu dự án đã sửa đổi
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Lấy/Đặt thuộc tính tác vụ
```csharp
// Tạo một dự án mới
var project = new Project();
// Thêm nhiệm vụ và đặt thuộc tính
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Thu thập và hiển thị thuộc tính nhiệm vụ
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Lặp lại các nhiệm vụ của nhiệm vụ
```csharp
// Tải một dự án với các bài tập
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Thu thập và hiển thị các nhiệm vụ được giao
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Đọc thông tin cơ bản của nhiệm vụ
```csharp
// Tạo một dự án mới
var project = new Project();
// Thêm nhiệm vụ và đặt đường cơ sở
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Hiển thị thời lượng cơ bản của nhiệm vụ
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Xóa một tác vụ
```csharp
// Tạo một dự án mới
var project = new Project();
// Thêm nhiệm vụ
var task = project.RootTask.Children.Add("Task");
// Hiển thị số lượng tác vụ trước và sau khi xóa
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Xóa nhiệm vụ
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Phần kết luận
Quản lý tác vụ trong Aspose.Tasks cho .NET là một quy trình liền mạch với các ví dụ được cung cấp. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay chỉ mới bắt đầu, việc kết hợp các kỹ thuật này sẽ nâng cao khả năng quản lý dự án của bạn.
## Các câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có tương thích với tất cả các khung .NET không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều khung .NET khác nhau, đảm bảo khả năng tương thích với môi trường phát triển của bạn.
### Câu hỏi: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Tasks?
 Đáp: Bạn có thể xin giấy phép tạm thời 30 ngày từ[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Có bất kỳ hạn chế nào khi làm việc với các tác vụ được phân chia trong Aspose.Tasks không?
 Trả lời: Phân chia nhiệm vụ là một tính năng mạnh mẽ và có thể tìm thấy tài liệu chi tiết[đây](https://reference.aspose.com/tasks/net/).
### Câu hỏi: Tôi có thể tùy chỉnh các thuộc tính nhiệm vụ ngoài những gì được hiển thị trong ví dụ không?
Đ: Chắc chắn rồi! Aspose.Tasks cung cấp các tùy chọn tùy chỉnh mở rộng cho các thuộc tính nhiệm vụ. Kiểm tra tài liệu để biết thêm chi tiết.
### Câu hỏi: Làm cách nào để tôi nhận được hỗ trợ cho Aspose.Tasks?
 Đáp: Hãy ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được cộng đồng hỗ trợ và thảo luận.