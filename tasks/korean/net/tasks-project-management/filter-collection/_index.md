---
title: Aspose.Tasks를 사용하여 MS 프로젝트 필터를 효율적으로 관리
linktitle: Aspose.Tasks에서 필터 수집 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 필터 MS 프로젝트 컬렉션을 효과적으로 관리하는 방법을 알아보세요.
type: docs
weight: 17
url: /ko/net/tasks-project-management/filter-collection/
---
## 소개
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 필터 MS 프로젝트 컬렉션을 효과적으로 관리하는 방법을 살펴보겠습니다. 필터 관리는 프로젝트 데이터를 효율적으로 구성하고 분석하는 데 중요합니다. Aspose.Tasks는 작업 및 리소스 필터를 원활하게 처리하는 강력한 기능을 제공합니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 Aspose.Tasks 설치: 다음에서 .NET용 Aspose.Tasks를 다운로드하여 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/net/).
2. .NET 개발 환경에 대한 액세스: Aspose.Tasks와 작동하도록 설정된 .NET 개발 환경이 있는지 확인하세요.

## 네임스페이스 가져오기
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 1단계: 프로젝트 파일 로드
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## 2단계: 작업 필터 반복
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## 3단계: 리소스 필터 반복
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## 4단계: 필터 지우기 및 복사
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// 다른 프로젝트의 필터 지우기
otherProject.TaskFilters.Clear();
// 다른 프로젝트에 필터 복사
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## 5단계: 사용자 정의 작업 필터 추가
```csharp
// 사용자 정의 작업 필터 추가
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## 6단계: 모든 필터 제거
```csharp
// 모든 필터 제거
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
다음 단계를 수행하면 Aspose.Tasks for .NET을 사용하여 필터 MS 프로젝트 컬렉션을 효율적으로 관리할 수 있습니다.

## 결론
MS 프로젝트 컬렉션의 필터를 효과적으로 관리하는 것은 프로젝트 데이터를 구성하고 분석하는 데 중요합니다. Aspose.Tasks for .NET은 작업 및 리소스 필터를 원활하게 처리하는 포괄적인 기능을 제공하여 개발자가 프로젝트 관리 작업을 효율적으로 간소화할 수 있도록 지원합니다.
## FAQ
### Q: Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있나요?
A: Aspose.Tasks는 복잡한 프로젝트를 포함하여 다양한 프로젝트 구조를 처리할 수 있는 강력한 기능을 제공하여 포괄적인 프로젝트 관리 기능을 보장합니다.
### Q: Aspose.Tasks는 다른 버전의 MS 프로젝트 파일과 호환됩니까?
A: 예, Aspose.Tasks는 다양한 MS 프로젝트 파일 형식을 지원하여 다양한 버전 간의 호환성을 보장합니다.
### Q: 특정 프로젝트 요구 사항에 따라 필터를 사용자 정의할 수 있습니까?
답: 물론이죠! Aspose.Tasks를 사용하면 개발자는 고유한 프로젝트 요구 사항에 맞는 사용자 정의 필터를 생성하여 유연성과 효율성을 높일 수 있습니다.
### Q: Aspose.Tasks는 문서와 지원 리소스를 제공합니까?
A: 예, Aspose.Tasks는 프로젝트 구현의 모든 단계에서 개발자를 지원하기 위해 광범위한 문서, 튜토리얼 및 전용 지원 포럼을 제공합니다.
### Q: Aspose.Tasks에 사용할 수 있는 평가판이 있나요?
A: 예, 개발자는 Aspose.Tasks의 무료 평가판에 액세스하여 구매 결정을 내리기 전에 기능을 살펴볼 수 있습니다.