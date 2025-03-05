---
title: Aspose.Tasks에서 달력 작업
linktitle: Aspose.Tasks에서 달력 작업
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 프로젝트 달력을 관리하고, 기간을 계산하고, 예외를 쉽게 처리하세요.
type: docs
weight: 10
url: /ko/net/calendar-scheduling/working-with-calendar/
---
## 소개

Aspose.Tasks for .NET은 캘린더 작업을 위한 강력한 기능을 제공하여 개발자가 프로젝트 일정과 리소스 할당을 효율적으로 관리할 수 있도록 해줍니다. 이 튜토리얼에서는 Aspose.Tasks를 활용하여 달력과 상호 작용하는 방법을 살펴보고 달력 정보 검색, 근무 주 정의, 근무 시간 계산 등과 같은 필수 작업을 다룹니다.

## 전제조건

시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 이해.
-  .NET용 Aspose.Tasks 설치. 설치되어 있지 않은 경우 다음에서 다운로드하세요.[여기](https://releases.aspose.com/tasks/net/).
- Visual Studio 또는 기타 선호하는 .NET 개발 환경에 대한 지식.

## 네임스페이스 가져오기

코딩을 시작하기 전에 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

이제 단계별 가이드 형식으로 각 예를 여러 단계로 나누어 보겠습니다.

## 1단계: 캘린더 정보 검색

프로젝트에서 달력 정보를 검색하려면 다음 단계를 따르세요.

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // 캘린더 정보 검색
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

설명:
- 프로젝트 파일을 로드합니다.
- 프로젝트의 각 달력을 반복합니다.
- 각 달력의 UID와 이름을 인쇄합니다.

## 2단계: 근무 주 정보 읽기

달력에서 근무 주 정보를 읽으려면 다음 단계를 따르세요.

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

설명:
- 프로젝트 파일을 로드합니다.
- UID로 달력을 가져옵니다.
- 달력의 각 작업 주를 반복합니다.
- 각 근무 주의 이름, 시작 날짜, 종료 날짜를 인쇄체로 입력하세요.
- 매주 근무일과 근무 시간을 순회합니다.

## 3단계: 달력 속성 읽기

프로젝트 달력의 속성을 읽으려면 다음 단계를 따르세요.

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

설명:
- 프로젝트 파일을 로드합니다.
- 프로젝트의 각 달력을 반복합니다.
- UID, 이름, 기본 달력인지 여부를 인쇄합니다.
- 각 요일별 근무 시간을 인쇄하세요.

## 4단계: 근무 시간 계산

작업의 작업 시간을 계산하려면 다음 단계를 따르세요.

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

설명:
- 프로젝트 파일을 로드합니다.
- 달력, 시작 날짜, 종료 날짜 등 작업 세부정보를 확인하세요.
- 매일 반복하고 근무일인지 확인하여 근무 시간을 계산합니다.
- 총 소요 시간을 분 단위로 요약합니다.

## 5단계: 달력의 평일 정의

달력의 평일을 정의하려면 다음 단계를 따르세요.

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

설명:
- 새 프로젝트와 달력을 만듭니다.
- 기본 근무일(월요일~목요일)과 금요일의 맞춤 근무 시간을 추가하세요.
- 토요일과 일요일을 휴무일로 설정하세요.

## 6단계: 업데이트된 달력 데이터를 MPP에 쓰기

업데이트된 달력 데이터를 MPP 파일에 쓰려면 다음 단계를 따르세요.

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
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/).");
    }
}
```

설명:
- 프로젝트 파일을 로드하고 표준 달력을 검색합니다.
- 예외사항, 근무시간 등 달력 데이터를 수정합니다.
- 수정된 캘린더 데이터로 업데이트된 프로젝트를 저장합니다.

## 7단계: 분할 작업 완료 날짜 계산

분할 작업의 완료 날짜를 계산하려면 다음 단계를 따르세요.

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

설명:
- 프로젝트 파일을 로드하고 분할 작업을 검색합니다.
- 프로젝트 달력을 받으세요.
- 사용자 정의 기간을 기준으로 완료 날짜를 계산합니다.

## 8단계: 달력 예외 검색

캘린더 예외에 대한 정보를 검색하려면 다음 단계를 따르세요.

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

설명:
- 프로젝트 파일을 로드합니다.
- 각 달력과 해당 예외를 반복합니다.
- 각 예외의 시작 및 종료 날짜를 인쇄합니다.

## 9단계: 기본 자원 달력 가져오기

자원 달력의 기본 달력을 사용하려면 다음 단계를 따르세요.

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

설명:
- 프로젝트 파일을 로드합니다.
- 리소스와 해당 달력을 추가합니다.
- 모든 자원의 기본 달력 이름을 인쇄합니다.

## 10단계: 캘린더 삭제

프로젝트에서 달력을 삭제하려면 다음 단계를 따르세요.

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

설명:
- 프로젝트 파일을 로드합니다.
- 이름으로 달력을 가져옵니다.
- 달력을 삭제하세요.

## 11단계: 시작 및 작업별로 완료 날짜 가져오기

시작 날짜 및 작업별로 완료 날짜를 계산하려면 다음 단계를 따르세요.

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

설명:
- 프로젝트 파일을 로드합니다.
- 표준 달력을 받으세요.
- 시작 날짜와 작업 기간을 정의합니다.
- 시작 날짜와 작업을 기준으로 완료 날짜를 계산합니다.

## 12단계: 다음 근무일 시작

달력을 사용하여 다음 근무일을 시작하려면 다음 단계를 따르세요.

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

설명:
- 프로젝트 파일을 로드합니다.
- UID로 달력을 가져옵니다.
- 다음 근무일 시작 시간을 가져옵니다.

## 13단계: 이전 근무일 종료 가져오기

달력을 사용하여 이전 근무일을 종료하려면 다음 단계를 따르세요.

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

설명:
- 프로젝트 파일을 로드합니다.
- UID로 달력을 가져옵니다.
- 이전 근무일 종료 시간을 가져옵니다.

## 14단계: 완료 및 기간에서 시작 날짜 가져오기

완료 날짜 및 기간별로 시작 날짜를 얻으려면 다음 단계를 따르십시오.

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

설명:
- 프로젝트 파일을 로드합니다.
- UID로 달력을 가져옵니다.
- 종료일과 기간으로부터 시작일을 계산합니다.

## 15단계: 근무 시간 가져오기

특정 날짜의 근무 시간을 확인하려면 다음 단계를 따르세요.

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

설명:
- 프로젝트 파일을 로드합니다.
- UID로 달력을 가져옵니다.
- 지정된 날짜의 근무 시간을 가져옵니다.

## 16단계: 근무 시간 가져오기

특정 날짜의 근무 시간을 확인하려면 다음 단계를 따르세요.

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

설명:
- 프로젝트 파일을 로드합니다.
- UID로 달력을 가져옵니다.
- 지정된 날짜의 근무 시간을 가져옵니다.

## 결론

Aspose.Tasks for .NET에서 달력을 사용하는 것은 프로젝트 일정을 효과적으로 관리하는 데 중요합니다. 제공된 예제와 단계별 가이드를 통해 캘린더 데이터를 쉽게 조작하고, 작업 기간을 계산하고, 예외를 효율적으로 처리할 수 있습니다. 이러한 기능을 애플리케이션에 통합하면 프로젝트 관리 프로세스를 간소화하고 정확한 일정을 계획할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks for .NET을 사용하려면 라이선스가 필요합니까?

 A1: 예, 애플리케이션에서 Aspose.Tasks for .NET을 활용하려면 유효한 라이선스가 필요합니다. 정식 라이센스를 구입하거나 다음 사이트에서 30일 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

### 질문 2: 프로그래밍 방식으로 일정 예외를 수정할 수 있습니까?

A2: 예, .NET API용 Aspose.Tasks를 사용하여 프로그래밍 방식으로 달력 예외를 추가, 업데이트 또는 삭제할 수 있습니다.

### Q3: 사용자 지정 기간을 사용하여 작업 완료 날짜를 어떻게 계산할 수 있나요?

 A3: .NET용 Aspose.Tasks는 다음과 같은 메서드를 제공합니다.`GetTaskFinishDateFromDuration()` 사용자 정의 기간을 기준으로 작업 완료 날짜를 계산합니다.

### Q4: 야간 근무 달력과 같은 맞춤형 달력을 만들 수 있습니까?

A4: 예, .NET API용 Aspose.Tasks를 사용하여 야간 근무 달력과 같은 사용자 정의 달력을 만들 수 있습니다.

### Q5: 프로젝트 파일에서 달력 예외에 대한 정보를 검색할 수 있습니까?

A5: 예, Aspose.Tasks for .NET을 사용하면 프로젝트 파일에서 달력 예외에 대한 정보를 쉽게 검색할 수 있습니다.