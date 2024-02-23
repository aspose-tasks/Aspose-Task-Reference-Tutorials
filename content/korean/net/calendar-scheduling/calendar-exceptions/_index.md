---
title: Aspose.Tasks에서 달력 예외 처리
linktitle: Aspose.Tasks에서 달력 예외 처리
second_title: Aspose.태스크 .NET API
description: 단계별 튜토리얼과 예제를 통해 Aspose.Tasks for .NET에서 달력 예외를 관리하는 방법을 알아보세요.
type: docs
weight: 12
url: /ko/net/calendar-scheduling/calendar-exceptions/
---
## 소개

이 튜토리얼에서는 .NET 프레임워크를 사용하여 Aspose.Tasks에서 달력 예외를 관리하는 방법을 살펴보겠습니다. 달력 예외를 사용하면 휴일이나 임시 휴무 등 정규 작업 일정이 변경되는 프로젝트 달력에서 특별한 날짜나 기간을 정의할 수 있습니다. .NET용 Aspose.Tasks를 사용하여 달력 예외를 단계별로 처리하는 다양한 방법을 다룰 것입니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 Visual Studio가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.Tasks가 프로젝트에 추가되었습니다.

## 네임스페이스 가져오기

먼저 프로젝트에 필요한 네임스페이스를 가져오겠습니다.

```csharp
using Aspose.Tasks;
using System;


```

## 1단계: 달력 예외 삭제

캘린더 예외를 삭제하려면 다음 단계를 따르세요.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // 캘린더 정보 표시
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // 첫 번째 예외 제거
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## 2단계: 달력 예외의 근무 시간 가져오기

달력 예외의 작업 시간을 검색하려면 다음 단계를 따르십시오.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // 달력 및 예외 정보 표시
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // 근무 시간 확인 및 세부정보 표시
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## 3단계: 달력 예외 정의

캘린더 예외를 추가하거나 제거하려면 다음 단계를 따르세요.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // 새 캘린더 예외 만들기
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // 예외 세부정보 설정
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // 날짜가 예외인지 확인
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // 달력에 예외 추가
    calendar.Exceptions.Add(exception);

    // 존재하는 경우 예외 제거
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // 새 예외 추가
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // 인쇄 예외
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## 결론

이 기사에서는 .NET용 Aspose.Tasks에서 달력 예외를 처리하는 다양한 측면을 다루었습니다. 제공된 단계를 따르면 프로젝트 일정의 예외를 효과적으로 관리하여 근무 시간과 특별 이벤트를 정확하게 표시할 수 있습니다.

## FAQ

### Q1: 단일 달력에 여러 예외를 추가할 수 있나요?

A1: 예, 다양한 특별 날짜나 기간을 수용하기 위해 달력에 여러 예외를 추가할 수 있습니다.

### Q2: 특정 날짜가 예외인지 어떻게 확인할 수 있나요?

 A2: 다음을 사용할 수 있습니다.`CheckException()` 특정 날짜가 예외에 해당하는지 확인하는 방법입니다.

### Q3: 달력에서 기존 예외를 제거할 수 있습니까?

 A3: 예, 다음 페이지에 액세스하여 예외를 제거할 수 있습니다.`Exceptions` 달력 수집 및 사용`Remove()` 방법.

### Q4: 어떤 유형의 달력 예외가 지원됩니까?

A4: Aspose.Tasks는 일일, 주간, 월간 및 연간 예외를 포함한 다양한 유형의 예외를 지원하여 예외 규칙 정의에 유연성을 제공합니다.

### Q5: 특정 예외일의 근무 시간을 맞춤 설정할 수 있나요?

A5: 예, Aspose.Tasks에서 제공하는 적절한 방법을 사용하여 개별 예외 날짜에 대한 사용자 정의 작업 시간을 정의할 수 있습니다.