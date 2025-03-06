---
title: Aspose.Tasks .NET의 개요 코드 정의 컬렉션
linktitle: Aspose.Tasks의 개요 코드 정의 컬렉션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project 문서에서 개요 코드 정의를 조작하는 방법을 알아보세요. 프로젝트 데이터를 손쉽게 분류하세요.
type: docs
weight: 13
url: /ko/net/outline-code-page-settings/outline-code-definition-collection/
---
## 소개
Aspose.Tasks는 Microsoft Project 문서를 쉽고 효율적으로 조작하도록 설계된 강력한 .NET 라이브러리입니다. 주요 기능 중 하나는 개요 코드 정의로 작업하여 사용자가 프로젝트 데이터를 효과적으로 구성하고 분류할 수 있는 기능입니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 개요 코드 정의로 작업하는 방법을 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
1. C#에 대한 기본 이해: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.
2. Visual Studio: Visual Studio 또는 기타 선호하는 C# 개발 환경을 설치합니다.
3.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).

## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 가져와야 합니다.
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 1단계: Microsoft Project 문서 로드
먼저 Microsoft Project 문서를 로드하여 개요 코드 정의 작업을 시작합니다.
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## 2단계: 개요 코드 정의에 액세스
이제 프로젝트 내의 개요 코드 정의에 액세스해 보겠습니다.
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## 3단계: 사용자 정의 개요 코드 정의 추가
다음과 같이 사용자 정의 개요 코드 정의를 추가할 수 있습니다.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## 4단계: 개요 코드 정의 수정
기존 개요 코드 정의를 쉽게 수정합니다.
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## 5단계: 개요 코드 정의 제거
더 이상 필요하지 않은 경우 개요 코드 정의를 제거합니다.
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## 6단계: 변경 사항 저장
마지막으로 프로젝트 문서의 변경 사항을 저장합니다.
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## 결론
결론적으로 Aspose.Tasks for .NET은 Microsoft Project 문서의 개요 코드 정의를 관리하기 위한 포괄적인 기능을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 개요 코드 정의를 효율적으로 조작하여 프로젝트 데이터를 효과적으로 구성하고 분류할 수 있습니다.
## FAQ
### Q: 단일 프로젝트에 여러 개요 코드 정의를 추가할 수 있습니까?
 A: 예, 요구 사항에 따라 프로젝트에 여러 개요 코드 정의를 추가할 수 있습니다. 간단히`Add` 포함하려는 각 정의에 대한 메서드입니다.
### Q: 프로젝트에서 모든 개요 코드 정의를 한 번에 제거할 수 있습니까?
 A: 예, 다음을 사용하여 프로젝트에서 모든 개요 코드 정의를 지울 수 있습니다.`Clear` 방법.
### Q: 읽기 전용 개요 코드 정의를 수정하려고 하면 어떻게 됩니까?
A: 개요 코드 정의가 읽기 전용인 경우 직접 수정할 수 없습니다. 수정을 시도하기 전에 읽기 전용 상태를 확인해야 합니다.
### Q: 프로젝트에 추가할 수 있는 개요 코드 정의 수에 제한이 있습니까?
A: .NET용 Aspose.Tasks는 프로젝트에 추가할 수 있는 개요 코드 정의 수에 특정 제한을 두지 않습니다. 그러나 많은 수의 정의로 작업할 때는 성능에 미치는 영향을 고려하십시오.
### Q: 개요 코드 정의를 사용하여 사용자 지정 기준에 따라 작업을 그룹화할 수 있습니까?
A: 예, 개요 코드 정의를 사용하면 사용자 정의 기준에 따라 작업을 분류할 수 있으므로 프로젝트 데이터 구성에 유연성이 제공됩니다.## 완전한 소스 코드