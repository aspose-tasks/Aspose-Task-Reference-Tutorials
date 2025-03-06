---
title: Aspose.Tasks에서 연도별 반복
linktitle: Aspose.Tasks에서 연도별 반복
second_title: Aspose.태스크 .NET API
description: 반복 작업을 효율적으로 관리하는 데 있어 Aspose.Tasks for .NET의 강력한 기능을 살펴보세요. 연도 요일별 반복 기능 구현을 위한 단계별 가이드입니다.
weight: 28
url: /ko/net/advanced-features/repetition-by-year-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 연도별 반복

## 소개

프로젝트 관리 영역에서는 효율성과 정확성이 가장 중요합니다. Aspose.Tasks for .NET은 프로젝트 처리를 간소화하는 다양한 기능을 제공하는 강력한 도구로 등장합니다. 그 무기 중 하나는 놀라운 유연성으로 반복되는 작업을 관리하는 능력입니다. 그러한 기능 중 하나는 "연도별 반복, 요일별 반복" 기능으로, 사용자가 특정 요일, 지정된 달 내 및 여러 해에 걸쳐 반복되는 작업을 설정할 수 있습니다.

## 전제조건

.NET용 Aspose.Tasks의 "연도별 반복" 기능을 활용하는 복잡한 과정을 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### 1. .NET Framework에 대한 지식

개체 지향 프로그래밍 개념 및 C# 구문을 포함하여 .NET Framework의 기본 사항을 숙지하세요.

### 2. .NET용 Aspose.Tasks 설치

 다음에서 Aspose.Tasks for .NET 라이브러리를 다운로드하고 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/net/). 라이브러리를 개발 환경에 통합하려면 제공된 설치 지침을 따르십시오.

### 3. 문서에 대한 접근

 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/tasks/net/) 클래스, 메소드 및 사용 예제에 대한 자세한 설명을 포함하여 Aspose.Tasks for .NET에 대한 포괄적인 지침을 제공합니다.

## 4. 개발 환경 설정

Visual Studio 또는 .NET 개발용 호환 IDE와 같이 적합한 개발 환경이 구성되어 있는지 확인하세요.

이제 전제 조건이 준비되었으므로 .NET용 Aspose.Tasks에서 "연도별 반복" 구현에 대한 단계별 가이드를 살펴보겠습니다.


## 필요한 네임스페이스 가져오기

시작하려면 .NET 애플리케이션 내의 Aspose.Tasks 클래스 및 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

C# 코드 파일에 다음 네임스페이스 선언을 포함합니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

이러한 네임스페이스는 Aspose.Tasks 라이브러리와 작업 및 프로젝트 파일 작업에 필요한 클래스에 대한 액세스를 제공합니다.

이제 Aspose.Tasks for .NET의 "연도별 반복" 기능을 사용하여 반복 작업을 설정하는 과정을 관리 가능한 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 및 작업 매개변수 초기화

먼저 프로젝트를 초기화하고 반복 작업에 대한 매개변수를 정의합니다.

```csharp
// 문서 디렉터리의 경로입니다.
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

이 코드 세그먼트는 새 프로젝트를 초기화하고 반복 작업에 대한 매개변수를 지정합니다. 작업 이름, 기간을 설정하고 반복 패턴을 정의합니다.

## 2단계: 프로젝트에 매개변수 추가

다음으로 정의된 매개변수를 프로젝트에 추가합니다.

```csharp
project.RootTask.Children.Add(parameters);
```

이 줄은 반복 작업 구성을 통합하여 프로젝트의 루트 작업에 작업 매개변수를 추가합니다.

## 3단계: 프로젝트 파일 저장

마지막으로 구성된 반복 작업이 포함된 프로젝트 파일을 저장합니다.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

이 조각은 지정된 반복 작업 구성이 포함된 프로젝트 파일을 지정된 출력 디렉터리에 저장합니다.

## 결론

결론적으로 Aspose.Tasks for .NET의 "연도별 반복" 기능을 마스터하면 프로젝트 관리자와 개발자가 반복 작업을 정확하고 유연하게 효율적으로 처리할 수 있습니다. 이 문서에 설명된 단계별 가이드를 따르면 이 기능을 프로젝트 관리 워크플로에 원활하게 통합하여 생산성과 구성을 향상할 수 있습니다.

## FAQ

### Q1: 제공된 예시보다 더 나아가 반복 패턴을 사용자 정의할 수 있나요?

A: 예, .NET용 Aspose.Tasks는 반복 작업에 대한 광범위한 사용자 정의 옵션을 제공하므로 특정 요구 사항에 맞게 반복 패턴을 조정할 수 있습니다.

### Q2: Aspose.Tasks for .NET은 다른 프로젝트 관리 소프트웨어와 호환됩니까?

A: Aspose.Tasks for .NET은 다양한 프로젝트 관리 형식과의 상호 운용성을 지원하여 널리 사용되는 소프트웨어 제품군과의 원활한 통합을 가능하게 합니다.

### Q3: 반복 작업에 대한 예외나 수정 사항을 어떻게 처리할 수 있나요?

A: Aspose.Tasks for .NET은 반복 작업에 대한 예외 및 수정을 처리하는 API를 제공하여 진화하는 프로젝트 요구 사항을 관리하는 데 유연성을 보장합니다.

### Q4: Aspose.Tasks for .NET은 클라우드 기반 프로젝트 관리 솔루션을 지원합니까?

A: 예, Aspose.Tasks for .NET은 클라우드 기반 프로젝트 관리 솔루션을 지원하여 다양한 플랫폼에서 협업과 접근성을 촉진합니다.

### Q5: Aspose.Tasks for .NET에 사용할 수 있는 평가판이 있습니까?

A: 예, 다음에서 .NET용 Aspose.Tasks 무료 평가판에 액세스할 수 있습니다.[웹사이트](https://releases.aspose.com/), 구매 결정을 내리기 전에 기능을 탐색할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
