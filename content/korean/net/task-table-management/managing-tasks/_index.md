---
title: Aspose.Tasks에서 작업 관리
linktitle: Aspose.Tasks에서 작업 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용한 작업 관리에 대한 포괄적인 가이드를 살펴보세요. 추가, 분할된 부품 표시, 이동, 속성 가져오기/설정 등의 방법을 알아보세요.
type: docs
weight: 15
url: /ko/net/task-table-management/managing-tasks/
---
## 소개
프로젝트 내의 작업을 효율적으로 관리하려는 .NET 개발자라면 Aspose.Tasks for .NET이 강력한 솔루션을 제공합니다. 이 튜토리얼은 Aspose.Tasks를 사용하여 작업을 관리하는 다양한 측면을 안내하고 단계별 지침과 코드 예제를 제공합니다. 작업 추가, 분할된 부분 표시, 동일한 상위 항목 아래 작업 이동, 작업 속성 가져오기/설정, 작업 할당 반복, 작업 기준 읽기 또는 작업 삭제 등 무엇이든 이 가이드에서 다룹니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET 라이브러리용 Aspose.Tasks: .NET 라이브러리용 Aspose.Tasks가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
2. 문서 디렉터리: 프로젝트 문서가 저장될 디렉터리를 설정합니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Tasks 작업에 필요한 네임스페이스를 포함합니다.
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. 프로젝트에 작업 추가
```csharp
// 새 프로젝트 만들기
var project = new Project();
// 작업 추가
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// 프로젝트 저장
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. 태스크 분할 부분 표시
```csharp
// 분할된 작업으로 프로젝트 로드
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// 작업에 액세스
var task = project.RootTask.Children.GetById(4);
// 분할된 부분 표시
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. 동일한 상위 항목으로 작업 이동
```csharp
try
{
    // 프로젝트 로드
    var project = new Project(DataDir + "MoveTask.mpp");
    // ID가 3인 작업 이전에 ID가 5인 작업을 이동합니다.
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // 수정된 프로젝트 저장
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. 작업 속성 가져오기/설정
```csharp
// 새 프로젝트 만들기
var project = new Project();
// 작업 추가 및 속성 설정
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// 작업 속성 수집 및 표시
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. 작업 할당 반복
```csharp
// 과제가 포함된 프로젝트 로드
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// 작업 할당 수집 및 표시
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. 작업 기준 읽기
```csharp
// 새 프로젝트 만들기
var project = new Project();
// 작업 추가 및 기준 설정
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// 작업 기준 기간 표시
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. 작업 삭제
```csharp
// 새 프로젝트 만들기
var project = new Project();
// 작업 추가
var task = project.RootTask.Children.Add("Task");
//삭제 전후의 작업 수 표시
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// 작업 삭제
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## 결론
Aspose.Tasks for .NET에서 작업을 관리하는 것은 제공된 예제를 통해 원활한 프로세스입니다. 노련한 개발자이든 이제 막 시작하는 개발자이든 이러한 기술을 통합하면 프로젝트 관리 능력이 향상됩니다.
## 자주 묻는 질문
### Q: Aspose.Tasks는 모든 .NET 프레임워크와 호환됩니까?
A: 예, Aspose.Tasks는 다양한 .NET 프레임워크를 지원하여 개발 환경과의 호환성을 보장합니다.
### Q: Aspose.Tasks에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 A: 다음에서 30일 임시 라이센스를 받을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks에서 분할 작업을 작업할 때 제한 사항이 있나요?
 A: 분할 작업은 강력한 기능이며 자세한 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).
### Q: 예제에 표시된 것 이상으로 작업 속성을 사용자 지정할 수 있습니까?
답: 물론이죠! Aspose.Tasks는 작업 속성에 대한 광범위한 사용자 정의 옵션을 제공합니다. 자세한 내용은 설명서를 확인하세요.
### Q: Aspose.Tasks에 대한 지원은 어떻게 받나요?
 답: 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티 지원 및 토론을 위해.