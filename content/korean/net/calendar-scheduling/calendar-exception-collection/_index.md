---
title: Aspose.Tasks의 달력 예외 수집
linktitle: Aspose.Tasks의 달력 예외 수집
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks를 사용하여 .NET 프로젝트에서 달력 예외를 효율적으로 처리하여 정확한 일정과 리소스 관리를 보장하는 방법을 알아보세요.
type: docs
weight: 13
url: /ko/net/calendar-scheduling/calendar-exception-collection/
---
## 소개

프로젝트 관리에서는 정확한 일정 관리가 성공을 위해 매우 중요합니다. 그러나 실제 시나리오에서는 휴일, 특별 이벤트 또는 기타 요인으로 인해 표준 일정에서 벗어나는 경우가 많습니다. Aspose.Tasks for .NET은 Calendar Exception Collection 기능을 통해 이러한 예외를 관리하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 이 기능을 활용하는 과정을 단계별로 안내합니다.

## 전제조건

튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.

1.  .NET용 Aspose.Tasks: 라이브러리가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
2. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙하면 예제를 이해하는 데 도움이 됩니다.
3. 개발 환경: Visual Studio 또는 JetBrains Rider 등 원하는 개발 환경을 설정합니다.

## 네임스페이스 가져오기

.NET용 Aspose.Tasks 작업을 시작하기 전에 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이 단계를 통해 달력 예외를 관리하는 데 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

이제 제공된 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 로드 및 달력 검색

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

이 단계에서는 프로젝트 파일을 로드하고 해당 UID로 원하는 달력을 검색합니다.

## 2단계: 기존 예외 지우기 및 표준 달력 설정

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

이 단계는 달력에서 기존 예외를 모두 지우고 표준 구성으로 설정합니다.

## 3단계: 근무 시간 예외 정의 및 추가

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

이 단계에서는 특정 시작 및 종료 날짜와 해당 날짜 내의 작업 시간을 포함하는 작업 시간 예외를 정의하고 이를 달력에 추가합니다.

## 4단계: 근무 외 시간 예외 정의 및 추가

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// 필요한 경우 더 많은 예외를 추가하세요.

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

이 단계에서는 휴일 등 휴무 시간 예외를 정의하고 이를 달력에 추가합니다.

## 5단계: 달력 예외 표시

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

이 단계에서는 추가된 달력 예외와 해당 세부정보가 표시됩니다.

## 6단계: 모든 예외 제거

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

마지막으로 이 단계는 달력에서 모든 예외를 제거합니다.

## 결론

정확한 프로젝트 일정을 계획하려면 일정 예외를 관리하는 것이 중요합니다. Aspose.Tasks for .NET은 Calendar Exception Collection을 포함한 포괄적인 기능 세트를 제공하여 이 작업을 단순화합니다. 이 튜토리얼에 설명된 단계를 따르면 프로젝트 내의 다양한 일정 시나리오를 효율적으로 처리할 수 있습니다.

## FAQ

### Q1: 단일 달력에 여러 예외를 추가할 수 있나요?

 A1: 예, 다음을 사용하여 달력에 여러 예외를 추가할 수 있습니다.`AddRange` 방법.

### Q2: 주휴일 등 반복되는 예외사항은 어떻게 처리하나요?

대답 2: 반복되는 예외를 프로그래밍 방식으로 계산하고 사용자 지정 논리를 사용하여 달력에 추가할 수 있습니다.

### Q3: 외부 소스에서 달력 예외를 가져올 수 있습니까?

A3: 예, 데이터베이스나 CSV 파일과 같은 외부 소스에서 달력 예외를 읽고 프로젝트에 통합할 수 있습니다.

### Q4: 달력에 중복되는 예외가 있으면 어떻게 됩니까?

A4: .NET용 Aspose.Tasks를 사용하면 프로젝트 요구 사항에 따라 우선 순위를 정의하거나 충돌을 해결하여 중복되는 예외를 처리할 수 있습니다.

### Q5: 예외 내에서 매일 근무 시간을 맞춤 설정할 수 있나요?

A5: 예, 특정 일정 요구 사항을 수용하기 위해 예외 내에서 개별 날짜에 대한 사용자 정의 작업 시간을 지정할 수 있습니다.