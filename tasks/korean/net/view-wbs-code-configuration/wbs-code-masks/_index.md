---
title: Aspose.Tasks .NET의 단계별 WBS 코드 구성
linktitle: Aspose.Tasks에서 WBS 코드 마스크 구성
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks를 사용하여 .NET 프로젝트에서 단계별 WBS 코드 마스크 구성을 살펴보세요. 손쉽게 프로젝트 관리 기능을 향상하세요.
weight: 14
url: /ko/net/view-wbs-code-configuration/wbs-code-masks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks .NET의 단계별 WBS 코드 구성

## 소개
Aspose.Tasks for .NET은 개발자가 .NET 애플리케이션에서 프로젝트 관리 데이터를 효율적으로 조작할 수 있도록 지원하는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 WBS(작업 분할 구조) 코드 마스크를 구성하는 프로세스를 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET 라이브러리용 Aspose.Tasks: 다음에서 라이브러리를 다운로드하고 설치하세요.[.NET 문서용 Aspose.Tasks](https://reference.aspose.com/tasks/net/).
- 개발 환경: 작동하는 .NET 개발 환경이 설정되어 있는지 확인하세요.
- 문서 디렉터리: 프로젝트 파일을 저장할 시스템의 디렉터리를 선택합니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Tasks 작업에 필요한 네임스페이스를 포함합니다.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## 1단계: 프로젝트 인스턴스 생성
새 프로젝트 인스턴스를 생성하여 시작합니다.
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## 2단계: WBS 코드 정의 정의
프로젝트에 대한 WBS 코드 정의를 설정합니다.
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 3단계: WBS 코드 마스크 추가
WBS 코드 마스크를 정의하고 프로젝트에 추가합니다.
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## 4단계: 작업 생성
프로젝트에 작업을 추가합니다.
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## 5단계: 다시 계산
WBS 코드가 올바르게 적용되도록 프로젝트를 다시 계산합니다.
```csharp
project.Recalculate();
```
## 6단계: WBS 마스크 정보 표시
WBS 마스크에 대한 정보를 콘솔에 출력합니다.
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## 7단계: 프로젝트 저장
추가된 WBS 코드를 사용하여 프로젝트를 저장합니다.
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
축하해요! Aspose.Tasks 프로젝트에서 WBS 코드 마스크를 성공적으로 구성했습니다.
## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 WBS 코드 마스크를 구성하는 단계별 프로세스를 살펴보았습니다. 이 강력한 라이브러리는 개발자에게 .NET 애플리케이션 내에서 프로젝트 관리 기능을 향상시킬 수 있는 원활한 방법을 제공합니다.

## FAQ
### Aspose.Tasks를 무료로 사용할 수 있나요?
 Aspose.Tasks는 다운로드할 수 있는 무료 평가판을 제공합니다.[여기](https://releases.aspose.com/).
### 추가 지원은 어디서 찾을 수 있나요?
 방문하다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지역 사회 지원을 위해.
### 임시 라이센스는 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### 자세한 문서가 제공되나요?
 예, 포괄적인 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).
### Aspose.Tasks는 어디서 구매할 수 있나요?
 Aspose.Tasks 구매[여기](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
