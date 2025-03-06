---
title: Aspose.Tasks에서 월별 반복
linktitle: Aspose.Tasks에서 월별 반복
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks를 사용하여 .NET 프로젝트에서 반복되는 작업을 관리하는 방법을 알아보세요. 월별 반복 처리를 위한 단계별 안내입니다.
type: docs
weight: 25
url: /ko/net/advanced-features/repetition-by-month-day/
---
## 소개

.NET 개발 영역에서 Aspose.Tasks는 프로젝트 작업 및 일정을 관리하기 위한 강력한 도구입니다. 반복되는 작업 처리를 포함하여 프로젝트 관리 워크플로를 간소화하는 다양한 기능을 제공합니다. 월별 반복은 프로젝트 일정의 일반적인 요구 사항이며 Aspose.Tasks는 이 시나리오에 대한 강력한 지원을 제공합니다.

## 전제조건

튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.

1. C#에 대한 기본 이해: 이 자습서에서 설명하는 개념을 이해하려면 C# 프로그래밍 언어에 대한 지식이 필요합니다.
2. .NET용 Aspose.Tasks 설치: .NET용 Aspose.Tasks를 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
3. 통합 개발 환경(IDE): 코딩 편의를 위해 Visual Studio와 같은 IDE를 시스템에 설치합니다.

## 네임스페이스 가져오기

C# 프로젝트에서 Aspose.Tasks 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

제공된 코드 예제를 단계별 가이드 형식으로 분석해 보겠습니다.

## 1단계: 프로젝트 파일 로드

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 이 코드 줄은`Project` 클래스, "Project1.mpp"라는 프로젝트 파일을 로드합니다.

## 2단계: 반복 작업 매개변수 정의

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

이 섹션에서는 이름, 기간, 반복 패턴 및 반복 범위를 포함하여 반복 작업에 대한 매개변수를 정의합니다.

## 3단계: 프로젝트에 작업 추가

```csharp
project.RootTask.Children.Add(parameters);
```

여기서는 프로젝트에 반복 작업 매개변수를 추가합니다.

## 4단계: 프로젝트 파일 저장

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

마지막으로 수정된 프로젝트가 추가된 반복 작업과 함께 저장됩니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 월별 반복을 처리하는 방법을 살펴보았습니다. 제공된 단계를 따르면 프로젝트 일정 내에서 반복되는 작업을 효율적으로 관리할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks는 모든 버전의 .NET과 호환됩니까?

A1: Aspose.Tasks는 다양한 버전의 .NET 프레임워크를 지원하여 다양한 환경 간의 호환성을 보장합니다.

### Q2: 반복 패턴을 추가로 사용자 정의할 수 있나요?

A2: 예, Aspose.Tasks는 특정 프로젝트 요구 사항에 따라 반복 패턴을 정의하기 위한 광범위한 사용자 정의 옵션을 제공합니다.

### Q3: Aspose.Tasks는 다른 프로젝트 관리 기능을 지원합니까?

A3: 물론 Aspose.Tasks는 작업 추적, 리소스 할당 및 간트 차트 생성을 포함하여 프로젝트 관리를 위한 광범위한 기능을 제공합니다.

### Q4: Aspose.Tasks에 사용할 수 있는 평가판이 있습니까?

 A4: 예, 다음에서 무료 평가판을 이용하실 수 있습니다.[여기](https://releases.aspose.com/) 구매 결정을 내리기 전에 Aspose.Tasks의 기능을 살펴보세요.

### Q5: 문제가 발생하거나 문의사항이 있는 경우 어디서 도움을 받을 수 있나요?

 A5: 다음을 방문할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티나 Aspose 팀의 지원을 구합니다.