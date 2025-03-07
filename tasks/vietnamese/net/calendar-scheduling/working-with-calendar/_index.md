---
title: Làm việc với Lịch trong Aspose.Tasks
linktitle: Làm việc với Lịch trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Quản lý lịch dự án, tính toán thời lượng, xử lý các trường hợp ngoại lệ một cách dễ dàng bằng Aspose.Tasks for .NET.
weight: 10
url: /vi/net/calendar-scheduling/working-with-calendar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Làm việc với Lịch trong Aspose.Tasks

## Giới thiệu

Aspose.Tasks for .NET cung cấp các tính năng mạnh mẽ để làm việc với lịch, cho phép các nhà phát triển quản lý hiệu quả lịch trình dự án và phân bổ tài nguyên. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng Aspose.Tasks để tương tác với lịch, bao gồm các hoạt động thiết yếu như truy xuất thông tin lịch, xác định tuần làm việc, tính giờ làm việc, v.v.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:

- Hiểu biết cơ bản về ngôn ngữ lập trình C#.
-  Cài đặt Aspose.Tasks cho .NET. Nếu chưa được cài đặt, hãy tải xuống từ[đây](https://releases.aspose.com/tasks/net/).
- Làm quen với Visual Studio hoặc bất kỳ môi trường phát triển .NET ưa thích nào khác.

## Nhập không gian tên

Trước khi bắt đầu viết mã, hãy đảm bảo nhập các không gian tên cần thiết:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Bây giờ, hãy chia mỗi ví dụ thành nhiều bước theo định dạng hướng dẫn từng bước:

## Bước 1: Truy xuất thông tin lịch

Để truy xuất thông tin lịch từ một dự án, hãy làm theo các bước sau:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Truy xuất thông tin lịch
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Giải trình:
- Tải tập tin dự án.
- Lặp lại qua từng lịch trong dự án.
- In UID và tên từng lịch.

## Bước 2: Đọc thông tin về tuần làm việc

Để đọc thông tin tuần làm việc từ lịch, hãy làm theo các bước sau:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Giải trình:
- Tải tập tin dự án.
- Lấy lịch bằng UID.
- Lặp lại qua từng tuần làm việc trong lịch.
- In tên, ngày bắt đầu và ngày kết thúc của mỗi tuần làm việc.
- Duyệt qua các ngày làm việc và thời gian làm việc trong mỗi tuần.

## Bước 3: Đọc thuộc tính lịch

Để đọc các thuộc tính của lịch dự án, hãy làm theo các bước sau:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Giải trình:
- Tải tập tin dự án.
- Lặp lại qua từng lịch trong dự án.
- In UID, tên và xem đó có phải là lịch cơ sở hay không.
- In giờ làm việc cho từng loại ngày.

## Bước 4: Tính giờ làm việc

Để tính giờ làm việc cho một nhiệm vụ, hãy làm theo các bước sau:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Giải trình:
- Tải tập tin dự án.
- Nhận thông tin chi tiết về nhiệm vụ như lịch, ngày bắt đầu và ngày kết thúc.
- Tính số giờ làm việc bằng cách lặp lại từng ngày và kiểm tra xem đó có phải là ngày làm việc hay không.
- Tổng hợp thời lượng tính bằng phút.

## Bước 5: Xác định ngày trong tuần cho Lịch

Để xác định các ngày trong tuần cho lịch, hãy làm theo các bước sau:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Giải trình:
- Tạo một dự án và lịch mới.
- Thêm ngày làm việc mặc định (Thứ Hai đến Thứ Năm) và thời gian làm việc tùy chỉnh cho Thứ Sáu.
- Đặt thứ bảy và chủ nhật là những ngày không làm việc.

## Bước 6: Ghi dữ liệu lịch cập nhật vào MPP

Để ghi dữ liệu lịch cập nhật vào tệp MPP, hãy làm theo các bước sau:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://mua.aspose.com/temporary-license/).");
    }
}
```

Giải trình:
- Tải tệp dự án và truy xuất lịch tiêu chuẩn.
- Sửa đổi dữ liệu lịch như ngoại lệ và thời gian làm việc.
- Lưu dự án đã cập nhật với dữ liệu lịch đã sửa đổi.

## Bước 7: Tính ngày kết thúc nhiệm vụ phân chia

Để tính ngày kết thúc của một nhiệm vụ được phân chia, hãy làm theo các bước sau:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Giải trình:
- Tải tệp dự án và truy xuất tác vụ đã phân chia.
- Nhận lịch dự án.
- Tính ngày kết thúc dựa trên khoảng thời gian tùy chỉnh.

## Bước 8: Truy xuất ngoại lệ lịch

Để truy xuất thông tin về các ngoại lệ của lịch, hãy làm theo các bước sau:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Giải trình:
- Tải tập tin dự án.
- Lặp lại từng lịch và các ngoại lệ của nó.
- In ngày bắt đầu và ngày kết thúc của từng ngoại lệ.

## Bước 9: Nhận lịch tài nguyên cơ sở

Để làm việc với lịch cơ sở của lịch của tài nguyên, hãy làm theo các bước sau:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Giải trình:
- Tải tập tin dự án.
- Thêm tài nguyên và lịch của nó.
- In tên lịch cơ sở cho tất cả các tài nguyên.

## Bước 10: Xóa lịch

Để xóa lịch khỏi dự án, hãy làm theo các bước sau:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Giải trình:
- Tải tập tin dự án.
- Lấy lịch theo tên.
- Xóa lịch.

## Bước 11: Nhận ngày kết thúc bằng cách bắt đầu và làm việc

Để tính ngày kết thúc theo ngày bắt đầu và công việc, hãy làm theo các bước sau:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Giải trình:
- Tải tập tin dự án.
- Nhận lịch chuẩn.
- Xác định ngày bắt đầu và thời gian làm việc.
- Tính ngày kết thúc dựa trên ngày bắt đầu và công việc.

## Bước 12: Bắt đầu ngày làm việc tiếp theo

Để bắt đầu ngày làm việc tiếp theo bằng cách sử dụng lịch, hãy làm theo các bước sau:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Giải trình:
- Tải tập tin dự án.
- Lấy lịch bằng UID.
- Nhận thời gian bắt đầu ngày làm việc tiếp theo.

## Bước 13: Nhận kết thúc ngày làm việc trước đó

Để kết thúc ngày làm việc trước đó bằng cách sử dụng lịch, hãy làm theo các bước sau:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Giải trình:
- Tải tập tin dự án.
- Lấy lịch bằng UID.
- Lấy thời gian kết thúc ngày làm việc trước đó.

## Bước 14: Nhận ngày bắt đầu từ kết thúc và thời lượng

Để có được ngày bắt đầu theo ngày kết thúc và thời lượng, hãy làm theo các bước sau:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Giải trình:
- Tải tập tin dự án.
- Lấy lịch bằng UID.
- Tính ngày bắt đầu từ ngày kết thúc và thời gian.

## Bước 15: Nhận giờ làm việc

Để biết giờ làm việc cho một ngày cụ thể, hãy làm theo các bước sau:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Giải trình:
- Tải tập tin dự án.
- Lấy lịch bằng UID.
- Nhận giờ làm việc cho ngày được chỉ định.

## Bước 16: Nhận thời gian làm việc

Để biết thời gian làm việc cho một ngày cụ thể, hãy làm theo các bước sau:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Giải trình:
- Tải tập tin dự án.
- Lấy lịch bằng UID.
- Nhận thời gian làm việc cho ngày được chỉ định.

## Phần kết luận

Làm việc với lịch trong Aspose.Tasks cho .NET là rất quan trọng để quản lý lịch trình dự án một cách hiệu quả. Với các ví dụ được cung cấp và hướng dẫn từng bước, bạn có thể dễ dàng thao tác với dữ liệu lịch, tính toán thời gian thực hiện nhiệm vụ và xử lý các trường hợp ngoại lệ một cách hiệu quả. Bằng cách tích hợp các chức năng này vào ứng dụng của mình, bạn có thể hợp lý hóa quy trình quản lý dự án và đảm bảo lập kế hoạch chính xác.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có cần giấy phép để sử dụng Aspose.Tasks cho .NET không?

 Câu trả lời 1: Có, bạn cần có giấy phép hợp lệ để sử dụng Aspose.Tasks cho .NET trong các ứng dụng của mình. Bạn có thể mua giấy phép đầy đủ hoặc lấy giấy phép tạm thời 30 ngày từ[đây](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 2: Tôi có thể sửa đổi các ngoại lệ của lịch theo chương trình không?

Câu trả lời 2: Có, bạn có thể thêm, cập nhật hoặc xóa các ngoại lệ lịch theo chương trình bằng cách sử dụng Aspose.Tasks cho API .NET.

### Câu hỏi 3: Làm cách nào tôi có thể tính ngày hoàn thành nhiệm vụ với thời hạn tùy chỉnh?

 Câu trả lời 3: Aspose.Tasks cho .NET cung cấp các phương thức như`GetTaskFinishDateFromDuration()` để tính toán ngày hoàn thành nhiệm vụ dựa trên khoảng thời gian tùy chỉnh.

### Q4: Có thể tạo lịch tùy chỉnh, chẳng hạn như lịch ca đêm không?

Câu trả lời 4: Có, bạn có thể tạo lịch tùy chỉnh như lịch ca đêm bằng cách sử dụng Aspose.Tasks cho API .NET.

### Câu hỏi 5: Tôi có thể truy xuất thông tin về các ngoại lệ của lịch từ các tệp dự án không?

Câu trả lời 5: Có, bạn có thể dễ dàng truy xuất thông tin về các ngoại lệ của lịch từ các tệp dự án bằng Aspose.Tasks cho .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
