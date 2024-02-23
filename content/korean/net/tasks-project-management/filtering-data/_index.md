---
title: Aspose.Tasks를 사용한 효율적인 데이터 필터링
linktitle: Aspose.Tasks에서 데이터 필터링
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 데이터를 필터링하는 방법을 알아보세요. 손쉽게 생산성과 분석 기능을 향상하세요.
type: docs
weight: 16
url: /ko/net/tasks-project-management/filtering-data/
---
## 소개
Aspose.Tasks for .NET은 Microsoft Project 파일의 데이터를 필터링하는 강력한 기능을 제공하여 사용자가 프로젝트 정보를 효율적으로 관리하고 분석할 수 있도록 합니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 데이터를 필터링하는 방법을 단계별 가이드 형식으로 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 Aspose.Tasks 설치
 다음에서 .NET용 Aspose.Tasks를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/tasks/net/), 개발 환경에서 라이브러리를 설정하려면 제공된 설치 지침을 따르십시오.
### 2. 개발 환경 설정
.NET 프로그래밍을 위한 작업 개발 환경이 있는지 확인하세요. 여기에는 Visual Studio와 같은 호환 IDE와 C# 프로그래밍 언어에 대한 기본적인 이해가 포함됩니다.
### 3. 샘플 Microsoft Project 파일에 액세스
필터링할 데이터가 포함된 샘플 Microsoft Project 파일(.mpp)을 준비합니다. 프로젝트 디렉터리에서 파일에 액세스할 수 있는지 확인하세요.
## 네임스페이스 가져오기
C# 코드 파일에서 Aspose.Tasks 기능을 활용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
using System;
using System.Collections.Generic;

```
이제 Aspose.Tasks를 사용하여 MS 프로젝트에서 데이터를 필터링하는 프로세스를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 파일 로드
```csharp
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "SampleProject.mpp");
```
 교체를 확인하세요`"Your Document Directory"`프로젝트 파일 디렉터리 경로를 사용하세요.
## 2단계: 작업 필터 검색
```csharp
List<Filter> filters = project.TaskFilters.ToList();
```
프로젝트에 있는 작업 필터 목록을 검색합니다.
## 3단계: 작업 필터 세부 정보 표시
```csharp
foreach (var filter in filters)
{
    Console.WriteLine("Uid: " + filter.Uid);
    Console.WriteLine("Index: " + filter.Index);
    Console.WriteLine("Name: " + filter.Name);
    Console.WriteLine("Type: " + filter.FilterType);
    Console.WriteLine("Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Show Related Summary Rows: " + filter.ShowRelatedSummaryRows);
}
```
작업 필터 목록을 반복하고 Uid, 색인, 이름, 필터 유형, 메뉴에 표시 및 관련 요약 행 표시와 같은 세부 정보를 표시합니다.
## 4단계: 리소스 필터 확인
```csharp
List<Filter> resourceFilters = project.ResourceFilters.ToList();
```
프로젝트에 있는 리소스 필터 목록을 검색합니다.
## 5단계: 리소스 필터 세부 정보 표시
```csharp
Console.WriteLine("Project.ResourceFilters count: " + resourceFilters.Count);
Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + resourceFilters[0].FilterType);
Console.WriteLine("Resource filter ShowInMenu" + resourceFilters[0].ShowInMenu);
Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + resourceFilters[0].ShowRelatedSummaryRows);
```
개수, 필터 유형, 메뉴에 표시 및 관련 요약 행 표시를 포함한 리소스 필터의 세부 정보를 표시합니다.
## 결론
.NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 데이터를 필터링하는 것은 생산성과 분석 기능을 향상시키는 간단한 프로세스입니다. 이 튜토리얼에 설명된 단계를 따르면 특정 기준에 따라 프로젝트 정보를 효율적으로 관리할 수 있습니다.
## FAQ
### Q: Aspose.Tasks는 사용자 정의 기준에 따라 데이터를 필터링할 수 있습니까?
A: 예, Aspose.Tasks를 사용하면 프로젝트 요구 사항에 맞는 사용자 정의 기준에 따라 데이터를 필터링할 수 있습니다.
### Q: Aspose.Tasks는 모든 버전의 Microsoft Project 파일과 호환됩니까?
A: Aspose.Tasks는 다양한 버전의 Microsoft Project 파일을 지원하여 다양한 환경에서의 호환성을 보장합니다.
### Q: Aspose.Tasks에서 여러 필터를 결합할 수 있나요?
A: 물론 여러 필터를 결합하여 Aspose.Tasks에서 데이터 추출 및 분석을 세분화할 수 있습니다.
### Q: Aspose.Tasks는 추가 지원을 위한 문서를 제공합니까?
 A: 그렇습니다, 당신은 포괄적인 내용을 참조할 수 있습니다[선적 서류 비치](https://reference.aspose.com/tasks/net/) 자세한 안내는 Aspose.Tasks에서 제공됩니다.
### Q: Aspose.Tasks 사용자에게 기술 지원이 제공됩니까?
 A: 예, 다음을 통해 기술 지원을 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 귀하가 직면하는 모든 질문이나 문제에 대해.