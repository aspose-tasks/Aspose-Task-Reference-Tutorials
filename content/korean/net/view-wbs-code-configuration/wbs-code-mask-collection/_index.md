---
title: .NET용 Aspose.Tasks로 WBS 코드 마스크 마스터하기
linktitle: Aspose.Tasks의 WBS 코드 마스크 컬렉션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks로 프로젝트 관리를 강화하세요. 이 포괄적인 튜토리얼에서 WBS 코드 마스크를 손쉽게 생성, 관리 및 전송하는 방법을 알아보세요.
type: docs
weight: 15
url: /ko/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## 소개
역동적인 프로젝트 관리 세계에서는 작업을 효율적으로 구성하는 것이 중요합니다. Aspose.Tasks for .NET은 프로젝트 작업분류체계(WBS) 코드를 쉽게 관리할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 WBS 코드 마스크 컬렉션을 자세히 살펴보고 .NET용 Aspose.Tasks를 사용하여 이를 구현하고 조작하는 방법을 탐구합니다.
## 전제조건
이 코딩 여정을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식.
-  개발 환경에 설치된 .NET용 Aspose.Tasks. 그렇지 않은 경우 다운로드하십시오.[여기](https://releases.aspose.com/tasks/net/).
- 원활한 코딩 환경을 위한 Visual Studio와 같은 코드 편집기입니다.
## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 가져오세요.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 프로젝트 및 WBS 코드 정의 초기화
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. WBS 코드 마스크 정의
기존 코드 마스크를 지우고 새 마스크를 추가합니다.
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. 코드 마스크 정보 표시
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. 프로젝트에 작업 추가
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. 작업 정보 검색
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. 코드 마스크 조작
코드 마스크를 제거하고 제거되었는지 확인합니다.
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. 코드 마스크를 다른 프로젝트에 복사
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. 다른 프로젝트에 코드 마스크 표시
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. 다른 프로젝트에 작업 추가
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. 다른 프로젝트에 WBS 코드 표시
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 결론
.NET용 Aspose.Tasks를 사용하면 WBS 코드 관리가 손쉬운 작업이 됩니다. 이 튜토리얼에서는 WBS 코드 마스크의 생성, 조작 및 전송을 다루며 프로젝트 관리 경험을 향상시키기 위한 포괄적인 가이드를 제공합니다.
## 자주 묻는 질문
### Q: Aspose.Tasks for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?
A: Aspose.Tasks는 주로 .NET 언어를 지원하지만 다른 언어와의 상호 운용성 옵션을 탐색할 수도 있습니다.
### Q: Aspose.Tasks for .NET에 사용할 수 있는 평가판이 있습니까?
 A: 예, 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET에 대한 도움을 구하거나 문제를 보고하려면 어떻게 해야 합니까?
 답: 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지원과 토론을 위해.
### Q: 프로젝트 관리에서 WBS 코드의 목적은 무엇입니까?
A: WBS 코드는 프로젝트 작업을 계층적으로 구성하고 구조화하여 프로젝트 계획에 대한 체계적인 접근 방식을 제공합니다.
### Q: .NET용 Aspose.Tasks에서 WBS 코드 형식을 사용자 정의할 수 있나요?
A: 물론 .NET용 Aspose.Tasks를 사용하여 WBS 코드의 형식과 구조를 완전히 제어할 수 있습니다.