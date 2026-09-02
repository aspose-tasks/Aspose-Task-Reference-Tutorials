---
date: 2026-04-13
description: Aspose.Tasks for .NET에서 캘린더 예외를 삭제하는 방법을 배우고, ASP.NET 캘린더 일정 관리 시 예외
  날짜를 확인하세요.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Aspose.Tasks로 캘린더 예외 삭제
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks를 사용하여 캘린더 예외 삭제
url: /ko/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks와 함께 캘린더 예외 삭제

## 소개

이 튜토리얼에서는 **delete calendar exception**을 수행하고 Aspose.Tasks에서 .NET 프레임워크를 사용하여 다른 캘린더 예외를 관리하는 방법을 배웁니다. 캘린더 예외를 사용하면 휴일, 일시적인 폐쇄 또는 일반 작업 일정이 변경되는 특별한 기간을 모델링할 수 있습니다. 이러한 예외를 추가, 조회 및 제거하는 방법을 이해하는 것은 정확한 프로젝트 일정 관리에 필수적이며, 특히 **ASP.NET calendar scheduling** 시나리오에서 중요합니다.

## 빠른 답변
- **예외를 제거하는 기본 메서드는 무엇입니까?** `CalendarException` 객체의 `Delete()` 메서드를 사용합니다.  
- **예외에 대해 날짜를 확인하는 클래스는 무엇입니까?** `CalendarException.CheckException()` — **check exception date**를 확인하는 데 유용합니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 예, 프로덕션 사용을 위해 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **하나의 캘린더에 여러 예외를 추가할 수 있나요?** 물론입니다; `Exceptions` 컬렉션은 다수의 항목을 지원합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## 캘린더 예외란?

**calendar exception**은 일반 작업 캘린더에서 벗어나는 경우를 나타냅니다—즉, “이 날짜에는 근무 시간이 다르거나 전혀 없음”이라는 규칙이라고 생각하면 됩니다. Aspose.Tasks에서 각 예외는 자체 작업 시간, 반복 패턴 및 해당 날짜가 작업일인지 여부를 나타내는 플래그를 가질 수 있습니다.

## ASP.NET Calendar Scheduling에서 캘린더 예외를 관리해야 하는 이유

- **정확한 일정:** 프로젝트가 자동으로 휴일 및 특별 폐쇄를 고려하여 비현실적인 마감일을 방지합니다.  
- **유연성:** 일일, 주간, 월간 또는 연간 패턴을 정의하여 실제 비즈니스 캘린더와 일치시킬 수 있습니다.  
- **자동화:** 예외 날짜를 프로그래밍 방식으로 확인함으로써 ASP.NET 애플리케이션에서 동적 일정 로직을 구축할 수 있습니다.

## 전제 조건

- C# 프로그래밍에 대한 기본 지식.  
- Visual Studio(최근 버전).  
- 프로젝트에 Aspose.Tasks for .NET 라이브러리를 추가(NuGet 또는 수동 참조).

## 네임스페이스 가져오기

먼저, 필요한 네임스페이스를 가져옵니다:

```csharp
using Aspose.Tasks;
using System;
```

## 단계 1: 캘린더 예외 삭제

원하지 않는 예외를 제거하는 것은 간단합니다. 아래 코드는 프로젝트를 로드하고, 첫 번째 캘린더를 선택한 뒤 기본 정보를 표시하고, 첫 번째 예외를 삭제한 후 업데이트된 개수를 보여줍니다.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **팁:** `Delete()`를 호출하기 전에 예외 인덱스가 존재하는지 항상 확인하여 `IndexOutOfRangeException`을 방지하세요.

## 단계 2: 캘린더 예외의 작업 시간 가져오기

예외에 정의된 작업 시간을 확인해야 하면 `GetWorkingTime()`을 사용합니다. 이 예제는 `CheckException`을 사용하여 **check exception date**를 확인하는 방법도 보여줍니다.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## 단계 3: 캘린더 예외 정의

아래는 캘린더 예외를 **add**, **check**, **remove**하는 전체 과정을 보여주는 예제입니다. 특정 순간에 **check exception date**를 확인하기 위해 `CheckException`을 사용하는 것을 확인하세요.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## 일반적인 문제 및 팁

| 문제 | 원인 | 해결 방법 |
|-------|--------|----------|
| **삭제 시 `IndexOutOfRangeException`** | 존재하지 않는 예외를 삭제하려고 시도함. | `Delete()` 호출 전에 `calendar.Exceptions.Count`가 인덱스보다 큰지 확인합니다. |
| **잘못된 작업 시간** | `DayWorking` 또는 `WorkingTimes`를 올바르게 설정하지 않음. | `exception.WorkingTimes.Add(new WorkingTime(...))`를 사용하여 명시적인 기간을 정의합니다. |
| **예외가 인식되지 않음** | `CheckException`이 정의된 범위를 벗어난 날짜이므로 `false`를 반환함. | `FromDate`/`ToDate`와 `Type`(Daily, Weekly 등)을 다시 확인합니다. |

## 자주 묻는 질문

**Q: 단일 캘린더에 여러 예외를 추가할 수 있나요?**  
A: 예, 휴일, 유지보수 기간 또는 기타 특별 일정 규칙을 나타내기 위해 필요한 만큼 많은 예외를 추가할 수 있습니다.

**Q: 특정 날짜에 **check exception date**를 어떻게 확인합니까?**  
A: `CalendarException` 인스턴스의 `CheckException(DateTime date)` 메서드를 사용합니다. 제공된 날짜가 예외 범위에 포함되면 `true`를 반환합니다.

**Q: 캘린더에서 기존 예외를 제거할 수 있나요?**  
A: 물론 가능합니다. `Exceptions` 컬렉션에 접근하여 `Remove()`를 호출하거나 특정 `CalendarException` 객체에서 `Delete()`를 호출합니다.

**Q: 어떤 유형의 캘린더 예외를 지원하나요?**  
A: Aspose.Tasks는 Daily, Weekly, Monthly, Yearly 예외 유형을 지원하여 거의 모든 반복 패턴을 모델링할 수 있는 유연성을 제공합니다.

**Q: 특정 예외 날짜에 대한 작업 시간을 사용자 정의할 수 있나요?**  
A: 예. 예외를 만든 후 해당 날짜의 시작 및 종료 시간을 정의하는 `WorkingTime` 객체를 `WorkingTimes` 컬렉션에 추가합니다.

## 결론

우리는 기존 예외를 검사하고 새 예외를 추가하며 날짜를 확인하는 **delete calendar exception** 작업의 전체 수명 주기를 살펴보았습니다. 이러한 기술을 숙달하면 프로젝트 일정이 실제 캘린더를 반영하게 되어 ASP.NET 캘린더 일정 구현이 견고하고 신뢰할 수 있게 됩니다.

---

**마지막 업데이트:** 2026-04-13  
**테스트 환경:** Aspose.Tasks for .NET (latest release)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}