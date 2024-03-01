---
title: Aspose.Tasks에서 가용성 기간 작업
linktitle: Aspose.Tasks에서 가용성 기간 작업
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET을 사용하여 리소스 가용성 기간을 효율적으로 관리하는 방법을 알아보세요. 이 자습서에서는 .NET 프로젝트의 가용성 기간 작업에 대한 단계별 가이드를 제공합니다.
type: docs
weight: 17
url: /ko/net/advanced-features/working-with-availability-periods/
---
## 소개

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 가용성 기간을 사용하는 방법을 살펴보겠습니다. 프로젝트 관리 시나리오에서 자원을 효율적으로 관리하려면 가용성 기간이 중요합니다. 프로세스를 단계별로 안내해 드리겠습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Visual Studio: Visual Studio 또는 .NET 개발을 위해 선호하는 기타 IDE를 설치합니다.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C# 프로그래밍에 대한 기본 이해: C# 프로그래밍 언어 기본 사항에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기

코드를 살펴보기 전에 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

예제 코드를 여러 단계로 나누어 보겠습니다.

## 1단계: 새 프로젝트 인스턴스 만들기

```csharp
var project = new Project();
```

이 줄은 Aspose.Tasks의 프로젝트를 나타내는 Project 클래스의 새 인스턴스를 초기화합니다.

## 2단계: 리소스 추가

```csharp
var resource = project.Resources.Add("Work Resource");
```

여기서는 "Work Resource"라는 이름으로 프로젝트에 새 리소스를 추가합니다.

## 3단계: 가용성 기간 정의

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 우리는`GetPeriods()` 가용성 기간 모음을 검색하는 방법입니다.

## 4단계: 리소스에 가용성 기간 추가

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

이전 단계에서 얻은 가용성 기간 수집을 반복하여 리소스에 추가합니다.

## 5단계: 가용성 기간 세부 정보 표시

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

마지막으로 리소스와 관련된 가용성 기간을 반복하고 시작 날짜, 종료 날짜 및 사용 가능한 단위를 포함한 세부 정보를 인쇄합니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 가용성 기간을 사용하는 방법을 배웠습니다. 단계별 가이드를 따르면 프로젝트 관리 애플리케이션에서 리소스 가용성을 효율적으로 관리할 수 있습니다.

## FAQ

### Q1: 상업용 프로젝트에서 .NET용 Aspose.Tasks를 사용할 수 있습니까?

 A1: 예, .NET용 Aspose.Tasks는 상용 프로젝트에서 사용할 수 있습니다. 라이센스를 구매하실 수 있습니다[여기](https://purchase.aspose.com/buy).

### Q2: Aspose.Tasks for .NET에 사용할 수 있는 무료 평가판이 있습니까?

A2: 예, .NET용 Aspose.Tasks 무료 평가판을 얻을 수 있습니다.[여기](https://releases.aspose.com/).

### Q3: .NET용 Aspose.Tasks에 대한 설명서는 어디에서 찾을 수 있습니까?

 A3: 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).

### Q4: .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?

 A4: 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).

### Q5: Aspose.Tasks for .NET에 대한 임시 라이선스를 제공합니까?

 A5: 예, 임시 라이센스를 사용할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).