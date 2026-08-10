---
date: 2026-04-09
description: Aspose.Tasks를 사용하여 .NET 프로젝트에서 표준 캘린더를 설정하고 프로젝트 휴일을 관리하는 방법을 배워 정확한
  일정 관리를 실현하세요.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Aspose.Tasks에서 표준 캘린더 설정 및 예외 처리
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 표준 캘린더 설정 및 예외 처리
url: /ko/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 표준 캘린더 설정 및 예외 처리

## 소개

정확한 일정 관리는 모든 성공적인 프로젝트의 핵심이며, 실제 계획은 휴일, 특별 행사 또는 예상치 못한 중단으로 인해 기본 작업 캘린더에서 벗어나야 할 경우가 많습니다. Aspose.Tasks for .NET은 **표준 캘린더 설정**을 쉽게 할 수 있게 하며, 그 위에 사용자 정의 예외를 추가할 수 있습니다. 이 튜토리얼에서는 프로젝트 캘린더를 로드하고, 표준 캘린더를 설정하며, Calendar Exception Collection 기능을 통해 프로젝트 휴일을 관리하는 방법을 배웁니다.

## 빠른 답변
- **“표준 캘린더 설정”이 무엇을 하나요?** 사용자 정의 예외를 추가하기 전에 캘린더를 기본 작업 시간(월‑금 9 AM‑5 PM)으로 재설정합니다.  
- **기존 예외를 제거하는 메서드는 무엇인가요?** `Calendar.Exceptions.Clear()`는 이전에 정의된 모든 예외를 제거합니다.  
- **휴일을 어떻게 추가하나요?** `DayWorking = false`인 `CalendarException`을 생성하고 컬렉션에 추가합니다.  
- **변경 후 프로젝트를 다시 로드해야 하나요?** 아니요, 변경 사항은 메모리 내 `Project` 객체에 바로 적용됩니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for .NET(지원되는 .NET 버전)과 `System` 네임스페이스.

## 전제 조건

코드에 들어가기 전에 다음을 준비하세요:

1. **Aspose.Tasks for .NET** – [여기](https://releases.aspose.com/tasks/net/)에서 다운로드하십시오.  
2. **C#** 기본 지식 – 몇 개의 짧은 코드 조각을 작성하게 됩니다.  
3. **Visual Studio** 또는 **JetBrains Rider**와 같은 개발 환경.

## 네임스페이스 가져오기

`using` 지시문을 사용하면 캘린더 조작에 필요한 클래스를 사용할 수 있습니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 캘린더 예외란 무엇인가요?

*캘린더 예외*는 일반 작업 일정이 변경되는 기간을 의미합니다 – 예를 들어, 전사적인 휴일이나 일시적인 초과 근무 일정 등이 있습니다. 캘린더에 예외를 추가함으로써 기본 캘린더를 변경하지 않고도 실제 제약 조건을 모델링할 수 있습니다.

## Aspose.Tasks에서 표준 캘린더 설정 방법

첫 번째 단계는 프로젝트 파일을 로드하고 작업하려는 캘린더를 가져오는 것입니다.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### 단계 1: 기존 예외 제거 및 표준 캘린더로 재설정

새 규칙을 추가하기 전에 기존 예외를 모두 제거하고 **표준 캘린더** 설정을 하는 것이 좋은 습관입니다. 이렇게 하면 깨끗한 기준선을 확보할 수 있습니다.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### 단계 2: 작업 시간 예외 정의

때때로 임시 일정을 만들어야 할 경우가 있습니다(예: 제품 출시를 위한 연장 근무). 다음 코드 조각은 며칠에 걸쳐 두 개의 일일 작업 기간을 포함하는 작업 시간 예외를 정의합니다.

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

### 단계 3: 비작업 시간 예외 추가 (휴일)

**프로젝트 휴일을 관리**하려면 `DayWorking`이 `false`인 예외를 생성합니다. 아래 예시는 2일간의 휴일 블록을 추가합니다.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### 단계 4: 캘린더 예외 표시 (검증)

예외를 추가한 후에는 올바르게 기록되었는지 확인하고 싶을 때가 많습니다. 다음 루프는 각 예외의 세부 정보를 콘솔에 출력합니다.

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

### 단계 5: 모든 예외 제거 (정리)

캘린더를 원래 상태로 되돌려야 할 경우, 프로그래밍 방식으로 모든 예외를 제거할 수 있습니다.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| 저장 후 예외가 나타나지 않음 | 수정 후 프로젝트가 저장되지 않음 | 변경 후 `project.Save("output.mpp")`를 호출합니다. |
| 겹치는 예외로 인해 예상치 못한 작업 시간이 발생 | Aspose.Tasks는 겹치는 기간에 마지막으로 추가된 예외를 사용합니다. | `Add` 호출 순서를 신중히 정하거나 우선순위를 수동으로 조정합니다. |
| `MakeStandardCalendar`가 사용자 정의 작업 시간을 재설정 | 이 메서드는 의도적으로 사용자 정의 시간을 삭제합니다; 필요하면 호출 후 다시 추가하십시오. | `MakeStandardCalendar` 호출 후 사용자 정의 `WorkingTime` 객체를 추가합니다. |

## 자주 묻는 질문

**Q: 하나의 캘린더에 여러 예외를 추가할 수 있나요?**  
A: 예, `AddRange` 메서드를 사용하여 캘린더에 여러 예외를 추가할 수 있습니다.

**Q: 주간 휴일과 같은 반복 예외를 어떻게 처리하나요?**  
A: 프로그래밍 방식으로 반복 예외를 계산하고 사용자 정의 로직을 사용해 캘린더에 추가할 수 있습니다.

**Q: 외부 소스에서 캘린더 예외를 가져올 수 있나요?**  
A: 예, 데이터베이스나 CSV 파일과 같은 외부 소스에서 캘린더 예외를 읽어 프로젝트에 통합할 수 있습니다.

**Q: 캘린더에 겹치는 예외가 있으면 어떻게 되나요?**  
A: Aspose.Tasks for .NET은 우선순위를 정의하거나 프로젝트 요구 사항에 따라 충돌을 해결함으로써 겹치는 예외를 처리할 수 있게 합니다.

**Q: 예외 내의 각 날짜에 대해 작업 시간을 맞춤 설정할 수 있나요?**  
A: 예, 특정 일정 요구에 맞게 예외 내 개별 날짜의 작업 시간을 사용자 정의할 수 있습니다.

## 결론

**표준 캘린더를 먼저 설정하고 그 위에 사용자 정의 예외를 추가**함으로써 프로젝트 일정에 대한 완전한 제어권을 얻을 수 있으며, **프로젝트 휴일** 및 기타 특수 일정 관리가 쉬워집니다. Aspose.Tasks의 Calendar Exception Collection은 .NET 애플리케이션 내에서 실제 캘린더를 직접 모델링할 수 있는 깔끔하고 프로그래밍 가능한 방법을 제공합니다.

---

**마지막 업데이트:** 2026-04-09  
**테스트 환경:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}