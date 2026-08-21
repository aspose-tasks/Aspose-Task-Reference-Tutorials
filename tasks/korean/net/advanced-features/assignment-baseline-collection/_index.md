---
date: 2026-03-19
description: Aspose.Tasks for .NET를 사용하여 기준선을 읽고 프로젝트 관리 기준선을 효율적으로 관리하는 방법을 배워보세요.
linktitle: Project Management Baselines using Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks를 사용한 프로젝트 관리 기준선
url: /ko/net/advanced-features/assignment-baseline-collection/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 이용한 프로젝트 관리 베이스라인

## 소개

## 빠른 답변
- **할당 베이스라인의 주요 목적은 무엇입니까?** 각 리소스 할당에 대한 계획된 시작/완료 날짜를 캡처합니다.  
- **어떤 API 메서드가 베이스라인을 읽습니까?** `Assignment.Baselines` 컬렉션.  
- **베이스라인을 프로그래밍 방식으로 삭제할 수 있습니까?** 예, `Assignment.Baselines` 컬렉션에서 항목을 제거함으로써 가능합니다.  
- **이 기능을 사용하려면 라이선스가 필요합니까?** 프로덕션 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **.NET 버전 지원은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## 프로젝트 관리 베이스라인이란?

프로젝트 관리 베이스라인은 일정, 비용 및 범위 데이터의 특정 시점 스냅샷입니다. 이는 프로젝트 성과를 측정하고 프로젝트 수명 주기 전반에 걸쳐 차이를 식별하기 위한 기준점으로 사용됩니다.

## 왜 프로젝트 관리 베이스라인에 Aspose.Tasks를 사용합니까?

- **전체 제어:** Microsoft Project를 열지 않고도 베이스라인 데이터를 액세스하고 조작할 수 있습니다.  
- **자동화 준비:** 베이스라인 처리를 CI/CD 파이프라인이나 보고 도구에 통합할 수 있습니다.  
- **다중 포맷 지원:** MPP, XML, MPX 파일과 작동하여 다양한 프로젝트 파일 형식에 대한 유연성을 보장합니다.  

## 전제 조건

이 튜토리얼을 진행하기 전에 다음 전제 조건이 충족되는지 확인하십시오:

1. C# 프로그래밍 언어에 대한 기본 지식.  
2. 시스템에 Visual Studio가 설치되어 있음.  
3. Aspose.Tasks for .NET 라이브러리가 설치되어 있음. [here](https://releases.aspose.com/tasks/net/)에서 다운로드할 수 있습니다.

## 네임스페이스 가져오기

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;
```

## 단계 1: 프로젝트 파일 로드

먼저, 할당 베이스라인이 포함된 프로젝트 파일을 로드해야 합니다.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## 베이스라인을 읽는 방법은?

다음으로, 프로젝트의 각 리소스 할당을 반복하여 해당 베이스라인에 접근합니다.

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

## 단계 3: 할당 베이스라인 삭제

이 단계에서는 프로젝트에서 모든 할당 베이스라인을 삭제하는 방법을 보여줍니다.

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

## 일반적인 문제 및 해결책

| 문제 | 해결책 |
|-------|----------|
| **베이스라인이 비어 있음** | 프로젝트 파일에 실제로 저장된 베이스라인이 포함되어 있는지 확인하십시오; 베이스라인은 자동으로 생성되지 않습니다. |
| **`baselines.ParentAssignment`에 접근할 때 `NullReferenceException`** | 할당 객체가 null이 아니며 베이스라인이 초기화되었는지 확인하십시오. |
| **대규모 프로젝트에서 성능 저하** | `Assignment`을 배치로 처리하거나 `Assignment.Id`로 필터링하여 범위를 제한하십시오. |

## 결론

할당 베이스라인의 효율적인 관리는 프로젝트 관리에서 매우 중요하며, 일정 준수와 프로젝트 진행 상황을 정확하게 추적할 수 있게 합니다. Aspose.Tasks for .NET을 사용하면 할당 베이스라인 처리가 원활해져 개발자에게 프로젝트 관리 프로세스를 간소화하는 데 필요한 도구를 제공합니다.

## FAQ

### Q1: Aspose.Tasks가 다양한 프로젝트 파일 형식의 할당 베이스라인을 처리할 수 있나요?

A1: 예, Aspose.Tasks는 MPP, XML, MPX 등 다양한 프로젝트 파일 형식을 지원하므로 다양한 파일 유형에서 할당 베이스라인을 손쉽게 관리할 수 있습니다.

### Q2: Aspose.Tasks가 모든 .NET Framework 버전과 호환됩니까?

A2: Aspose.Tasks for .NET은 여러 .NET Framework 버전과 호환되어 다양한 환경의 개발자에게 호환성과 유연성을 제공합니다.

### Q3: Aspose.Tasks를 사용하여 할당 베이스라인을 프로그래밍 방식으로 조작할 수 있나요?

A3: 물론입니다. Aspose.Tasks는 포괄적인 API를 제공하여 개발자가 프로젝트 요구 사항에 따라 할당 베이스라인을 프로그래밍 방식으로 생성, 읽기, 업데이트 및 삭제할 수 있습니다.

### Q4: Aspose.Tasks가 개발자를 위한 기술 지원을 제공합니까?

A4: 예, Aspose.Tasks는 커뮤니티 포럼을 통해 강력한 기술 지원을 제공하며, 개발자는 여기서 도움을 구하고, 지식을 공유하며, 동료와 협업할 수 있습니다.

### Q5: 구매하기 전에 Aspose.Tasks를 체험할 수 있나요?

A5: 예, Aspose.Tasks는 무료 체험 버전을 제공하여 개발자가 구매 결정을 내리기 전에 기능과 활용성을 탐색할 수 있습니다.

## 자주 묻는 질문

**Q: 특정 할당에 대한 베이스라인을 어떻게 읽나요?**  
A: 해당 할당의 `Assignment.Baselines` 컬렉션에 접근하고 “베이스라인을 읽는 방법은?” 섹션에 표시된 대로 반복합니다.

**Q: 기존 할당에 새 베이스라인을 추가할 수 있나요?**  
A: 예, `AssignmentBaseline` 객체를 생성하고 `Start`와 `Finish` 값을 설정한 뒤 `Assignment.Baselines` 컬렉션에 추가할 수 있습니다.

**Q: 베이스라인을 삭제하면 원래 일정에 영향을 줍니까?**  
A: 베이스라인을 삭제하면 저장된 스냅샷만 제거되며 현재 일정(실제 날짜)은 변경되지 않습니다.

**Q: 베이스라인 데이터를 CSV로 내보낼 수 있나요?**  
A: Aspose.Tasks는 베이스라인에 대한 직접적인 CSV 내보내기를 제공하지 않지만, 컬렉션을 반복하여 표준 .NET I/O 클래스를 사용해 CSV 파일에 값을 기록할 수 있습니다.

**Q: Aspose.Tasks가 베이스라인 비교 보고서를 지원합니까?**  
A: 예, 베이스라인 날짜와 실제 날짜를 프로그래밍 방식으로 비교하고 원하는 보고 라이브러리를 사용해 맞춤 보고서를 생성할 수 있습니다.

---

**마지막 업데이트:** 2026-03-19  
**테스트 환경:** Aspose.Tasks for .NET (latest)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}