---
title: Aspose.Tasks의 마스터 확장 속성 정의 MS 프로젝트
linktitle: Aspose.Tasks의 확장된 속성 정의 컬렉션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project에서 확장된 속성 정의를 관리하는 방법을 알아보세요. 프로젝트 데이터를 손쉽게 사용자 정의하고 향상하세요.
type: docs
weight: 14
url: /ko/net/tasks-project-management/extended-attribute-definition-collection/
---
## 소개
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 Microsoft Project에서 확장된 속성 정의로 작업하는 방법을 살펴보겠습니다. 확장된 속성은 프로젝트 데이터를 사용자 정의하고 향상시키는 유연한 방법을 제공하므로 사용자는 기본적으로 제공되는 표준 필드 외에 추가 필드를 추가할 수 있습니다. Aspose.Tasks를 사용하면 이러한 확장된 속성을 쉽게 관리하여 프로젝트 관리 요구 사항에 맞게 조정할 수 있습니다.
## 전제조건
계속하기 전에 다음 필수 구성 요소가 설치되어 있는지 확인하세요.
- [.넷 프레임 워크](https://dotnet.microsoft.com/download)
-  .NET 라이브러리용 Aspose.Tasks. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).

## 네임스페이스 가져오기
먼저 .NET 프로젝트의 Aspose.Tasks 클래스 및 메서드에 액세스하려면 필요한 네임스페이스를 가져와야 합니다. 다음과 같이하세요:
## 1단계: .NET 프로젝트 열기
Visual Studio 등 원하는 IDE에서 .NET 프로젝트를 엽니다.
## 2단계: Aspose.Tasks 네임스페이스 추가
Aspose.Tasks 네임스페이스를 가져오려면 코드 파일 시작 부분에 다음 줄을 추가하세요.
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

이제 포괄적인 이해를 위해 제공된 코드 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 파일 로드
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## 2단계: 기존 확장 속성 정의 지우기(선택 사항)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## 3단계: 작업에 대한 확장된 속성 정의 생성 및 추가
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## 4단계: 작업 확장 속성 반복
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## 5단계: 리소스에 대한 확장된 속성 정의 생성 및 추가
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## 6단계: 리소스 확장 속성 정의 삽입
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## 7단계: 인덱스별로 확장된 속성 제거
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 Microsoft Project에서 확장된 속성 정의 작업에 대한 기본 사항을 다루었습니다. 다음 단계를 수행하면 프로젝트 관리 요구 사항에 맞게 확장된 속성을 효율적으로 관리하고 사용자 정의할 수 있습니다.
## FAQ
### Q: 기존 확장 특성 정의를 수정할 수 있습니까?
A: 예, 기존 확장 속성 정의를 수정하거나 필요에 따라 새 정의를 생성할 수 있습니다.
### Q: 모든 버전의 Microsoft Project에서 확장된 특성이 지원됩니까?
A: 예, 확장된 특성은 최신 버전을 포함하여 대부분의 Microsoft Project 버전에서 지원됩니다.
### Q: 확장된 속성을 사용하여 사용자 정의 필드를 계산할 수 있습니까?
A: 물론, 확장된 속성을 사용하여 정의한 특정 기준에 따라 사용자 정의 필드를 계산할 수 있습니다.
### Q: Aspose.Tasks는 다른 .NET 프레임워크와 호환됩니까?
A: Aspose.Tasks는 다양한 .NET 프레임워크와 호환되므로 유연성과 통합 용이성을 보장합니다.
### Q: Aspose.Tasks에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지원을 받고 문서를 살펴보세요[여기](https://reference.aspose.com/tasks/net/).