---
title: Aspose.Tasks에서 월별 반복 패턴 처리
linktitle: Aspose.Tasks에서 월별 반복 패턴 처리
second_title: Aspose.태스크 .NET API
description: 이 단계별 튜토리얼을 통해 Aspose.Tasks for .NET에서 월별 반복 패턴을 처리하는 방법을 알아보세요.
type: docs
weight: 18
url: /ko/net/advanced-concepts/monthly-recurrence-patterns/
---
## 소개

Aspose.Tasks for .NET은 개발자가 프로그래밍 방식으로 Microsoft Project 파일을 조작할 수 있는 강력한 API입니다. 그것이 제공하는 필수 기능 중 하나는 반복되는 작업을 효율적으로 처리하는 능력입니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 월별 반복 패턴으로 작업하는 방법을 단계별로 살펴보겠습니다.

## 전제조건

시작하기 전에 다음 필수 구성 요소가 설치되어 있는지 확인하세요.

## 네임스페이스 가져오기

먼저 .NET 프로젝트에 필요한 네임스페이스를 가져왔는지 확인하세요.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

이제 월별 반복 패턴을 처리하는 프로세스를 여러 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 초기화

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 2단계: 반복 작업 매개변수 설정

작업 이름, 기간, 반복 패턴을 포함하여 반복 작업에 대한 매개변수를 정의합니다.

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

## 3단계: 프로젝트에 매개변수 추가

```csharp
project.RootTask.Children.Add(parameters);
```

## 4단계: 프로젝트 저장

반복 작업으로 수정된 프로젝트를 저장합니다.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## 결론

Aspose.Tasks for .NET에서 월별 반복 패턴을 처리하는 것은 간단하고 효율적입니다. 이 자습서에 설명된 단계를 따르면 특정 월간 간격과 반복 범위를 사용하여 반복 작업을 쉽게 만들 수 있습니다.

## FAQ

### Q1: Aspose.Tasks는 모든 버전의 Microsoft Project 파일과 호환됩니까?

A1: Aspose.Tasks는 MPP, MPT, XML 및 MPX를 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.

### Q2: 반복 패턴을 추가로 사용자 정의할 수 있나요?

A2: 예, Aspose.Tasks는 매일, 매주, 매월, 매년을 포함하여 반복 패턴을 사용자 정의하기 위한 광범위한 옵션을 제공합니다.

### Q3: Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?

 A3: 예, 웹사이트에서 Aspose.Tasks의 무료 평가판을 얻을 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?

 답변 4: 귀하는 다음 사항에 관해 도움을 구하고 토론에 참여할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).

### Q5: Aspose.Tasks 라이선스는 어디서 구매할 수 있나요?

 A5: 웹사이트에서 Aspose.Tasks 라이선스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy)