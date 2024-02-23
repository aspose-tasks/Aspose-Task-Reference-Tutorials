---
title: Aspose.Tasks에서 할당 기준선 관리
linktitle: Aspose.Tasks에서 할당 기준선 관리
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET을 사용하여 할당 기준선을 효율적으로 관리하여 프로젝트 진행 상황과 성과를 정확하게 추적하는 방법을 알아보세요.
type: docs
weight: 14
url: /ko/net/advanced-features/assignment-baseline/
---
## 소개

프로젝트 관리 작업을 수행할 때 할당 기준선을 관리하는 것은 정확한 진행 상황을 추적하는 데 중요합니다. Aspose.Tasks for .NET은 할당 기준선을 효율적으로 처리하기 위한 포괄적인 도구 세트를 제공합니다. 이 자습서에서는 할당 기준선을 관리하는 프로세스를 단계별로 살펴보겠습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 Visual Studio가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.Tasks가 프로젝트에 추가되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
- MPP 형식의 프로젝트 파일에 액세스합니다.

## 네임스페이스 가져오기

Aspose.Tasks 작업을 시작하려면 필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다. C# 파일 시작 부분에 다음 네임스페이스를 추가합니다.

```csharp
using Aspose.Tasks;
using System;


```

## 1단계: 프로젝트 로드 및 기준선 설정

 먼저, 다음을 사용하여 프로젝트 파일을 로드합니다.`Project` Aspose.Tasks의 클래스입니다. 그런 다음 다음을 사용하여 프로젝트의 기준선 유형을 설정합니다.`SetBaseline` 방법.

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## 2단계: 할당 기준 정보 읽기

프로젝트의 각 자원 할당을 반복하고 각 할당에 대한 기준 정보를 검색합니다.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## 3단계: 기준선 동등성 확인

Aspose.Tasks에서 제공하는 다양한 비교 방법을 사용하여 다양한 과제에 대한 기준 정보를 비교하세요.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// 기준선 동등성 확인
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// 기준 비교 확인
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// 기준 해시코드 표시
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## 결론

할당 기준선 관리는 프로젝트 관리에 필수적이므로 진행 상황과 성과를 정확하게 추적할 수 있습니다. .NET용 Aspose.Tasks를 사용하면 할당 기준선 처리가 간소화되고 효율적이 되어 개발자에게 프로젝트 관리 워크플로우를 향상시키는 강력한 도구를 제공합니다.

## FAQ

### Q1: Aspose.Tasks는 단일 할당에 대해 여러 기준을 처리할 수 있습니까?

A1: 예, Aspose.Tasks는 각 과제에 대해 여러 기준을 지원하므로 시간 경과에 따른 프로젝트 진행 상황을 포괄적으로 추적할 수 있습니다.

### Q2: Aspose.Tasks는 MPP 이외의 다양한 프로젝트 파일 형식과 호환됩니까?

A2: 예, Aspose.Tasks는 XML, MPX 및 MPP를 포함한 광범위한 프로젝트 파일 형식을 지원하여 다양한 프로젝트 관리 도구와의 호환성을 보장합니다.

### Q3: Aspose.Tasks를 사용하여 프로그래밍 방식으로 기본 정보를 수정할 수 있나요?

A3: 물론 Aspose.Tasks는 프로젝트 요구 사항에 따라 기본 정보를 동적으로 수정할 수 있는 광범위한 API를 제공하여 프로젝트 관리 프로세스에 대한 유연성과 제어 기능을 제공합니다.

### Q4: Aspose.Tasks는 개발자를 위한 문서 및 지원 리소스를 제공합니까?

A4: 예, 개발자는 Aspose.Tasks 웹사이트에서 포괄적인 문서, 튜토리얼 및 포럼에 액세스하여 원활한 통합 및 문제 해결을 촉진할 수 있습니다.

### Q5: Aspose.Tasks for .NET에 사용할 수 있는 평가판이 있습니까?

 A5: 예, 개발자는 다음에서 .NET용 Aspose.Tasks의 무료 평가판을 얻을 수 있습니다.[여기](https://releases.aspose.com/), 구매 결정을 내리기 전에 기능을 평가할 수 있습니다.