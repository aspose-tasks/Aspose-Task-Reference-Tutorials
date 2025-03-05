---
title: Aspose.Tasks에서 작업 컬렉션 관리
linktitle: Aspose.Tasks에서 작업 컬렉션 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks에서 효율적인 작업 컬렉션 관리를 살펴보세요. 생성부터 편집까지 마스터 프로젝트 관리를 쉽게 수행하세요.
type: docs
weight: 18
url: /ko/net/task-table-management/task-collection/
---
## 소개
.NET을 사용하여 프로젝트 관리의 세계를 탐구하고 있다면 Aspose.Tasks는 작업 컬렉션을 원활하게 처리하기 위한 솔루션입니다. 이 튜토리얼은 작업 컬렉션을 효율적으로 관리하는 프로세스를 안내하여 이 강력한 라이브러리를 최대한 활용할 수 있도록 합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본 지식.
- 컴퓨터에 Visual Studio가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.Tasks가 프로젝트에서 다운로드되고 참조됩니다.
## 네임스페이스 가져오기
시작하려면 C# 프로젝트에서 필요한 네임스페이스를 가져오겠습니다.
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
이러한 네임스페이스는 효과적인 작업 관리에 필요한 필수 클래스 및 메서드에 대한 액세스를 제공합니다.
이제 튜토리얼을 일련의 단계로 나누어 명확성과 단순성을 보장해 보겠습니다.
## 1단계: 프로젝트 인스턴스 생성
```csharp
var project = new Project();
```
 다음을 사용하여 새 프로젝트를 인스턴스화합니다.`Project` 수업.
## 2단계: 작업 수집 준비 상태 확인
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
작업 컬렉션이 읽기 전용인지 확인하세요.
## 3단계: 작업 생성
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
// 시작, 기간, 완료 등 추가 작업 속성 설정
// 작업 2와 작업 3의 유사한 단계
```
프로젝트 내에서 작업을 생성하고 해당 속성을 설정합니다.
## 4단계: 프로젝트 작업 인쇄
```csharp
foreach (var child in project.RootTask.Children)
{
    // 작업 세부정보 인쇄
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
프로젝트 내 각 작업의 세부정보를 인쇄합니다.
## 5단계: 작업 편집
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
ID 또는 UID를 사용하여 작업을 편집합니다.
## 6단계: 반복 작업 추가
```csharp
var parameters = new RecurringTaskParameters
{
    // 반복 작업 매개변수 설정
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
프로젝트에 반복 작업을 추가합니다.
## 7단계: 컬렉션을 목록으로 변환
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
작업 컬렉션을 목록으로 변환하고 각 작업에 대한 작업을 수행합니다.
## 결론
이 단계별 가이드를 사용하면 Aspose.Tasks for .NET에서 작업 컬렉션을 관리하는 것이 매우 쉽습니다. 작업을 생성, 편집 또는 삭제하는 경우 Aspose.Tasks를 사용하면 프로젝트 관리를 원활하게 처리할 수 있습니다.
## 자주 묻는 질문
### Aspose.Tasks는 .NET Core와 호환되나요?
예, Aspose.Tasks는 .NET Core를 지원하므로 크로스 플랫폼 애플리케이션에서 사용할 수 있습니다.
### 프로젝트 작업을 다른 파일 형식으로 내보낼 수 있나요?
전적으로! Aspose.Tasks는 PDF, XLSX 및 MPP를 포함한 다양한 내보내기 옵션을 제공합니다.
### 작업 간의 종속성을 어떻게 처리할 수 있나요?
 다음을 사용하여 작업 종속성을 설정할 수 있습니다.`TaskLink` Aspose.Tasks에서 제공하는 클래스입니다.
### Aspose.Tasks 지원을 위한 커뮤니티 포럼이 있나요?
 예, 다음에서 지원을 받고 커뮤니티에 참여할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks에 대한 임시 라이선스를 얻을 수 있나요?
 네, 임시면허증을 받으실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).