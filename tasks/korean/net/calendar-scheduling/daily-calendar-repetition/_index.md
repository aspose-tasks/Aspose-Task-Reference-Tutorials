---
title: Aspose.Tasks의 일일 달력 반복
linktitle: Aspose.Tasks의 일일 달력 반복
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET에서 일일 달력 반복으로 반복 작업을 생성하는 방법을 알아보세요. 손쉽게 프로젝트 관리 효율성을 향상하세요.
type: docs
weight: 25
url: /ko/net/calendar-scheduling/daily-calendar-repetition/
---
## 소개

 Aspose.Tasks for .NET은 작업과 프로젝트를 프로그래밍 방식으로 관리하기 위한 강력한 도구 세트를 제공합니다. 주목할만한 기능 중 하나는 일일 달력 반복을 효율적으로 처리하는 기능입니다. 이 튜토리얼에서는`DailyCalendarRepetition` 다른 관련 수업과 함께 수업을 진행하여 지정된 달력에 따라 매일 반복되는 반복 작업을 만듭니다.

## 전제조건

시작하기 전에 다음이 설정되어 있는지 확인하세요.

1.  설치: .NET용 Aspose.Tasks가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).

2. 네임스페이스 가져오기: 필요한 네임스페이스를 프로젝트로 가져옵니다.

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## 1단계: 프로젝트 초기화

먼저, 기존 프로젝트를 로드하거나 작업할 새 프로젝트를 만들어야 합니다.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 2단계: 달력 정의

다음으로, 24시간 단위의 달력을 생성하고 이를 프로젝트와 연결합니다.

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## 3단계: 반복 작업 매개변수 설정

이제 반복 작업에 대한 매개변수를 설정해 보겠습니다. 이름, 기간, 반복 패턴 및 범위를 정의합니다.

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## 4단계: 작업 달력 설정

정의된 달력을 작업과 연결합니다.

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## 5단계: 프로젝트에 작업 추가

정의된 매개변수가 있는 작업을 프로젝트에 추가합니다.

```csharp
project.RootTask.Children.Add(parameters);
```

## 6단계: 프로젝트 저장

마지막으로 반복 작업이 추가된 프로젝트를 저장합니다.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

이제 Aspose.Tasks for .NET을 사용하여 24시간 달력을 기준으로 매일 반복되도록 설정된 반복 작업이 포함된 프로젝트를 성공적으로 만들었습니다!

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks를 활용하여 일일 달력 반복을 효율적으로 처리하는 방법을 시연했습니다. 이러한 단계를 따르면 반복 작업을 프로젝트에 원활하게 통합하여 생산성과 구성을 향상할 수 있습니다.

## FAQ

### Q1: 각 반복 기간을 맞춤 설정할 수 있나요?

A1: 예, 코드의 매개변수를 수정하여 요구 사항에 따라 각 반복 기간을 조정할 수 있습니다.

### Q2: 동일한 프로젝트 내의 다양한 작업에 대해 서로 다른 달력을 설정할 수 있습니까?

A2: 물론입니다. Aspose.Tasks를 사용하면 특정 달력을 개별 작업에 할당하여 일정을 유연하게 설정할 수 있습니다.

### Q3: Aspose.Tasks는 매일 이외의 다른 반복 패턴을 지원합니까?

A3: 예, Aspose.Tasks는 다양한 프로젝트 요구에 맞춰 주간, 월간, 연간 등과 같은 광범위한 반복 패턴을 제공합니다.

### Q4: Aspose.Tasks를 사용하여 생성된 반복 작업을 시각화할 수 있나요?

A4: 물론 Aspose.Tasks는 반복 작업을 효과적으로 분석하고 추적하는 데 도움이 되는 시각화 옵션을 제공합니다.

### Q5: Aspose.Tasks에 사용할 수 있는 평가판이 있나요?

 A5: 예, Aspose의 무료 평가판을 이용할 수 있습니다.[여기](https://releases.aspose.com/) 구매하기 전에 기능을 살펴보세요.