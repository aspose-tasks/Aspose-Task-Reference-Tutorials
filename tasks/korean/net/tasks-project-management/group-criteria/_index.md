---
title: Aspose.Tasks에서 MS 프로젝트 그룹 기준 조작
linktitle: Aspose.Tasks의 그룹 기준
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks를 사용하여 .NET에서 프로그래밍 방식으로 MS 프로젝트 파일을 조작하는 방법을 살펴보세요. 작업 그룹 및 기준 정보를 단계별로 검색하는 예입니다.
weight: 27
url: /ko/net/tasks-project-management/group-criteria/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 그룹 기준 조작

## 소개
Aspose.Tasks for .NET은 .NET 애플리케이션에서 Microsoft Project 파일 작업을 용이하게 해주는 강력한 API입니다. 프로젝트 관리 소프트웨어를 개발하든 프로젝트 데이터를 프로그래밍 방식으로 조작해야 하든 Aspose.Tasks는 귀하의 요구 사항을 충족하는 포괄적인 기능 세트를 제공합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
### 1. C# 및 .NET Framework에 대한 지식
이 자습서에서 제공되는 예제를 이해하고 구현하려면 C# 프로그래밍 언어 및 .NET Framework에 대한 지식이 필수적입니다.
### 2. .NET용 Aspose.Tasks 설치
 개발 환경에 .NET용 Aspose.Tasks가 설치되어 있는지 확인하세요. 다음에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/) 제공된 설치 지침을 따르십시오.
### 3. 통합 개발 환경(IDE)
C# 코드를 작성하고 실행하려면 시스템에 Visual Studio와 같은 IDE를 설치하십시오.

## 네임스페이스 가져오기
시작하려면 C# 코드에서 필요한 네임스페이스를 가져옵니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1단계: Microsoft Project 파일 로드
먼저 Microsoft Project 파일의 경로를 지정합니다.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 바꾸다`"Your Document Directory"` 프로젝트 파일의 경로로.
## 2단계: 작업 그룹 정보 검색
다음으로 프로젝트의 작업 그룹에 대한 정보를 검색합니다.
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
이 코드 조각은 작업 그룹의 총 개수를 인쇄하고, 두 번째 작업 그룹, 해당 이름, 보유 기준 개수를 검색합니다.
## 3단계: 작업 그룹의 기준 정보 검색
이제 작업 그룹 내의 특정 기준에 대해 자세히 살펴보겠습니다.
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
이 세그먼트에는 인덱스, 필드, 그룹화 정보, 셀 색상, 글꼴 색상, 그룹 간격, 시작점 등 기준의 다양한 속성이 표시됩니다.
## 4단계: Criterion의 글꼴 정보 검색
마지막으로 기준의 글꼴 관련 세부정보를 얻습니다.
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
이 단계에서는 글꼴 이름, 크기, 스타일 및 기준이 오름차순 또는 내림차순으로 정렬되었는지 여부를 인쇄합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 파일에서 작업 그룹 및 기준에 대한 정보를 검색하는 방법을 살펴보았습니다. 단계별 가이드를 따르면 .NET 애플리케이션에서 프로그래밍 방식으로 프로젝트 데이터를 효율적으로 사용할 수 있습니다.
## FAQ
### Aspose.Tasks가 대용량 Microsoft Project 파일을 처리할 수 있나요?
Aspose.Tasks는 대용량 프로젝트 파일을 효율적으로 처리하도록 최적화되어 높은 성능과 안정성을 보장합니다.
### Aspose.Tasks는 모든 버전의 Microsoft Project와 호환됩니까?
예, Aspose.Tasks는 다양한 버전의 Microsoft Project를 지원하여 다양한 파일 형식 간의 호환성을 보장합니다.
### Aspose.Tasks를 사용하여 프로젝트 데이터를 조작할 수 있나요?
물론 Aspose.Tasks는 작업, 리소스, 달력 등을 포함하여 프로젝트 데이터를 조작하는 광범위한 기능을 제공합니다.
### Aspose.Tasks는 다양한 .NET 플랫폼을 지원합니까?
예, Aspose.Tasks는 .NET Framework, .NET Core 및 .NET Standard를 포함한 여러 .NET 플랫폼을 지원합니다.
### 도움을 구할 수 있는 Aspose.Tasks 커뮤니티 포럼이 있나요?
 네, 방문하실 수 있습니다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 질문하고, 지식을 공유하고, 다른 사용자와 협력할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
