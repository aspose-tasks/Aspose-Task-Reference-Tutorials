---
title: Aspose.Tasks에서 연도별 반복
linktitle: Aspose.Tasks에서 연도별 반복
second_title: Aspose.태스크 .NET API
description: 반복 작업 관리를 효율적으로 간소화하기 위해 .NET용 Aspose.Tasks에서 연간 반복을 처리하는 방법을 알아보세요.
weight: 27
url: /ko/net/advanced-features/repetition-by-year-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 연도별 반복

## 소개

프로젝트 관리 영역에서 효율적인 작업 예약 및 반복은 적시 실행과 원활한 작업 흐름을 보장하는 데 중추적인 역할을 합니다. Aspose.Tasks for .NET은 개발자가 애플리케이션 내에서 반복되는 작업을 쉽게 처리할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 연도별 반복 작업의 복잡성을 탐구하고 연간 패턴을 기반으로 반복 작업을 생성하기 위한 포괄적인 가이드를 제공합니다.

## 전제조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET 라이브러리용 Aspose.Tasks: 다음에서 .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치하세요.[웹사이트](https://releases.aspose.com/tasks/net/).
   
2. 개발 환경: Visual Studio 또는 .NET 개발을 위해 선호하는 기타 IDE를 사용하여 적합한 개발 환경을 설정합니다.

3. C# 기본 지식: 코드 예제를 따라가려면 C# 프로그래밍 언어 기본 사항을 숙지하세요.

4. 프로젝트 관리 개념: 프로젝트 관리 개념과 작업 일정을 이해하면 튜토리얼 개념을 효과적으로 이해하는 데 도움이 됩니다.

## 네임스페이스 가져오기

코딩을 시작하기 전에 Aspose.Tasks for .NET을 사용하여 작업 조작을 용이하게 하는 데 필요한 네임스페이스를 가져와 보겠습니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

이제 제공된 예제를 여러 단계로 나누고 각 단계를 자세히 설명하겠습니다.

## 1단계: 프로젝트 파일 로드

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 여기서는 새로운 것을 초기화합니다.`Project` 개체를 만들고 "Project1.mpp"라는 기존 프로젝트 파일을 로드합니다.

## 2단계: 반복 작업 매개변수 정의

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

 이 단계에서는 반복 작업에 대한 매개변수를 정의합니다. 작업 이름, 기간, 반복 패턴을 지정합니다. 매년 반복되는 경우에는 다음을 사용합니다.`YearlyRecurrencePattern` 다음을 사용하여 7월 1일에 반복이 발생하도록 설정합니다.`ByYearDayRepetition`. 또한 2018년 7월 1일부터 2019년 7월 1일까지 반복 범위를 정의합니다.

## 3단계: 프로젝트에 작업 추가

```csharp
project.RootTask.Children.Add(parameters);
```

여기서는 정의된 반복 작업 매개변수를 프로젝트의 루트 작업에 추가합니다.

## 4단계: 프로젝트 저장

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

마지막으로 반복 작업이 추가된 수정된 프로젝트 파일을 저장합니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 연도별 반복 작업 프로세스를 살펴보았습니다. 제공된 단계를 따르면 개발자는 반복 작업 기능을 애플리케이션에 원활하게 통합하여 프로젝트 관리 기능을 향상시킬 수 있습니다.

## FAQ

### Q1: Aspose.Tasks가 복잡한 반복 패턴을 처리할 수 있나요?

A1: 예, Aspose.Tasks는 연간, 월간, 주간 및 일일 반복과 같은 복잡한 패턴을 포함하여 다양한 반복 패턴에 대한 포괄적인 지원을 제공합니다.

### Q2: Aspose.Tasks는 다른 프로젝트 파일 형식과 호환됩니까?

A2: 물론 Aspose.Tasks는 MPP, XML 및 CSV와 같은 널리 사용되는 프로젝트 파일 형식을 지원하여 다양한 프로젝트 관리 도구 간의 호환성을 보장합니다.

### Q3: Aspose.Tasks는 개발자를 위한 문서와 지원을 제공합니까?

A3: 예, 개발자는 광범위한 문서에 액세스하고 Aspose.Tasks 커뮤니티 포럼에서 발생한 질문이나 문제에 대한 지원을 구할 수 있습니다.

### Q4: Aspose.Tasks를 사용하여 기간 및 시작 날짜와 같은 작업 속성을 사용자 지정할 수 있나요?

A4: 확실히 Aspose.Tasks는 작업 속성을 동적으로 조작할 수 있는 강력한 API를 제공하므로 개발자는 기간, 시작 날짜, 종속성 등을 사용자 정의할 수 있습니다.

### Q5: Aspose.Tasks는 소규모 및 기업 수준 프로젝트 모두에 적합합니까?

A5: 실제로 Aspose.Tasks는 개별 작업부터 대규모 기업 프로젝트에 이르기까지 모든 규모의 프로젝트에서 작업하는 개발자의 요구를 충족하도록 설계되었습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
