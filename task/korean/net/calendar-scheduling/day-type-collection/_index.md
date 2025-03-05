---
title: Aspose.Tasks에서 요일 유형 수집 관리
linktitle: Aspose.Tasks에서 요일 유형 수집 관리
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET에서 요일 유형 컬렉션을 효율적으로 관리하는 방법을 알아보세요. 캘린더 예외를 쉽게 생성, 수정 및 조작할 수 있습니다.
type: docs
weight: 28
url: /ko/net/calendar-scheduling/day-type-collection/
---
## 소개

 Aspose.Tasks for .NET은 요일 유형 컬렉션 관리를 위한 강력한 기능을 제공하며, 이는 프로젝트 관리 애플리케이션에서 주간 달력 예외를 정의하는 데 중요합니다. 이 튜토리얼에서는`DayTypeCollection` 효율적으로 수업합니다. 

## 전제조건

튜토리얼을 진행하기 전에 다음 전제 조건이 있는지 확인하십시오.

1. Visual Studio: 시스템에 Visual Studio가 설치되어 있는지 확인하세요.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C#에 대한 기본 지식: C# 프로그래밍 언어 및 .NET 프레임워크 개념에 대한 지식.

## 네임스페이스 가져오기

시작하려면 필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다.

```csharp
using Aspose.Tasks;
using System;


```

이제 제공된 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 로드 및 달력 액세스

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

이 단계에서는 새 프로젝트 인스턴스를 초기화하고 해당 UID로 달력을 검색합니다.

## 2단계: 달력 예외를 통해 반복

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

여기서는 각 달력 예외를 반복하고 해당 이름과 관련 요일 유형을 인쇄합니다.

## 3단계: 달력 예외 수정

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

이 단계에서는 요일 유형을 추가, 제거 또는 업데이트하여 달력 예외를 수정하는 방법을 보여줍니다.

## 4단계: 새 달력 예외 생성 및 조작

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

이 마지막 단계에서는 새로운 달력 예외를 생성하고 요일 유형을 추가하고 복사하여 이를 조작합니다.

## 결론

 결론적으로, Aspose.Tasks for .NET에서 요일 유형 컬렉션을 관리하는 것은 프로젝트 관리 애플리케이션에서 주간 달력 예외를 정의하고 수정하는 데 필수적입니다. 이 튜토리얼에서 제공하는 단계별 가이드를 따르면,`DayTypeCollection` 다양한 달력 작업을 처리하는 클래스입니다.

## FAQ

### Q1: Aspose.Tasks for .NET을 사용하여 프로그래밍 방식으로 Gantt 차트를 만들 수 있습니까?

A1: 예, Aspose.Tasks for .NET은 .NET 애플리케이션에서 Gantt 차트를 생성하고 조작할 수 있는 API를 제공합니다.

### Q2: Aspose.Tasks for .NET은 .NET Core 및 .NET Framework와 모두 호환됩니까?

A2: 예, .NET용 Aspose.Tasks는 .NET Core와 .NET Framework를 모두 지원합니다.

### Q3: .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?

 A3: 다음을 방문하여 지원을 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 질문을 하고 다른 사용자와 상호 작용할 수 있는 곳입니다.

### Q4: Aspose.Tasks for .NET은 무료 평가판을 제공합니까?

 A4: 예, 다음 사이트에서 Aspose.Tasks for .NET 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### Q5: Aspose.Tasks for .NET의 임시 라이선스를 구입할 수 있나요?

 A5: 예, 임시 라이센스는 다음 사이트에서 구입할 수 있습니다.[Aspose 웹사이트](https://purchase.aspose.com/temporary-license/).