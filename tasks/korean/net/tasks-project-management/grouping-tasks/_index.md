---
title: Aspose.Tasks를 사용한 효율적인 MS 프로젝트 작업 그룹화
linktitle: Aspose.Tasks에서 작업 그룹화
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project 작업을 효과적으로 그룹화하는 방법을 알아보세요.
weight: 25
url: /ko/net/tasks-project-management/grouping-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용한 효율적인 MS 프로젝트 작업 그룹화

## 소개
Microsoft Project에서 작업을 관리하는 것은 때로는 어려울 수 있으며, 특히 작업을 효율적으로 구성하는 경우 더욱 그렇습니다. Aspose.Tasks for .NET은 작업을 효과적으로 그룹화하는 기능을 제공하여 이에 대한 포괄적인 솔루션을 제공합니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 작업을 그룹화하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: 다음에서 .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
2. 개발 환경: .NET 개발 환경이 설정되어 있는지 확인하세요.
3. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기
먼저 Aspose.Tasks 기능을 사용하려면 필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 1단계: MS 프로젝트 파일 로드
다음 코드를 사용하여 MS 프로젝트 파일을 로드하는 것으로 시작하세요.
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## 2단계: 작업 그룹에 액세스
다음으로 프로젝트 내의 작업 그룹에 액세스해 보겠습니다.
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## 3단계: 그룹 정보 검색
이제 작업 그룹에 대한 정보를 검색합니다.
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## 4단계: 액세스 그룹 기준
작업 그룹에 설정된 기준에 액세스합니다.
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## 5단계: 기준 정보 검색
각 기준에 대한 자세한 정보를 검색합니다.
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
다음 단계를 수행하면 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 작업을 효과적으로 그룹화하여 프로젝트 데이터의 구성 및 관리를 향상시킬 수 있습니다.

## 결론
결론적으로 Aspose.Tasks for .NET은 MS 프로젝트 작업을 그룹화하는 강력한 기능을 제공하여 프로젝트 데이터를 더 효과적으로 구성하고 관리할 수 있습니다. 이 자습서에 설명된 단계를 따르면 .NET 애플리케이션에서 이러한 기능을 효율적으로 활용할 수 있습니다.
## FAQ
### 사용자 정의 기준에 따라 작업을 그룹화할 수 있나요?
예, Aspose.Tasks for .NET을 사용하여 특정 요구 사항에 따라 작업을 그룹화하기 위한 사용자 정의 기준을 정의할 수 있습니다.
### Aspose.Tasks는 다양한 버전의 MS 프로젝트 파일을 지원합니까?
예, Aspose.Tasks는 다양한 버전의 MS 프로젝트 파일을 지원하여 호환성과 원활한 통합을 보장합니다.
### .NET용 Aspose.Tasks에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 .NET용 Aspose.Tasks 무료 평가판을 구할 수 있습니다.[여기](https://releases.aspose.com/).
### 그룹화된 작업의 모양을 사용자 지정할 수 있나요?
물론 Aspose.Tasks는 셀 색상, 글꼴 및 스타일을 포함하여 그룹화된 작업의 모양을 사용자 정의하는 옵션을 제공합니다.
### .NET용 Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
 .NET용 Aspose.Tasks에 대한 지원 및 지원은 다음에서 찾을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
