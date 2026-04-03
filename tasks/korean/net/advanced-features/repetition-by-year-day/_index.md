---
date: 2026-04-03
description: Aspose.Tasks for .NET를 사용한 프로젝트 관리 작업 일정 수립 및 반복 작업 추가 방법을 배우고, 프로젝트를
  MPP 형식으로 저장하는 방법을 포함합니다.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Aspose.Tasks에서 연도 일자별 반복
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 연도 일 반복을 사용한 프로젝트 관리 작업 일정
url: /ko/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 연도 일 반복을 사용한 프로젝트 관리 작업 일정

## 소개

효과적인 **project management task scheduling**은 모든 성공적인 프로젝트의 핵심입니다. 작업이 매년 반복될 때—예를 들어 연간 감사, 유지 보수 기간, 혹은 계절별 검토—이러한 반복을 수동으로 처리하면 오류가 발생하기 쉽고 시간이 많이 소요됩니다. Aspose.Tasks for .NET은 연도 일 패턴을 프로그래밍 방식으로 정의할 수 있게 하여 이를 간소화하므로 가장 중요한 일, 즉 가치를 제공하는 일에 집중할 수 있습니다. 이 튜토리얼에서는 연도 특정 일에 기반한 **how to add recurring task** 로직을 배우고 Microsoft Project와 원활히 통합하기 위해 **how to save project as MPP** 를 정확히 확인하게 됩니다.

## 빠른 답변
- **What does “year day repetition” mean?** 연도 일 반복은 매년 특정 월의 특정 일에 작업을 예약하는 것입니다.  
- **Which API class creates the recurrence?** `YearlyRecurrencePattern`와 `ByYearDayRepetition`을 결합합니다.  
- **Can I set a start and end date?** 예, `EndByRecurrenceRange`를 사용합니다.  
- **What file format is produced?** 프로젝트가 MPP 파일(`SaveFileFormat.Mpp`)로 저장됩니다.  
- **Do I need a license for production?** 비평가용이 아닌 경우 상업용 라이선스가 필요합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 준비되어 있는지 확인하십시오:

1. Aspose.Tasks for .NET 라이브러리: [website](https://releases.aspose.com/tasks/net/)에서 Aspose.Tasks for .NET 라이브러리를 다운로드하고 설치합니다.  
2. 개발 환경: Visual Studio 또는 .NET 개발에 선호하는 다른 IDE를 사용하여 적절한 개발 환경을 설정합니다.  
3. C# 기본 지식: 코드 예제를 따라가기 위해 C# 프로그래밍 언어 기본을 숙지합니다.  
4. 프로젝트 관리 개념: 프로젝트 관리 개념 및 작업 일정에 대한 이해가 튜토리얼 내용을 효과적으로 파악하는 데 도움이 됩니다.

## 네임스페이스 가져오기

코딩을 시작하기 전에 Aspose.Tasks for .NET을 사용하여 작업 조작을 용이하게 할 필요한 네임스페이스를 가져오겠습니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

이제 제공된 예제를 여러 단계로 나누어 각 단계를 자세히 설명하겠습니다.

## 연도 일 패턴으로 반복 작업 추가 방법

### 단계 1: 프로젝트 파일 로드

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

여기서는 새로운 `Project` 객체를 초기화하고 **Project1.mpp**라는 기존 프로젝트 파일을 로드합니다.

### 단계 2: 반복 작업 매개변수 정의

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

이 단계에서는 반복 작업의 매개변수를 정의합니다. 작업 이름, 기간 및 반복 패턴을 지정합니다. 연간 반복의 경우 `YearlyRecurrencePattern`을 사용하고 `ByYearDayRepetition`을 이용해 **7월 1일**에 반복되도록 설정합니다. 또한 반복 범위를 2018년 7월 1일부터 2019년 7월 1일까지 정의합니다.

### 단계 3: 작업을 프로젝트에 추가

```csharp
project.RootTask.Children.Add(parameters);
```

여기서는 정의된 반복 작업 매개변수를 프로젝트의 루트 작업에 추가합니다.

### 단계 4: 프로젝트를 MPP로 저장

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

마지막으로 **프로젝트를 MPP 파일로 저장**하여 Microsoft Project 또는 호환 뷰어에서 열 수 있도록 합니다.

## 이것이 중요한 이유

- **Automation** – 연간 작업의 수동 입력을 없애 인적 오류를 줄입니다.  
- **Consistency** – 동일한 일‑월 패턴이 여러 해에 걸쳐 적용됨을 보장합니다.  
- **Integration** – 생성된 MPP 파일을 Microsoft Project에 의존하는 이해관계자와 공유할 수 있습니다.

## 일반적인 함정 및 팁

- **DateTime precision** – 시작 시간이 프로젝트 캘린더와 일치하도록 확인하십시오. 그렇지 않으면 작업이 위치가 어긋나 보일 수 있습니다.  
- **Time zones** – API는 `DateTime` 객체와 함께 작동하므로 애플리케이션이 여러 지역에 걸쳐 있는 경우 UTC 변환을 고려하십시오.  
- **License enforcement** – 평가 모드에서는 저장된 MPP에 워터마크가 포함될 수 있으니, 프로덕션에서는 유효한 라이선스를 사용하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks가 복잡한 반복 패턴을 처리할 수 있나요?**  
A: 예, Aspose.Tasks는 연간, 월간, 주간 및 일간 반복을 포함한 다양한 반복 패턴에 대한 포괄적인 지원을 제공합니다.

**Q: Aspose.Tasks가 다양한 프로젝트 파일 형식과 호환되나요?**  
A: 물론입니다. Aspose.Tasks는 MPP, XML, CSV와 같은 인기 있는 프로젝트 파일 형식을 지원하여 다양한 프로젝트 관리 도구와의 호환성을 보장합니다.

**Q: Aspose.Tasks가 개발자를 위한 문서와 지원을 제공하나요?**  
A: 예, 개발자는 방대한 문서에 접근할 수 있으며, 발생하는 질문이나 문제에 대해 Aspose.Tasks 커뮤니티 포럼에서 도움을 받을 수 있습니다.

**Q: Aspose.Tasks를 사용해 작업 기간 및 시작 날짜와 같은 작업 속성을 사용자 정의할 수 있나요?**  
A: 물론입니다. Aspose.Tasks는 작업 속성을 동적으로 조작할 수 있는 강력한 API를 제공하여 개발자가 기간, 시작 날짜, 종속성 등을 맞춤 설정할 수 있게 합니다.

**Q: Aspose.Tasks가 소규모와 엔터프라이즈 수준 프로젝트 모두에 적합한가요?**  
A: 네, Aspose.Tasks는 개별 작업부터 대규모 엔터프라이즈 프로젝트까지 모든 규모의 프로젝트에 종사하는 개발자의 요구를 충족하도록 설계되었습니다.

---

**마지막 업데이트:** 2026-04-03  
**테스트 환경:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}