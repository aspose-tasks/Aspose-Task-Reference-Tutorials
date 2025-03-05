---
title: Aspose.Tasks에서 작업 링크 처리
linktitle: Aspose.Tasks에서 작업 링크 처리
second_title: Aspose.태스크 .NET API
description: 프로젝트 작업 링크를 효율적으로 관리하는 데 있어 Aspose.Tasks for .NET의 강력한 기능을 살펴보세요. 프로젝트 관리 경험을 향상하려면 단계별 가이드를 따르십시오.
type: docs
weight: 19
url: /ko/net/task-table-management/task-link-collection/
---
## 소개
.NET용 Aspose.Tasks에서 작업 링크 처리에 대한 단계별 가이드에 오신 것을 환영합니다! 작업 링크는 프로젝트 관리에서 중요한 역할을 하며, 이를 통해 작업 간의 관계를 설정하고 종속성을 생성할 수 있습니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 작업 링크 컬렉션으로 작업하는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: Aspose.Tasks 라이브러리를 다운로드하고 설치합니다. 도서관을 찾으실 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
2. 샘플 프로젝트 파일: 예제와 함께 사용할 샘플 프로젝트 파일(예: "SampleProject.mpp")을 준비합니다.
이제 시작해보자!
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Tasks 작업에 필요한 네임스페이스를 가져와야 합니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1단계: 프로젝트 로드 및 작업 액세스
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
// 프로젝트 로드
var project = new Project(DataDir + "SampleProject.mpp");
// ID로 작업에 액세스
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## 2단계: 작업 링크 생성
작업을 서로 연결하여 종속성을 설정합니다.
```csharp
// FinishToStart 종속성을 사용하여 작업 연결
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## 3단계: 작업 링크 인쇄
프로젝트의 작업 링크를 인쇄합니다.
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//작업 링크를 통해 반복
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## 4단계: 작업 링크 편집
인덱스 액세스로 작업 링크를 편집합니다.
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## 5단계: 작업 링크 제거
프로젝트에서 모든 작업 링크를 제거합니다.
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## 결론
축하해요! .NET용 Aspose.Tasks에서 작업 링크를 처리하는 방법을 성공적으로 배웠습니다. 이 포괄적인 가이드에서는 프로젝트 로드, 작업 링크 생성, 링크 인쇄, 링크 편집 및 작업 링크 제거를 다루었습니다.
Aspose.Tasks가 제공하는 더 많은 특징과 기능을 자유롭게 탐색하여 프로젝트 관리 경험을 향상하세요.
## 자주 묻는 질문
### Aspose.Tasks는 모든 버전의 .NET과 호환됩니까?
예, Aspose.Tasks는 모든 버전의 .NET에서 원활하게 작동하도록 설계되었습니다.
### Aspose.Tasks를 사용하여 사용자 정의 작업 링크 유형을 만들 수 있나요?
현재 Aspose.Tasks는 표준 작업 링크 유형을 지원하며 사용자 정의 링크 유형은 사용할 수 없습니다.
### Aspose.Tasks의 작업에 제약 조건을 어떻게 적용할 수 있나요?
 다음을 사용하여 제약 조건을 적용할 수 있습니다.`ConstraintType` 의 재산`Task` Aspose.Tasks의 클래스입니다.
### Aspose.Tasks가 처리할 수 있는 프로젝트 파일의 크기에 제한이 있나요?
Aspose.Tasks는 성능에 미치는 영향을 최소화하면서 대규모 프로젝트 파일을 효율적으로 처리할 수 있습니다.
### Aspose.Tasks 지원을 위한 커뮤니티 포럼이 있나요?
 예, 다음에서 지원을 찾고 커뮤니티에 참여할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).