---
title: 在 Aspose.Tasks 中使用日曆
linktitle: 在 Aspose.Tasks 中使用日曆
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 輕鬆管理專案行事曆、計算工期、處理例外狀況。
type: docs
weight: 10
url: /zh-hant/net/calendar-scheduling/working-with-calendar/
---
## 介紹

Aspose.Tasks for .NET 提供了強大的行事曆處理功能，使開發人員能夠有效地管理專案進度和資源分配。在本教程中，我們將探索如何利用 Aspose.Tasks 與日曆交互，涵蓋基本操作，例如檢索日曆資訊、定義工作週、計算工作時間等。

## 先決條件

在我們開始之前，請確保您已設定以下先決條件：

- 對 C# 程式語言有基本了解。
- 安裝 Aspose.Tasks for .NET。如果沒有安裝，請從以下位置下載[這裡](https://releases.aspose.com/tasks/net/).
- 熟悉 Visual Studio 或任何其他首選的 .NET 開發環境。

## 導入命名空間

在開始編碼之前，請確保導入必要的命名空間：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

現在，讓我們以逐步指南的形式將每個範例分解為多個步驟：

## 第 1 步：檢索日曆信息

若要從專案中擷取日曆信息，請執行下列步驟：

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    //檢索日曆資訊
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

解釋：
- 載入專案文件。
- 迭代項目中的每個日曆。
- 列印每個日曆的 UID 和名稱。

## 第 2 步：閱讀工作週資訊

要從日曆中讀取工作週信息，請按照下列步驟操作：

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

解釋：
- 載入專案文件。
- 透過UID取得日曆。
- 迭代日曆中的每個工作週。
- 列印每個工作週的名稱、開始日期和結束日期。
- 遍歷每週的工作日和工作時間。

## 第 3 步：讀取日曆屬性

若要讀取專案日曆的屬性，請執行下列步驟：

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

解釋：
- 載入專案文件。
- 迭代項目中的每個日曆。
- 列印 UID、名稱以及是否為基準日曆。
- 列印每天類型的工作時間。

## 第四步：計算工作時間

要計算任務的工時，請依照下列步驟操作：

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

解釋：
- 載入專案文件。
- 取得任務詳細信息，例如日曆、開始日期和結束日期。
- 透過迭代每一天並檢查當天是否為工作日來計算工作時間。
- 以分鐘為單位總結總持續時間。

## 步驟 5：定義日曆的工作日

若要定義日曆的工作日，請依照下列步驟操作：

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

解釋：
- 建立一個新專案和日曆。
- 新增預設工作日（週一至週四）和週五的自訂工作時間。
- 將週六和週日設定為非工作日。

## 步驟 6：將更新的日曆資料寫入 MPP

若要將更新的日曆資料寫入 MPP 文件，請依照下列步驟操作：

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
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/.」）；
    }
}
```

解釋：
- 載入專案文件並檢索標準日曆。
- 修改日曆數據，例如例外情況和工作時間。
- 使用修改後的日曆資料儲存更新的項目。

## 第 7 步：計算拆分任務完成日期

若要計算拆分任務的完成日期，請執行下列步驟：

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

解釋：
- 載入專案檔案並檢索拆分任務。
- 取得項目日曆。
- 根據自訂持續時間計算完成日期。

## 步驟 8：檢索日曆異常

要檢索有關日曆例外的信息，請執行以下步驟：

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

解釋：
- 載入專案文件。
- 迭代每個日曆及其例外。
- 列印每個異常的開始和結束日期。

## 第 9 步：取得基礎資源日曆

若要使用資源日曆的基準日曆，請執行下列步驟：

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

解釋：
- 載入專案文件。
- 新增資源及其日曆。
- 列印所有資源的基準日曆名稱。

## 第10步：刪除日曆

若要從項目中刪除行事曆，請依照下列步驟操作：

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

解釋：
- 載入專案文件。
- 按名稱取得日曆。
- 刪除日曆。

## 第 11 步：透過開始和工作確定完成日期

若要根據開始日期和工時計算完成日期，請執行下列步驟：

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

解釋：
- 載入專案文件。
- 取得標準日曆。
- 定義開始日期和工作持續時間。
- 根據開始日期和工時計算完成日期。

## 第 12 步：開始下一個工作日

若要使用日曆開始下一個工作日，請依照下列步驟操作：

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

解釋：
- 載入專案文件。
- 透過UID取得日曆。
- 取得下一個工作日的開始時間。

## 第 13 步：取得前一個工作日結束時間

若要使用日曆取得前一個工作日的結束時間，請依照下列步驟操作：

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

解釋：
- 載入專案文件。
- 透過UID取得日曆。
- 取得前一個工作日的結束時間。

## 第 14 步：根據完成時間和持續時間取得開始日期

若要按結束日期和持續時間取得開始日期，請依照下列步驟操作：

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

解釋：
- 載入專案文件。
- 透過UID取得日曆。
- 根據結束日期和持續時間計算開始日期。

## 第 15 步：取得工作時間

若要取得特定日期的工作時間，請執行下列步驟：

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

解釋：
- 載入專案文件。
- 透過UID取得日曆。
- 取得指定日期的工作時間。

## 第 16 步：取得工作時間

若要取得特定日期的工作時間，請依照下列步驟操作：

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

解釋：
- 載入專案文件。
- 透過UID取得日曆。
- 取得指定日期的工作時間。

## 結論

在 Aspose.Tasks for .NET 中使用行事曆對於有效管理專案進度至關重要。透過提供的範例和逐步指南，您可以輕鬆操作日曆資料、計算任務持續時間並有效處理異常。透過將這些功能整合到您的應用程式中，您可以簡化專案管理流程並確保準確的調度。

## 常見問題解答

### Q1：我需要許可證才能使用 Aspose.Tasks for .NET 嗎？

 A1：是的，您需要有效的許可證才能在應用程式中使用 Aspose.Tasks for .NET。您可以購買完整許可證或從以下位置取得 30 天的臨時許可證：[這裡](https://purchase.aspose.com/temporary-license/).

### 問題 2：我可以透過程式修改日曆例外嗎？

A2：是的，您可以使用 Aspose.Tasks for .NET API 以程式設計方式新增、更新或刪除行事曆例外。

### 問題 3：如何計算具有自訂持續時間的任務完成日期？

 A3：Aspose.Tasks for .NET 提供了類似的方法`GetTaskFinishDateFromDuration()`根據自訂持續時間計算任務完成日期。

### Q4：是否可以建立自訂日曆，例如夜班日曆？

A4：是的，您可以使用 Aspose.Tasks for .NET API 建立自訂行事曆，例如夜間行事曆。

### Q5：我可以從專案文件中檢索有關日曆例外的資訊嗎？

A5：是的，您可以使用 Aspose.Tasks for .NET 輕鬆地從專案文件中檢索日曆異常的資訊。