---
date: 2026-03-19
description: Aspose.Tasks의 트리 알고리즘을 사용하여 프로젝트에 리소스를 추가하고 작업 기간을 계산하는 방법을 배우고, .NET에서
  작업에 리소스를 할당하세요.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 트리 알고리즘을 사용하여 프로젝트에 리소스 추가
url: /ko/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 트리 알고리즘을 사용하여 프로젝트에 리소스 추가

## Introduction

이 튜토리얼에서는 Aspose.Tasks for .NET이 제공하는 강력한 트리 알고리즘을 활용하여 **프로젝트에 리소스를 추가하는 방법**을 알아봅니다. 작업 계층 구조를 만들고, 작업 기간을 계산하며, 작업에 리소스를 할당하는 과정을 단계별로 명확하게 설명하므로 여러분의 솔루션에 그대로 복사해서 사용할 수 있습니다.

## Quick Answers
- **Tree Algorithm은 무엇을 하나요?** 작업 계층 구조를 순회하여 작업 값을 효율적으로 집계합니다.  
- **이 가이드에서 다루는 주요 작업은 무엇인가요?** 프로젝트에 리소스를 추가하고 작업 총합을 업데이트합니다.  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 정식 라이선스가 필요합니다.  
- **.NET Core와 함께 사용할 수 있나요?** 예, Aspose.Tasks는 .NET Framework와 .NET Core를 지원합니다.  
- **구현에 얼마나 걸리나요?** 기본 프로젝트 파일의 경우 약 10‑15분 정도 소요됩니다.

## What is “add resource to project” in Aspose.Tasks?

프로젝트에 리소스를 추가한다는 것은 `Resource` 객체를 생성하고, 유형(예: work)을 정의한 뒤 `ResourceAssignments`를 통해 하나 이상의 작업에 연결하는 것을 의미합니다. 이를 통해 스케줄러가 노력, 비용 및 전체 프로젝트 기간을 계산할 수 있습니다.

## Why use the Tree Algorithm for resource work calculations?

트리 알고리즘은 작업 트리를 한 번만 순회하면서 리프 작업의 작업량을 요약 작업으로 누적합니다. 대규모 프로젝트와 깊은 계층 구조에서 개별 작업을 반복해서 검사하는 방식보다 훨씬 효율적이며, 요약 작업의 작업 값이 하위 작업과 항상 일치하도록 보장합니다.

## Prerequisites

시작하기 전에 다음 항목을 준비하세요:

1. **Visual Studio** – 최신 버전(2019, 2022 등) 중 하나.  
2. **Aspose.Tasks for .NET** – [here](https://releases.aspose.com/tasks/net/)에서 다운로드.  
3. **Basic C# knowledge** – 클래스, 객체 및 간단한 LINQ에 익숙해야 합니다.

## Import Namespaces

C# 프로젝트에서 Aspose.Tasks 기능을 사용하기 위해 필요한 네임스페이스를 가져옵니다:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

이제 각 예제를 여러 단계로 나누어 살펴보겠습니다:

## Step 1: Load Project File

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

`Project` 클래스를 사용하여 프로젝트 파일을 메모리로 로드합니다.

## Step 2: Define Task Hierarchy

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

상위 작업과 하위 작업을 추가하여 작업 계층 구조를 정의합니다.

## Step 3: Set Task Properties (including **calculate task duration**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

여기서는 작업 시간을 `Duration` 객체로 변환하고 종료 날짜를 도출함으로써 **작업 기간을 계산**합니다.

## Step 4: Add Resource (**assign resources to tasks**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

이 코드 조각은 **프로젝트에 리소스를 추가**하고 **작업에 리소스를 할당**하여 스케줄러가 누가 작업을 담당하는지 알 수 있게 합니다.

## Step 5: Apply Tree Algorithm

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

`WorkAccumulator` 클래스를 초기화하고 트리 알고리즘을 적용하여 계층 전체에 걸친 공통 작업을 수집합니다.

## Step 6: Update Task Work

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

수집된 정보를 기반으로 작업의 작업 값을 업데이트합니다.

## Common Issues & Tips

- **Missing calendar settings:** 종료 날짜가 이상하게 보이면 `GetFinishDateByStartAndWork`를 호출하기 전에 프로젝트 캘린더가 올바르게 설정되었는지 확인하세요.  
- **Resource type mismatch:** 노력 기반 리소스는 반드시 `Rsc.Type`을 `ResourceType.Work`로 설정해야 합니다. 그렇지 않으면 작업 누적이 0이 될 수 있습니다.  
- **Pro tip:** 작업을 업데이트한 후 `project.Save("UpdatedProject.mpp")`을 호출하여 변경 사항을 저장하세요.

## Conclusion

이 단계를 따라 하면 Aspose.Tasks의 트리 알고리즘을 사용하여 **프로젝트에 리소스를 추가**, **작업 기간을 계산**, **작업에 리소스를 할당**하는 방법을 알게 됩니다. 이 방법은 계층 관리와 요약 작업 값의 정확성을 최소한의 코드로 보장합니다.

## FAQ's

### Q1: What is Aspose.Tasks for .NET?

A1: Aspose.Tasks for .NET은 C#를 사용해 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있게 해 주는 강력한 API입니다.

### Q2: Can I download a free trial of Aspose.Tasks for .NET?

A2: 예, [here](https://releases.aspose.com/)에서 Aspose.Tasks for .NET의 무료 체험판을 다운로드할 수 있습니다.

### Q3: Where can I find documentation for Aspose.Tasks for .NET?

A3: 문서는 [here](https://reference.aspose.com/tasks/net/)에서 확인할 수 있습니다.

### Q4: How can I get support for Aspose.Tasks for .NET?

A4: Aspose.Tasks 관련 지원은 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)에서 받을 수 있습니다.

### Q5: Is there a temporary license available for testing purposes?

A5: 예, 테스트용 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 얻을 수 있습니다.

## Frequently Asked Questions

**Q: Can I use this approach with an existing large project file?**  
A: 물론입니다. 트리 알고리즘은 크기에 관계없이 모든 `Project` 인스턴스에서 작동합니다.

**Q: Does the algorithm also update cost values?**  
A: 예제는 작업에 초점을 맞추지만, `Tsk.Cost`를 누적하는 방식으로 확장하면 비용도 업데이트할 수 있습니다.

**Q: What .NET versions are supported?**  
A: Aspose.Tasks는 .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, .NET 6+를 지원합니다.

**Q: How do I handle multiple resources per task?**  
A: `project.ResourceAssignments.Add(task, resource)`를 사용해 각 리소스를 추가하면 누산기가 자동으로 작업을 합산합니다.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}