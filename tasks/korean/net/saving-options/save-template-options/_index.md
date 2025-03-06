---
title: Aspose.Tasks를 사용하여 MS 프로젝트 파일을 템플릿으로 저장
linktitle: Aspose.Tasks에 대한 템플릿 옵션 저장
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET을 사용하여 Microsoft Project 파일을 템플릿으로 저장하는 방법을 알아보세요. 효율적인 프로젝트 관리를 위해 템플릿 설정을 사용자 정의하세요.
weight: 18
url: /ko/net/saving-options/save-template-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MS 프로젝트 파일을 템플릿으로 저장

## 소개
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 템플릿을 저장하는 과정을 안내합니다. 템플릿은 나중에 사용할 수 있도록 프로젝트 구조와 설정을 표준화하는 데 유용합니다. 프로젝트를 템플릿으로 저장하고 그 과정에서 해당 속성을 조정하는 방법을 보여 드리겠습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: .NET 라이브러리용 Aspose.Tasks가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
2. C# 프로그래밍 지식: 제공된 코드 조각을 이해하고 구현하려면 C# 프로그래밍에 대한 기본 지식이 필요합니다.
3. Microsoft Project 파일: 템플릿으로 저장할 Microsoft Project 파일(MPP 형식)을 준비합니다.

## 네임스페이스 가져오기
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 1단계: 프로젝트 로드
먼저 템플릿으로 저장하려는 Microsoft Project 파일(.mpp)을 로드해야 합니다.
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 2단계: 프로젝트 파일 정보 가져오기
형식 등 로드된 프로젝트 파일에 대한 정보를 검색합니다.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## 3단계: 템플릿 저장 옵션 구성
템플릿 저장 옵션을 생성하고 요구 사항에 따라 해당 속성을 구성합니다. 이러한 옵션을 사용하면 템플릿에서 제거해야 하는 데이터를 사용자 정의할 수 있습니다.
```csharp
var options = new SaveTemplateOptions
{
	// 프로젝트 템플릿에서 모든 고정 비용 제거
	RemoveFixedCosts = true,
	// 프로젝트 템플릿에서 모든 실제 값을 제거합니다.
	RemoveActualValues = true,
	// 프로젝트 템플릿에서 자원 요율 제거
	RemoveResourceRates = true,
	// 프로젝트 템플릿에서 모든 기준 값을 제거합니다.
	RemoveBaselineValues = true
};
```
## 4단계: 프로젝트를 템플릿으로 저장
지정된 옵션을 사용하여 프로젝트를 템플릿으로 저장합니다.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## 5단계: 템플릿 파일 정보 가져오기
형식 등 저장된 템플릿 파일에 대한 정보를 검색합니다.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
축하해요! Aspose.Tasks for .NET을 사용하여 템플릿을 성공적으로 저장하고 필요에 따라 해당 속성을 사용자 정의했습니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 파일을 템플릿으로 저장하는 방법을 살펴보았습니다. 템플릿은 프로젝트 구조와 설정을 표준화하고 향후 프로젝트 생성을 간소화하는 데 유용합니다.
## FAQ
### Q: 템플릿에서 제거할 데이터를 사용자 정의할 수 있습니까?
A: 예, 고정 비용, 실제 값, 자원 요율, 기준 값과 같은 특정 데이터를 제거하도록 템플릿 저장 옵션을 구성할 수 있습니다.
### Q: Aspose.Tasks for .NET은 모든 버전의 Microsoft Project와 호환됩니까?
A: Aspose.Tasks for .NET은 다양한 Microsoft Project 버전과의 광범위한 호환성을 제공하여 원활한 통합과 기능을 보장합니다.
### Q: 기존 프로젝트에 템플릿을 적용할 수 있나요?
A: 예, 필요에 따라 템플릿 파일을 로드하고 현재 프로젝트와 병합하여 기존 프로젝트에 템플릿을 적용할 수 있습니다.
### Q: .NET용 Aspose.Tasks는 크로스 플랫폼 개발을 지원합니까?
A: Aspose.Tasks for .NET은 주로 Windows 플랫폼에서 실행되는 .NET 프레임워크 애플리케이션용으로 설계되었습니다.
### Q: Aspose.Tasks for .NET에 대한 기술 지원이 제공됩니까?
 A: 예, Aspose.Tasks 커뮤니티에서 기술 지원과 지침을 구할 수 있습니다.[포럼](https://forum.aspose.com/c/tasks/15)또는 지원팀에 직접 문의하세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
