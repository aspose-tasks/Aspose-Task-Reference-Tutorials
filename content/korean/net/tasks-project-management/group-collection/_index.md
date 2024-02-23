---
title: Aspose.Tasks에서 프로젝트 컬렉션 관리
linktitle: Aspose.Tasks에서 그룹 컬렉션 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 컬렉션을 효율적으로 관리하는 방법을 알아보세요. 단계별 가이드를 따르세요.
type: docs
weight: 26
url: /ko/net/tasks-project-management/group-collection/
---
## 소개
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 그룹 MS 프로젝트 컬렉션을 관리하는 방법을 살펴보겠습니다. 그룹 컬렉션 관리는 프로젝트 내에서 작업과 리소스를 효율적으로 구성하고 조작하는 데 중요합니다.
## 전제조건
이 튜토리얼을 진행하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: 다음에서 .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/net/).
2. C#에 대한 기본 지식: 이 자습서에는 C# 코딩이 포함되므로 C# 프로그래밍 언어 기본 사항을 숙지하세요.
3. 개발 환경: Visual Studio 또는 .NET 개발을 지원하는 기타 IDE와 같은 개발 환경을 설정합니다.

## 네임스페이스 가져오기
먼저 C# 코드에서 Aspose.Tasks 기능을 사용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 1단계: 프로젝트 로드
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
이 단계에는 MS 프로젝트 파일을 Aspose.Tasks 프로젝트 개체에 로드하여 작업을 수행할 수 있는 작업이 포함됩니다.
## 2단계: 작업 그룹 반복
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
여기서는 프로젝트 내의 작업 그룹을 반복하여 각 그룹의 메뉴에 색인, 이름 및 가시성과 같은 세부 정보를 인쇄합니다.
## 3단계: 리소스 그룹 반복
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
마찬가지로 이 단계는 리소스 그룹을 반복하여 메뉴에 해당 인덱스, 이름 및 가시성을 표시합니다.
## 4단계: 그룹을 지우고 다른 프로젝트에 복사
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// 다른 프로젝트의 그룹 지우기
otherProject.TaskGroups.Clear();
// 다른 프로젝트에 그룹 복사
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
여기서는 다른 프로젝트의 그룹을 지운 다음 원래 프로젝트의 그룹을 해당 프로젝트로 복사합니다.
## 5단계: 사용자 지정 작업 그룹 추가
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
이 단계에서는 사용자 지정 작업 그룹을 생성하고 아직 없는 경우 다른 프로젝트에 추가합니다.
## 6단계: 모든 그룹 제거
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
마지막으로 다른 프로젝트에서 모든 그룹을 제거합니다.

## 결론
.NET용 Aspose.Tasks에서 그룹 MS 프로젝트 컬렉션을 관리하는 것은 프로젝트 데이터를 효율적으로 구성하고 조작하는 데 필수적입니다. 이 튜토리얼에 설명된 단계를 따르면 프로젝트 내의 작업 및 리소스 그룹을 효과적으로 처리하여 전반적인 프로젝트 관리를 개선할 수 있습니다.
## FAQ
### Aspose.Tasks for .NET은 모든 버전의 MS Project와 호환됩니까?
.NET용 Aspose.Tasks는 2003, 2007, 2010, 2013, 2016 및 2019를 포함한 다양한 버전의 Microsoft Project를 지원합니다.
### .NET용 Aspose.Tasks를 사용하여 그룹 속성을 사용자 정의할 수 있나요?
예, .NET용 Aspose.Tasks를 사용하여 이름 및 가시성과 같은 그룹 속성을 사용자 정의할 수 있습니다.
### .NET용 Aspose.Tasks는 플랫폼 간 호환성을 제공합니까?
.NET용 Aspose.Tasks는 주로 .NET 프레임워크를 대상으로 하지만 .NET Core 및 .NET Standard를 사용하는 크로스 플랫폼 시나리오에서 사용할 수 있습니다.
### .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?
 .NET용 Aspose.Tasks에 대한 지원은 다음을 통해 얻을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
### .NET용 Aspose.Tasks에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 .NET용 Aspose.Tasks의 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/).