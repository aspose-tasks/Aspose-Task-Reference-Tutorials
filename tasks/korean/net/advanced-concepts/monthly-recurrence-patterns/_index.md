---
date: 2026-03-08
description: Aspose.Tasks for .NET에서 월간 반복 작업을 만드는 방법을 단계별 튜토리얼로 배워보세요.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 월간 반복 작업 만들기
url: /ko/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 월간 반복 작업 만들기

## 소개

Aspose.Tasks for .NET을 사용하면 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있으며, 가장 흔한 실제 요구 중 하나는 **월간 반복 작업** 일정을 만드는 것입니다. 프로젝트 추적 도구를 구축하든, 리소스 할당을 자동화하든, 정기적인 유지보수 작업 항목을 생성하든, 이 튜토리얼에서는 작업에 월간 반복 패턴을 추가하는 정확한 단계를 단계별로 안내합니다.

다음 섹션에서는 프로젝트를 설정하고, 반복 매개변수를 정의한 뒤, 업데이트된 파일을 저장하는 방법을 명확한 설명과 실용적인 팁과 함께 보여드립니다.

## 빠른 답변
- **“월간 반복 작업”이란 무엇인가요?** 매월 정의된 일자 또는 요일 패턴에 따라 반복되는 작업입니다.  
- **반복을 처리하는 API 클래스는 무엇인가요?** `RecurringTaskParameters`와 `MonthlyRecurrencePattern`이 함께 사용됩니다.  
- **샘플을 실행하려면 라이선스가 필요합니까?** 평가용으로는 무료 체험판으로 충분하지만, 실제 운영 환경에서는 라이선스가 필요합니다.  
- **간격을 변경할 수 있나요?** 예 – `RepetitionInterval`에 발생 간격(개월 수)을 설정하면 됩니다.  
- **지원되는 파일 형식은 무엇인가요?** `.mpp`와 `.xml` Project 파일 모두 로드 및 저장이 가능합니다.

## 월간 반복 패턴이란?

월간 반복 패턴은 Microsoft Project(및 Aspose.Tasks)에 작업이 매월 얼마나 자주 반복되어야 하는지를 알려줍니다. 월의 고정된 날짜(예: 1일) 또는 상대적인 위치(예: 마지막 금요일)를 지정할 수 있습니다. API는 이러한 규칙을 기본 Project 파일 구조에 반영합니다.

## 왜 Aspose.Tasks를 사용해야 할까요?

- **전체 제어** – UI 제한이 없으며, 코드에서 패턴의 모든 요소를 정의합니다.  
- **크로스‑플랫폼** – .NET Framework, .NET Core, .NET 5/6+에서 모두 동작합니다.  
- **Microsoft Project 불필요** – 서버나 CI 파이프라인에서 파일을 생성·수정할 수 있습니다.  

## 전제 조건

시작하기 전에 다음이 설치되어 있는지 확인하세요.

- .NET 6(또는 .NET 5/Framework 4.7+)이 설치되어 있어야 합니다.  
- 프로젝트에 Aspose.Tasks for .NET NuGet 패키지가 추가되어 있어야 합니다.  
- 샘플 Project 파일(`Project1.mpp`)을 알려진 폴더(`DataDir`)에 배치합니다.  

## 네임스페이스 가져오기

작업을 다루고 프로젝트를 저장하는 데 필요한 네임스페이스를 먼저 가져옵니다:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## 단계 1: 프로젝트 초기화

기존 `.mpp` 파일을 가리키는 `Project` 인스턴스를 생성합니다. 이 인스턴스는 파일을 메모리로 로드하여 수정할 수 있게 합니다.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **프로 팁:** 파일이 존재하지 않으면 Aspose.Tasks가 자동으로 새 빈 프로젝트를 생성합니다.

## 단계 2: 반복 작업 매개변수 설정

반복 작업의 이름, 기간 및 적용할 월간 패턴 등 세부 정보를 정의합니다.

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1`은 작업이 **월의 첫 번째 날**에 발생함을 의미합니다.  
- `RepetitionInterval = 2`는 작업이 **두 달마다** 반복됨을 나타냅니다.  
- `Start`와 `Finish`는 반복이 활성화되는 전체 기간을 정의합니다.

## 단계 3: 프로젝트에 매개변수 추가

`RecurringTaskParameters` 객체를 루트 작업의 하위 컬렉션에 연결합니다. 이렇게 하면 프로젝트 계층 구조에 반복 작업이 실제로 생성됩니다.

```csharp
project.RootTask.Children.Add(parameters);
```

## 단계 4: 프로젝트 저장

변경 사항을 새 파일에 저장하여 영구히 반영합니다. 지원되는 형식 중 원하는 것을 선택할 수 있으며, 여기서는 기본 `.mpp` 형식을 사용합니다.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

코드를 실행한 후, Microsoft Project에서 결과 파일을 열면 방금 만든 월간 반복 작업을 확인할 수 있습니다.

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결 방법 |
|-------|-------|-----|
| 저장 후 작업이 표시되지 않음 | UI에서 프로젝트가 새로 고침되지 않음 | 파일을 다시 열거나 저장 전에 `project.UpdateTaskLinks()`를 호출합니다. |
| 시작 날짜가 잘못됨 | `Start`가 주말로 설정됨 | 작업일이 되는 `DateTime`을 사용하거나 캘린더를 조정합니다. |
| 반복 간격이 무시됨 | `DayPosition` = 0인 `ByMonthDayRepetition` 사용 | `DayPosition`이 1‑31 사이인지 확인합니다. |

## 결론

이 단계를 따라 하면 Aspose.Tasks for .NET을 사용해 **월간 반복 작업** 일정을 만드는 방법을 알게 됩니다. API를 통해 반복 간격, 시작·종료 범위, 특정 일자 패턴을 세밀하게 제어할 수 있어 복잡한 프로젝트 계획 시나리오를 자동화할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks가 모든 버전의 Microsoft Project 파일과 호환되나요?

A1: Aspose.Tasks는 MPP, MPT, XML, MPX 등 다양한 Microsoft Project 파일 형식을 지원합니다.

### Q2: 반복 패턴을 더 세부적으로 커스터마이즈할 수 있나요?

A2: 예, Aspose.Tasks는 일간, 주간, 월간, 연간 등 다양한 반복 패턴 옵션을 제공합니다.

### Q3: Aspose.Tasks의 무료 체험판을 이용할 수 있나요?

A3: 예, 웹사이트 [here](https://releases.aspose.com/)에서 Aspose.Tasks 무료 체험판을 받을 수 있습니다.

### Q4: Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?

A4: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 도움을 받거나 토론에 참여할 수 있습니다.

### Q5: Aspose.Tasks 라이선스는 어디서 구매하나요?

A5: 웹사이트 [here](https://purchase.aspose.com/buy)에서 Aspose.Tasks 라이선스를 구매할 수 있습니다.

## 자주 묻는 질문

**Q: 이 코드를 .NET Core 애플리케이션에서 사용할 수 있나요?**  
**A:** 물론 가능합니다. Aspose.Tasks for .NET은 .NET Core 3.1 및 이후 버전을 완전히 지원합니다.

**Q: 반복을 “월의 마지막 평일”로 변경하려면 어떻게 해야 하나요?**  
**A:** `ByMonthDayRepetition`에 `DayPosition = -1`(음수 값은 월 말부터 역순)으로 설정하고 `WeekDay`를 적절히 지정하면 됩니다.

**Q: 반복 범위가 프로젝트 캘린더를 초과하면 어떻게 되나요?**  
**A:** API는 프로젝트 캘린더를 따릅니다. 비근무일에 해당하는 발생은 캘린더 설정에 따라 건너뛰거나 이동됩니다.

**Q: 특정 반복 작업 발생을 삭제할 수 있나요?**  
**A:** 가능합니다. 반복 작업을 추가한 뒤 `Task.GetOccurrences()`를 통해 개별 발생을 가져와 필요 없는 항목을 삭제하면 됩니다.

**Q: Aspose.Tasks가 시간대 차이를 자동으로 처리하나요?**  
**A:** 라이브러리는 날짜를 UTC로 저장합니다. 필요에 따라 표준 .NET `DateTime` 메서드를 사용해 로컬 시간으로 변환할 수 있습니다.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}