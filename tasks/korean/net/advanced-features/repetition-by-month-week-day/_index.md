---
title: Aspose.Tasks에서 월 요일별 반복
linktitle: Aspose.Tasks에서 월 요일별 반복
second_title: Aspose.태스크 .NET API
description: 반복 작업을 효율적으로 자동화하기 위해 Aspose.Tasks for .NET에서 월, 주, 일 단위로 반복을 설정하는 방법을 알아보세요.
weight: 26
url: /ko/net/advanced-features/repetition-by-month-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 월 요일별 반복

## 소개

소프트웨어 개발 영역, 특히 프로젝트 관리 애플리케이션에서는 반복 작업을 효율적으로 처리하는 능력이 가장 중요합니다. Aspose.Tasks for .NET은 반복 작업을 포함하여 프로젝트 작업의 생성 및 관리를 간소화하도록 설계된 강력한 라이브러리입니다. Aspose.Tasks가 제공하는 기능 중 하나는 월, 주, 일별로 반복을 설정하여 수동 개입 없이 일정에 따라 작업이 실행되도록 하는 기능입니다.

## 전제조건

.NET용 Aspose.Tasks를 사용하여 월, 주, 일별 반복 설정의 복잡성을 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. C#에 대한 기본 이해: 제공된 코드 예제를 이해하고 구현하려면 C# 프로그래밍 언어에 대한 지식이 필수적입니다.
   
2.  .NET용 Aspose.Tasks 설치: .NET용 Aspose.Tasks 라이브러리를 다운로드하여 설치했는지 확인하세요. 도서관에서 도서관을 구할 수 있습니다.[다운로드 페이지](https://releases.aspose.com/tasks/net/).

3. .mpp 프로젝트 파일에 액세스: Microsoft Project 파일(.mpp)을 준비합니다. 월별, 주별, 일별 반복 구현을 보여주기 위해 이 파일을 활용할 것입니다.

## 네임스페이스 가져오기

C# 애플리케이션에서 Aspose.Tasks for .NET 활용을 시작하려면 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

각 부분을 철저하게 이해하기 위해 제공된 코드 조각을 여러 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 파일 로드

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 이 단계에는 다음의 새 인스턴스를 만드는 작업이 포함됩니다.`Project` 클래스를 생성하고 기존 Microsoft Project 파일을 로드합니다(`Project1.mpp`) 지정된 디렉토리에서.

## 2단계: 반복 작업 매개변수 정의

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

이 단계에서는 반복 작업에 대한 매개변수를 정의합니다. 작업 이름, 기간, 반복 패턴(월별), 반복 범위(특정 날짜까지 종료)를 지정합니다.

## 3단계: 프로젝트에 반복 작업 추가

```csharp
project.RootTask.Children.Add(parameters);
```

여기서는 정의된 반복 작업 매개변수를 프로젝트의 루트 작업에 추가합니다.

## 4단계: 프로젝트 파일 저장

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

마지막으로 반복 작업이 추가된 수정된 프로젝트 파일을 저장합니다.

## 결론

결론적으로 Aspose.Tasks for .NET에서 월, 주, 일 단위로 반복을 설정하는 것은 개발자가 프로젝트 내에서 반복 작업 관리를 효율적으로 자동화할 수 있는 간단한 프로세스입니다. 이 자습서에 설명된 단계를 따르면 이 기능을 C# 애플리케이션에 원활하게 통합하여 프로젝트 관리에 드는 시간과 노력을 절약할 수 있습니다.

## FAQ

###Q1: 제공된 예시 외에 반복 패턴을 맞춤설정할 수 있나요?

A1: 예, .NET용 Aspose.Tasks는 반복 패턴에 대한 광범위한 사용자 정의 옵션을 제공하므로 이를 특정 요구 사항에 맞게 조정할 수 있습니다.

###Q2: Aspose.Tasks for .NET에 사용할 수 있는 평가판이 있습니까?

 A2: 예, 다음 사이트에서 Aspose.Tasks for .NET 무료 평가판을 얻을 수 있습니다.[릴리스 페이지](https://releases.aspose.com/).

###Q3: .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?

 답변 3: 다음을 통해 도움을 구하고 커뮤니티에 참여할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).

###Q4: Aspose.Tasks for .NET에 임시 라이선스를 사용할 수 있나요?

 A4: 네, 임시 라이선스는 다음 사이트에서 취득할 수 있습니다.[구매 페이지](https://purchase.aspose.com/temporary-license/) 테스트 및 평가 목적으로.

###Q5: .NET용 Aspose.Tasks에 대한 포괄적인 문서는 어디에서 찾을 수 있나요?

 A5: 자세한 내용을 참조할 수 있습니다.[선적 서류 비치](https://reference.aspose.com/tasks/net/) 라이브러리 활용에 대한 자세한 지침은 Aspose 웹사이트에서 확인할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
