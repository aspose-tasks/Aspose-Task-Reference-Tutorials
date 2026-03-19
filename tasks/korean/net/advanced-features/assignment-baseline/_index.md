---
date: 2026-03-19
description: Aspose.Tasks for .NET를 사용하여 프로젝트 기준선을 설정하고 할당 기준선을 효율적으로 관리하는 방법을 배우고,
  프로젝트 진행 상황을 정확하게 추적하세요.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 프로젝트 기준선 설정 – Aspose.Tasks에서 할당 기준선 관리
url: /ko/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 기준선 설정 – Aspose.Tasks에서 할당 기준선 관리

## Introduction

프로젝트 관리 작업을 수행할 때, **프로젝트 기준선을 설정**하는 것은 실제 진행 상황을 원래 계획과 비교하는 데 필수적입니다. .NET용 Aspose.Tasks는 **프로젝트 기준선을 설정**할 수 있을 뿐만 아니라 할당 기준선에 대한 완전한 제어를 제공하여 정확한 성과 추적을 가능하게 합니다. 이 튜토리얼에서는 프로젝트 로드, 기준선 설정, 할당 기준선 데이터 읽기 및 기준선 비교 전체 과정을 단계별로 안내하므로 프로젝트를 자신 있게 모니터링할 수 있습니다.

## Quick Answers
- **“set project baseline”는 무엇을 의미하나요?** 원래 일정 및 비용 데이터를 기록하여 실제 성과와 나중에 비교할 수 있게 합니다.  
- **어떤 API 메서드가 기준선을 설정하나요?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **할당 기준선에 별도의 호출이 필요합니까?** 아니요, 프로젝트 기준선을 설정하면 자동으로 저장됩니다.  
- **지원되는 형식은 무엇인가요?** MPP, XML, MPX 등 Aspose.Tasks를 통해 다양한 형식을 지원합니다.  
- **프로덕션에서 라이선스가 필요합니까?** 예, 비시험용으로는 상용 라이선스가 필요합니다.

## Prerequisites

시작하기 전에 다음이 준비되어 있는지 확인하세요:

- C# 프로그래밍에 대한 기본 지식.  
- Visual Studio (최근 버전 중 하나).  
- 프로젝트에 추가된 Aspose.Tasks for .NET 라이브러리. 다운로드는 [here](https://releases.aspose.com/tasks/net/)에서 가능합니다.  
- MPP 형식의 프로젝트 파일에 대한 접근 권한 (예: `AssignmentBaseline2007.mpp`).

## Import Namespaces

컴파일러가 Aspose.Tasks 클래스를 찾을 수 있도록 C# 파일 상단에 필요한 네임스페이스를 추가합니다.

```csharp
using Aspose.Tasks;
using System;
```

## Step 1: Load Project and Set Project Baseline

먼저 기존 MPP 파일을 로드한 다음 `SetBaseline`을 호출하여 전체 프로젝트에 **프로젝트 기준선을 설정**합니다.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Step 2: Read Assignment Baseline Information

기준선을 설정한 후에는 각 리소스 할당에 자체 기준선 레코드가 포함됩니다. 아래 루프는 시작/종료 날짜, 비용, 작업량 및 시간 구간 데이터 등을 추출하여 출력합니다.

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

## Step 3: Compare Assignment Baselines

내장된 등호 및 비교 연산자를 사용하여 서로 다른 할당의 기준선을 비교할 수 있습니다. 이는 작업 간 일정 변동이나 비용 초과를 감지해야 할 때 유용합니다.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Common Issues and Solutions

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Baseline data appears empty** | 프로젝트 파일이 읽기 전용 모드로 열렸거나 기준선이 설정되지 않았습니다. | 할당 기준선을 읽기 전에 `project.SetBaseline(BaselineType.Baseline)`을 호출하세요. |
| **`NullReferenceException` on `TimephasedData`** | 모든 기준선에 시간 구간 데이터가 포함된 것은 아닙니다. | 코드에 표시된 대로 `baseline.TimephasedData != null`을 항상 확인하세요. |
| **Incorrect UID retrieval** | 파일 버전마다 UID 값이 다를 수 있습니다. | 올바른 UID를 사용해 `ResourceAssignments.GetByUid`를 호출하거나 할당을 찾아 반복하세요. |

## Frequently Asked Questions

**Q: Aspose.Tasks가 단일 할당에 대해 여러 기준선을 처리할 수 있나요?**  
A: 예, Aspose.Tasks는 각 할당에 대해 여러 기준선을 지원하므로 프로젝트 진행 상황을 시간에 따라 포괄적으로 추적할 수 있습니다.

**Q: Aspose.Tasks가 MPP 외의 다양한 프로젝트 파일 형식을 지원하나요?**  
A: 예, Aspose.Tasks는 XML, MPX, MPP 등 다양한 프로젝트 파일 형식을 지원하여 여러 프로젝트 관리 도구와 호환됩니다.

**Q: Aspose.Tasks를 사용해 프로그램matically 기준선 정보를 수정할 수 있나요?**  
A: 물론입니다. Aspose.Tasks는 프로젝트 요구 사항에 따라 기준선 정보를 동적으로 수정할 수 있는 풍부한 API를 제공하여 유연하고 강력한 관리가 가능합니다.

**Q: Aspose.Tasks가 개발자를 위한 문서 및 지원 리소스를 제공하나요?**  
A: 예, 개발자는 Aspose.Tasks 웹사이트에서 포괄적인 문서, 튜토리얼 및 포럼을 이용할 수 있어 원활한 통합과 문제 해결이 가능합니다.

**Q: Aspose.Tasks for .NET의 체험판 버전이 있나요?**  
A: 예, 개발자는 [here](https://releases.aspose.com/)에서 Aspose.Tasks for .NET 무료 체험판을 받아 기능과 성능을 평가한 후 구매 결정을 내릴 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

---