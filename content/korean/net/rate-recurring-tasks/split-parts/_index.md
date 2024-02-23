---
title: Aspose.Tasks에서 MS 프로젝트 분할 부분 처리
linktitle: Aspose.Tasks에서 분할 부분 처리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 분할 부분을 효율적으로 처리하는 방법을 알아보세요. 프로젝트 관리 워크플로를 강화하세요.
type: docs
weight: 18
url: /ko/net/rate-recurring-tasks/split-parts/
---

## 소개
MS 프로젝트 분할 부분을 관리하는 것은 Aspose.Tasks for .NET을 사용할 때 프로젝트 관리의 중요한 측면이 될 수 있습니다. 이 튜토리얼에서는 단계별 지침을 사용하여 분할된 부품을 효과적으로 처리하는 방법을 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1.  .NET용 Aspose.Tasks 설치: 다음에서 .NET용 Aspose.Tasks를 다운로드하여 설치하세요.[웹사이트](https://releases.aspose.com/tasks/net/).
   
2. C#에 대한 기본 이해: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기
C# 코드에서 필요한 네임스페이스를 가져와야 합니다.
```csharp
    using Aspose.Tasks;
    using System;
    
```

## 1단계: 프로젝트 인스턴스 생성
```csharp
var project = new Project();
```
 새 인스턴스를 생성합니다.`Project` 수업.
## 2단계: 프로젝트 시작 및 종료 날짜 설정
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
프로젝트의 시작 날짜와 종료 날짜를 설정합니다.
## 3단계: 작업 추가
```csharp
var task = project.RootTask.Children.Add("Task1");
```
프로젝트에 새 작업을 추가합니다.
## 4단계: 작업 속성 설정
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
작업의 수동 상태, 시작 날짜, 기간 등의 속성을 설정합니다.
## 5단계: 자원 할당 추가
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
작업에 자원 할당을 추가합니다.
## 6단계: 할당 속성 설정
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
과제의 시작 날짜, 작업, 완료 날짜 등의 속성을 설정합니다.
## 7단계: 시간대별 데이터 생성
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
프로젝트 달력을 기반으로 과제에 대한 시간대별 데이터를 생성합니다.
## 8단계: 작업 분할
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
지정된 시간 내에 작업을 여러 부분으로 나눕니다.
## 9단계: 분할된 부분 반복
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
작업의 분할된 부분을 반복하고 시작 날짜와 완료 날짜를 인쇄합니다.

## 결론
.NET용 Aspose.Tasks에서 MS 프로젝트 분할 부분을 효과적으로 처리하는 것은 프로젝트 관리 효율성에 매우 중요합니다. 이 튜토리얼에 설명된 단계를 따르면 분할 작업을 원활하게 관리하고 프로젝트 관리 워크플로를 향상할 수 있습니다.
## FAQ
### Q: 다른 .NET 프레임워크와 함께 .NET용 Aspose.Tasks를 사용할 수 있습니까?
A: 예, Aspose.Tasks for .NET은 .NET Core 및 .NET Standard를 포함한 다양한 .NET 프레임워크와 호환됩니다.
### Q: Aspose.Tasks for .NET에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 다음에서 무료 평가판을 얻을 수 있습니다.[여기](https://releases.aspose.com/).
### Q: .NET용 Aspose.Tasks는 리소스 관리를 지원합니까?
A: 예, Aspose.Tasks for .NET을 사용하면 프로젝트 리소스를 효율적으로 관리할 수 있습니다.
### Q: .NET용 Aspose.Tasks를 사용하여 프로젝트 달력을 사용자 정의할 수 있나요?
A: 물론, 프로젝트 요구 사항에 따라 프로젝트 달력을 사용자 정의할 수 있습니다.
### Q: .NET용 Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
 답변: 다음 웹사이트에서 지원과 도움을 받으실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).