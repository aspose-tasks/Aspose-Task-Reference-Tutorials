---
title: Aspose.Tasks에서 트리 알고리즘 사용
linktitle: Aspose.Tasks에서 트리 알고리즘 사용
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks의 트리 알고리즘을 사용하여 .NET 프로젝트에서 작업 계층 구조를 효과적으로 조작하는 방법을 알아보세요.
type: docs
weight: 13
url: /ko/net/advanced-concepts/tree-algorithm/
---
## 소개

Aspose.Tasks for .NET은 프로젝트 관리 작업, 리소스 및 일정 작업을 위한 강력한 기능을 제공합니다. 그러한 기능 중 하나는 사용자가 작업 계층을 효율적으로 조작할 수 있게 해주는 트리 알고리즘입니다. 이 튜토리얼에서는 Aspose.Tasks for .NET의 트리 알고리즘을 활용하여 프로젝트 내에서 일반적인 작업을 수집하고 작업 값을 업데이트하는 방법을 살펴보겠습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Visual Studio: 시스템에 Visual Studio가 설치되어 있는지 확인하세요.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C#에 대한 기본 이해: 예제를 따라가려면 C# 프로그래밍 언어에 대한 지식이 필요합니다.

## 네임스페이스 가져오기

C# 프로젝트에서 Aspose.Tasks 기능을 사용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

이제 각 예를 여러 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 파일 로드

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 다음을 사용하여 프로젝트 파일을 메모리에 로드합니다.`Project` 수업.

## 2단계: 작업 계층 정의

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

상위 및 하위 작업을 추가하여 작업 계층 구조를 정의합니다.

## 3단계: 작업 속성 설정

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

작업의 시작 날짜, 기간, 완료 날짜 등의 속성을 설정합니다.

## 4단계: 리소스 추가

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

프로젝트에 자원을 추가하고 필요에 따라 작업에 할당합니다.

## 5단계: 트리 알고리즘 적용

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 초기화`WorkAccumulator` 수업을 듣고 트리 알고리즘을 적용하여 일반적인 작업을 수집합니다.

## 6단계: 작업 업데이트

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

수집된 정보를 바탕으로 업무에 대한 업무 가치를 업데이트합니다.

## 결론

이 튜토리얼에서는 Aspose.Tasks for .NET의 트리 알고리즘을 활용하여 작업 계층 구조를 효과적으로 조작하는 방법을 배웠습니다. 단계별 가이드를 따르면 프로젝트 내의 작업과 리소스를 효율적으로 관리할 수 있습니다.

## FAQ

### Q1: .NET용 Aspose.Tasks란 무엇입니까?

A1: Aspose.Tasks for .NET은 개발자가 C#을 사용하여 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 API입니다.

### Q2: .NET용 Aspose.Tasks 무료 평가판을 다운로드할 수 있나요?

 A2: 예, 다음에서 .NET용 Aspose.Tasks 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Q3: .NET용 Aspose.Tasks에 대한 설명서는 어디에서 찾을 수 있습니까?

 A3: .NET용 Aspose.Tasks에 대한 설명서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).

### Q4: .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?

 A4: .NET용 Aspose.Tasks와 관련된 지원을 보려면 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).

### Q5: 테스트 목적으로 사용할 수 있는 임시 라이센스가 있습니까?

 A5: 예, 다음에서 테스트 목적으로 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).