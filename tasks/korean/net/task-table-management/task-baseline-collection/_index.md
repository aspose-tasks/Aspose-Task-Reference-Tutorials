---
title: Aspose.Tasks의 작업 기준선 수집
linktitle: Aspose.Tasks의 작업 기준선 수집
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 작업 기준선을 쉽게 탐색하세요. 효율적인 프로젝트 관리가 간편해졌습니다. 지금 다운로드하세요! #Aspose.Tasks #MS 프로젝트
type: docs
weight: 17
url: /ko/net/task-table-management/task-baseline-collection/
---
## 소개
프로젝트 작업의 원활한 조작 및 관리를 용이하게 하는 강력한 라이브러리인 Aspose.Tasks for .NET의 세계에 오신 것을 환영합니다. 이 튜토리얼에서는 프로젝트 계획 및 추적의 중요한 측면인 작업 기준선의 놀라운 영역을 자세히 살펴보겠습니다. 이 가이드를 마치면 작업 기준 컬렉션 작업 기술을 숙지하여 프로젝트 관리 기능을 향상시킬 수 있습니다.
## 전제조건
이 여정을 시작하기 전에 다음과 같은 전제 조건이 갖추어져 있는지 확인하세요.
-  .NET 라이브러리용 Aspose.Tasks: 다음에서 라이브러리를 다운로드하고 설치하세요.[릴리스 페이지](https://releases.aspose.com/tasks/net/).
- 개발 환경: 선호하는 .NET 개발 환경을 설정합니다.
- C#에 대한 기본 이해: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.
이제 모든 준비가 완료되었으므로 .NET용 Aspose.Tasks의 흥미로운 세계로 뛰어들어 보겠습니다.
## 네임스페이스 가져오기
C# 프로젝트에서 필요한 네임스페이스를 가져오는 것부터 시작합니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 프로젝트 및 작업 설정
새 프로젝트를 만들고 여기에 작업을 추가하는 것으로 시작하세요.
```csharp
var project = new Project();
var task = project.RootTask.Children.Add("Task");
```
## 2. 프로젝트 기준선 생성
이제 작업에 대한 프로젝트 기준선을 만들어 보겠습니다.
```csharp
project.SetBaseline(BaselineType.Baseline);
```
## 3. 작업 기준 인쇄
작업 기준선에 대한 정보를 인쇄합니다.
```csharp
Console.WriteLine("Count of task baselines: " + task.Baselines.Count);
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration: {0}", baseline.Duration);
    Console.WriteLine("Baseline start: {0}", baseline.Start);
    Console.WriteLine("Baseline finish: {0}", baseline.Finish);
}
```
## 4. 모든 기준선 지우기
필요한 경우 작업과 관련된 모든 기준을 지울 수 있습니다.
```csharp
List<TaskBaseline> baselines = task.Baselines.ToList();
for (var i = 0; i < baselines.Count; i++)
{
    task.Baselines.Remove(baselines[i]);
}
```
축하해요! Aspose.Tasks for .NET을 사용하여 작업 기준 작업 프로세스를 성공적으로 탐색했습니다.
## 결론
결론적으로 Aspose.Tasks for .NET으로 작업 기준을 마스터하면 효율적인 프로젝트 관리를 위한 수많은 가능성이 열립니다. 이 가이드는 이 기능을 효과적으로 활용할 수 있는 지식과 기술을 제공합니다.
## 자주 묻는 질문
### Q: 단일 작업에 대해 여러 기준선을 생성할 수 있습니까?
A: 예, .NET용 Aspose.Tasks를 사용하면 작업에 대한 여러 기준을 설정하고 관리할 수 있습니다.
### Q: 작업 기준으로 작업하는 동안 예외를 어떻게 처리합니까?
A: try-catch 블록을 사용하면 예외를 정상적으로 처리하고 코드가 원활하게 실행되도록 할 수 있습니다.
### Q: 프로젝트에 포함할 수 있는 작업 수에 제한이 있나요?
A: Aspose.Tasks for .NET은 작업 수에 엄격한 제한을 두지 않아 다양한 프로젝트 규모에 대한 유연성을 제공합니다.
### Q: 인쇄된 기본 정보의 형식을 사용자 정의할 수 있습니까?
답: 물론이죠! 기본 세부 사항을 인쇄할 때 형식을 완벽하게 제어할 수 있으므로 특정 요구 사항에 맞게 조정할 수 있습니다.
### Q: 문제가 발생하거나 추가 질문이 있는 경우 어디서 도움을 받을 수 있나요?
 답: 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 전담 지원 및 지역 사회 지원을 위해.