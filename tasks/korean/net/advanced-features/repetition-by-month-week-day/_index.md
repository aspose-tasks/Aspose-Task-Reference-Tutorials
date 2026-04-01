---
date: 2026-04-01
description: Aspose.Tasks for .NET에서 반복 설정 방법을 배우고, 반복 작업을 추가하며, 월별, 주별, 일별로 반복 작업을
  자동화하세요.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Aspose.Tasks에서 월·주·일별 반복
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 반복 설정 방법 (월, 주, 일)
url: /ko/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 반복 설정 방법 (월, 주, 일)

## 소개

프로젝트의 작업에 대해 **반복 설정 방법**이 필요하다면, Aspose.Tasks for .NET은 월, 주, 일 단위로 실행되는 반복 작업 정의를 추가할 수 있는 깔끔하고 프로그래밍 방식의 방법을 제공합니다. 이 튜토리얼에서는 실제 예제를 통해 **반복 작업** 항목을 **추가하고**, **반복 작업 자동화**하며 C# 코드에서 직접 관리하는 방법을 단계별로 살펴봅니다. 끝까지 읽으면 이 기능을 모든 일정 관리 또는 프로젝트 관리 솔루션에 통합할 준비가 됩니다.

## 빠른 답변
- **Aspose.Tasks에서 “recurrence”는 무엇을 의미합니까?** 날짜 범위에 걸쳐 작업 인스턴스를 자동으로 생성하는 패턴(매일, 매주, 매월)을 정의합니다.  
- **반복을 생성하는 주요 메서드는 무엇입니까?** `RecurringTaskParameters`와 특정 `RecurrencePattern`을 결합합니다.  
- **이 코드를 실행하려면 라이선스가 필요합니까?** 평가용으로는 체험판이 작동하지만, 제품 환경에서는 상용 라이선스가 필요합니다.  
- **월별 대신 주별 작업을 예약할 수 있나요?** 예 – `MonthlyRecurrencePattern`을 `WeeklyRecurrencePattern`으로 교체하면 됩니다.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 및 이후 버전.

## Aspose.Tasks에서 반복이란 무엇입니까?

반복은 Aspose.Tasks에게 작업 인스턴스를 정기적인 간격(매일, 매주, 매월)으로 자동 생성하도록 지시하는 규칙 집합입니다. 이를 통해 작업을 수동으로 복제할 필요가 없습니다. 이 기능은 상태 회의, 검사, 유지보수 작업 등 정기적인 활동이 포함된 프로젝트에 필수적입니다.

## 왜 반복 기능을 사용해야 할까요?

- **시간 절약:** 작업을 수동으로 복사‑붙여넣기 할 필요가 없습니다.  
- **오류 감소:** 라이브러리가 일관된 날짜와 기간을 보장합니다.  
- **유연성:** 패턴을 결합할 수 있습니다(예: “매 2개월 첫 번째 일요일”).  
- **자동화:** CI 파이프라인이나 보고 도구에서 일정 생성에 최적입니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **C# 기본 이해** – 몇 줄의 C# 코드를 작성하게 됩니다.  
2. **Aspose.Tasks for .NET 설치** – [다운로드 페이지](https://releases.aspose.com/tasks/net/)에서 받으세요.  
3. **.mpp 프로젝트 파일** – 소스 파일로 `Project1.mpp`를 사용합니다.

## 네임스페이스 가져오기

시작하려면 필요한 Aspose.Tasks 네임스페이스를 가져옵니다:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 단계 1: 프로젝트 파일 로드

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

기존 Microsoft Project 파일을 가리키는 `Project` 인스턴스를 생성합니다.

### 단계 2: 반복 작업 매개변수 정의

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

여기서 **반복 작업** 매개변수를 생성합니다:

- **TaskName** – 생성된 작업의 이름입니다.  
- **Duration** – 각 발생이 지속되는 시간입니다.  
- **RecurrencePattern** – 매 2개월마다 첫 번째 일요일에 반복되는 월별 패턴입니다.  
- **RecurrenceRange** – 일정의 시작 및 종료 날짜를 정의합니다.

### 단계 3: 프로젝트에 반복 작업 추가

```csharp
project.RootTask.Children.Add(parameters);
```

이 코드는 **반복 작업**을 프로젝트 계층 구조의 루트에 추가합니다.

### 단계 4: 업데이트된 프로젝트 저장

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

프로젝트는 자동 일정이 포함된 새로운 `.mpp` 파일로 저장됩니다.

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결책 |
|-------|--------|-----|
| **작업이 표시되지 않음** | 반복 범위가 프로젝트 날짜 범위 밖에 있습니다. | `Start`와 `Finish` 값이 프로젝트 캘린더 내에 있는지 확인하십시오. |
| **잘못된 요일** | `WeekDay` 열거형이 일치하지 않습니다. | 필요에 따라 `DayOfWeek.Monday` … `DayOfWeek.Sunday`를 사용하십시오. |
| **라이선스 예외** | 프로덕션 환경에서 유효한 라이선스 없이 실행하고 있습니다. | 저장하기 전에 임시 또는 전체 라이선스를 적용하십시오. |

## 자주 묻는 질문

### Q1: 제공된 예제 외에 반복 패턴을 사용자 정의할 수 있나요?

A1: 예, Aspose.Tasks for .NET은 반복 패턴에 대한 광범위한 사용자 정의 옵션을 제공하므로 특정 요구 사항에 맞게 조정할 수 있습니다.

### Q2: Aspose.Tasks for .NET의 체험판 버전을 사용할 수 있나요?

A2: 예, [릴리스 페이지](https://releases.aspose.com/)에서 Aspose.Tasks for .NET의 무료 체험판을 받을 수 있습니다.

### Q3: Aspose.Tasks for .NET에 대한 지원을 어떻게 받을 수 있나요?

A3: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 요청하고 커뮤니티와 소통할 수 있습니다.

### Q4: Aspose.Tasks for .NET에 임시 라이선스가 제공되나요?

A4: 예, 테스트 및 평가 목적으로 [구매 페이지](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 획득할 수 있습니다.

### Q5: Aspose.Tasks for .NET에 대한 포괄적인 문서를 어디서 찾을 수 있나요?

A5: 라이브러리 활용에 대한 심층 가이드를 위해 Aspose 웹사이트에 있는 자세한 [문서](https://reference.aspose.com/tasks/net/)를 참고하십시오.

---

**마지막 업데이트:** 2026-04-01  
**테스트 환경:** Aspose.Tasks 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}