---
title: Aspose.Tasks의 할당 기준선 수집
linktitle: Aspose.Tasks의 할당 기준선 수집
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET을 사용하여 프로젝트 관리에서 할당 기준선을 효율적으로 관리하는 방법을 알아보세요. 생산성과 정확성을 향상시킵니다.
type: docs
weight: 15
url: /ko/net/advanced-features/assignment-baseline-collection/
---
## 소개

프로젝트 관리 영역에서 할당 기준선을 추적하고 관리하는 것은 프로젝트 성공과 일정 준수를 보장하는 데 매우 중요합니다. Aspose.Tasks for .NET은 프로젝트 내에서 할당 기준선을 효율적으로 처리할 수 있는 강력한 기능 세트를 제공합니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 할당 기준 컬렉션 작업의 복잡성을 자세히 살펴보겠습니다.

## 전제조건

이 튜토리얼을 진행하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. C# 프로그래밍 언어에 대한 기본 지식.
2. 시스템에 Visual Studio가 설치되어 있습니다.
3.  .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).

## 네임스페이스 가져오기

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;


```

## 1단계: 프로젝트 파일 로드

먼저 할당 기준선이 포함된 프로젝트 파일을 로드해야 합니다.

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## 2단계: 할당 기준선 읽기

다음으로, 프로젝트의 각 리소스 할당을 반복하여 해당 기준선에 액세스합니다.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    var baselines = assignment.Baselines;
    Console.WriteLine("Count of assignment baselines: " + baselines.Count);
    Console.WriteLine("Parent Assignment: " + baselines.ParentAssignment);
    foreach (var baseline in baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
    }

    Console.WriteLine();
}
```

## 3단계: 발령 기준선 삭제

이 단계에서는 프로젝트에서 모든 할당 기준선을 삭제하는 방법을 보여줍니다.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    List<AssignmentBaseline> baselines = assignment.Baselines.ToList();
    foreach (var baseline in baselines)
    {
        assignment.Baselines.Remove(baseline);
    }
}
```

## 결론

할당 기준선의 효율적인 관리는 프로젝트 관리에서 가장 중요하며 일정 준수를 보장하고 프로젝트 진행 상황을 정확하게 추적합니다. .NET용 Aspose.Tasks를 사용하면 할당 기준 처리가 원활해지며 개발자에게 프로젝트 관리 프로세스를 간소화하는 데 필요한 도구가 제공됩니다.

## FAQ

### Q1: Aspose.Tasks는 다양한 프로젝트 파일 형식에 대한 할당 기준선을 처리할 수 있습니까?

A1: 예, Aspose.Tasks는 MPP, XML 및 MPX를 포함한 다양한 프로젝트 파일 형식을 지원하므로 다양한 파일 형식의 할당 기준선을 쉽게 관리할 수 있습니다.

### Q2: Aspose.Tasks는 모든 버전의 .NET Framework와 호환됩니까?

A2: Aspose.Tasks for .NET은 여러 버전의 .NET Framework와 호환되므로 다양한 환경에서 개발자에게 호환성과 유연성을 보장합니다.

### Q3: Aspose.Tasks를 사용하여 프로그래밍 방식으로 할당 기준선을 조작할 수 있습니까?

A3: 물론 Aspose.Tasks는 개발자가 프로젝트 요구 사항에 따라 할당 기준선을 프로그래밍 방식으로 생성, 읽기, 업데이트 및 삭제할 수 있는 포괄적인 API를 제공합니다.

### Q4: Aspose.Tasks는 개발자를 위한 기술 지원을 제공합니까?

A4: 예, Aspose.Tasks는 개발자가 도움을 구하고, 지식을 공유하고, 동료와 협력할 수 있는 커뮤니티 포럼을 통해 강력한 기술 지원을 제공합니다.

### Q5: 구매하기 전에 Aspose.Tasks를 사용해 볼 수 있나요?

A5: 예, Aspose.Tasks는 개발자가 구매 결정을 내리기 전에 기능을 탐색할 수 있도록 무료 평가판을 제공합니다.