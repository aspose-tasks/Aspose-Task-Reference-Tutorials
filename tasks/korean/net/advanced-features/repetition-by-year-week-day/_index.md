---
date: 2026-04-03
description: Aspose.Tasks를 사용하여 반복 작업 프로젝트를 추가하고 프로젝트를 MPP 파일로 저장하는 방법을 배웁니다. 이 가이드는
  연, 주, 일별 반복 기능을 단계별로 보여줍니다.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Aspose.Tasks에서 연, 주, 일별 반복
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks 사용 방법 – 연, 주, 일 단위 반복
url: /ko/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 연도 주 요일별 반복

## 소개

복잡한 반복 일정 처리를 위해 **how to use Aspose.Tasks**가 필요할 때, 이 라이브러리는 연간 패턴에 대한 세밀한 제어를 제공합니다. 이 튜토리얼에서는 특정 월의 특정 요일에 반복되는 작업을 여러 해에 걸쳐 만드는 과정을 단계별로 안내합니다. 끝까지 진행하면 몇 줄의 C# 코드만으로 **add recurring task project** 항목을 추가하고 **save project as MPP** 할 수 있게 됩니다.

## 빠른 답변
- **What does “Repetition by Year Week Day” mean?** 연도와 주, 요일을 기준으로 하는 반복이 의미하는 바는 선택한 월의 특정 요일(예: 첫 번째 일요일)에 매년 작업이 반복된다는 것입니다.  
- **Which .NET versions are supported?** 모든 최신 .NET Framework 및 .NET Core/5/6 버전을 지원합니다.  
- **Do I need a license to run the code?** 개발용으로는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **Can I change the recurrence range?** 예 – 시작 날짜, 종료 날짜 또는 고정된 발생 횟수를 설정할 수 있습니다.  
- **Is the output an MPP file?** 네 – 프로젝트가 Microsoft Project용 MPP 파일로 저장됩니다.

## “Repetition by Year Week Day” 기능이란?

이 기능을 사용하면 특정 **day of the week**(예: Sunday)와 월 내 **position**(첫 번째, 두 번째, 마지막 등)을 목표로 하는 연간 반복을 정의할 수 있습니다. 이는 분기별 검토, 연간 감사 또는 달력 기반 주기를 따르는 모든 이벤트에 이상적입니다.

## 반복 작업에 Aspose.Tasks를 사용하는 이유는?

- **Precision** – 월, 요일 및 서수 위치에 대한 완전한 제어를 제공합니다.  
- **Compatibility** – Microsoft Project에서 완벽히 열리는 네이티브 MPP 파일을 생성합니다.  
- **No COM interop** – 순수 .NET API이며 Office 설치가 필요하지 않습니다.  
- **Scalability** – 소규모 프로젝트부터 엔터프라이즈 수준 일정까지 모두 작동합니다.

## 전제 조건

Before diving into the code, make sure you have:

1. **Basic .NET knowledge** – C# 및 객체 지향 개념에 익숙합니다.  
2. **Aspose.Tasks for .NET** – [download link](https://releases.aspose.com/tasks/net/)에서 다운로드하고 DLL을 프로젝트에 추가합니다.  
3. **Access to the official docs** – [documentation](https://reference.aspose.com/tasks/net/)에는 모든 클래스에 대한 자세한 내용이 포함되어 있습니다.  
4. **A development IDE** – Visual Studio, Rider 또는 호환 가능한 .NET 편집기 중 하나를 사용합니다.

준비가 되었으니 구현을 살펴보겠습니다.

## 반복 작업에 Aspose.Tasks 사용 방법

### 필요한 네임스페이스 가져오기

먼저, 프로젝트, 작업 및 저장 옵션을 다루기 위해 필요한 네임스페이스를 범위에 가져옵니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 1단계: 프로젝트 및 작업 매개변수 초기화

`Project` 인스턴스를 새로 생성하고, 반복 패턴을 설명하는 `RecurringTaskParameters` 객체를 정의합니다.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** 실제 일정에 맞게 `Month`, `WeekDay`, `Position`을 조정하세요.

### 2단계: 매개변수를 프로젝트에 추가

반복 작업 정의를 프로젝트의 루트에 삽입합니다.

```csharp
project.RootTask.Children.Add(parameters);
```

### 3단계: 프로젝트를 MPP로 저장

마지막으로 프로젝트를 MPP 파일로 저장하여 Microsoft Project 또는 호환 뷰어에서 열 수 있도록 합니다.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> 이는 한 줄의 코드로 **save project as mpp** 를 시연합니다.

## 일반적인 문제 및 해결책

| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| MPP 파일을 열었을 때 작업이 표시되지 않음 | 반복 범위 날짜가 프로젝트 캘린더 외에 있음 | `Start` 및 `Finish` 날짜가 프로젝트 작업 시간 내에 있는지 확인하십시오 |
| `Add` 시 `ArgumentNullException` 예외 발생 | `parameters`가 null이거나 완전히 초기화되지 않음 | 모든 필수 속성(TaskName, Duration, RecurrencePattern)이 설정되었는지 확인하십시오 |
| 잘못된 요일 선택 | `WeekDay` 열거형 값이 일치하지 않음 | 필요에 따라 `DayOfWeek.Monday` … `DayOfWeek.Sunday`를 사용하십시오 |

## 자주 묻는 질문

**Q: Can I customize the recurrence pattern beyond the provided example?**  
A: 예, Aspose.Tasks를 사용하면 `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` 또는 사용자 정의 `RecurrenceRange` 객체를 결합하여 모든 일정에 맞출 수 있습니다.

**Q: Is Aspose.Tasks for .NET compatible with other project management software?**  
A: Absolutely – the library reads and writes MPP, XML, and Primavera formats, enabling smooth data exchange.

**Q: How can I handle exceptions or modifications to recurring tasks?**  
A: Use the `ExceptionTask` class to create overrides for specific occurrences, or edit the `RecurringTaskParameters` and re‑save the project.

**Q: Does Aspose.Tasks support cloud‑based solutions?**  
A: Yes, you can run the API in Azure Functions, AWS Lambda, or any .NET‑compatible cloud service.

**Q: Is there a trial version available for Aspose.Tasks for .NET?**  
A: Yes, you can access a free trial of Aspose.Tasks for .NET from the [website](https://releases.aspose.com/), allowing you to explore its features before making a purchase decision.

**Q: How do I add a recurring task to an existing project without overwriting other data?**  
A: Load the existing project with `new Project("Existing.mpp")`, add the `RecurringTaskParameters` to `RootTask.Children`, and then `Save` the file.

## 결론

**how to use Aspose.Tasks**와 **Repetition by Year Week Day** 시나리오를 숙달하면 실제 캘린더와 완벽히 일치하는 **add recurring task project** 항목을 추가하고 원활한 협업을 위해 **save project as MPP** 할 수 있는 능력을 얻게 됩니다. 이러한 코드 조각을 솔루션에 통합하여 일정 정확성을 높이고 수동 작업을 줄이세요.

---

**마지막 업데이트:** 2026-04-03  
**테스트 환경:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}