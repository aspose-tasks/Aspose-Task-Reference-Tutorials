---
title: Aspose.Tasks의 일일 작업 반복
linktitle: Aspose.Tasks의 일일 작업 반복
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일에서 매일 반복되는 작업을 만드는 방법을 알아보세요. 손쉽게 생산성과 조직성을 향상하세요.
type: docs
weight: 26
url: /ko/net/calendar-scheduling/daily-work-repetition/
---
## 소개

Aspose.Tasks for .NET은 개발자가 Microsoft Project 파일을 쉽게 조작할 수 있게 해주는 강력한 라이브러리입니다. 수많은 기능 중에는 반복되는 작업을 효율적으로 처리하는 기능이 있습니다. 이 튜토리얼에서는 프로젝트 내에서 매일 반복되는 작업을 생성할 수 있는 일일 작업 반복 기능을 자세히 살펴보겠습니다.

## 전제조건

이 튜토리얼을 시작하기 전에 다음 사항을 확인하세요.

- C# 및 .NET 프레임워크에 대한 기본 지식
- 시스템에 Visual Studio가 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Tasks. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
- Microsoft Project 파일(.mpp)에 대한 지식.

## 네임스페이스 가져오기

시작하기 전에 필요한 네임스페이스를 가져왔는지 확인하세요.

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

제공된 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 파일 로드

먼저, 다음을 사용하여 프로젝트 파일을 로드합니다.`Project` 수업:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 2단계: 반복 작업 매개변수 정의

반복 작업에 대한 매개변수를 정의합니다.

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## 3단계: 달력 및 작업 시작 날짜 설정

작업의 달력과 시작 날짜를 설정합니다.

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## 결론

이 튜토리얼에서는 Aspose.Tasks for .NET을 활용하여 일일 작업 반복으로 반복 작업을 생성하는 방법을 살펴보았습니다. 다음 단계를 따르면 프로젝트 내의 작업을 효율적으로 관리하여 원활한 작업 흐름과 구성을 보장할 수 있습니다.

## FAQ

### Q1: 반복 패턴을 추가로 사용자 정의할 수 있나요?

A1: 예, 시작 날짜, 발생 횟수, 반복 간격 등의 매개변수를 조정하여 요구 사항에 따라 반복 패턴을 맞춤화할 수 있습니다.

### Q2: Aspose.Tasks는 다른 버전의 Microsoft Project와 호환됩니까?

A2: 예, Aspose.Tasks는 다양한 버전의 Microsoft Project를 지원하여 호환성과 원활한 통합을 보장합니다.

### Q3: 반복 작업에 대한 예외나 수정 사항을 어떻게 처리할 수 있나요?

A3: Aspose.Tasks는 반복 작업 내에서 예외 및 수정을 관리하는 강력한 기능을 제공하여 유연성과 사용자 정의를 허용합니다.

### Q4: 프로젝트를 다른 형식으로 내보낼 수 있나요?

A4: 물론입니다. Aspose.Tasks는 PDF, HTML, XML 등을 포함한 다양한 형식으로 프로젝트를 내보내는 기능을 지원하므로 쉽게 공유하고 협업할 수 있습니다.

### Q5: Aspose.Tasks는 기술 지원을 제공합니까?

A5: 예, Aspose.Tasks는 포럼을 통해 포괄적인 기술 지원을 제공합니다. 포럼에서 도움을 구하고, 경험을 공유하고, 동료 사용자와 소통할 수 있습니다.