---
title: Aspose.Tasks로 MS 프로젝트 개요 값 마스터하기
linktitle: Aspose.Tasks에서 개요 값 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 개요 값을 효율적으로 관리하는 방법을 알아보세요. 프로젝트 개요를 쉽게 사용자 정의하세요.
weight: 16
url: /ko/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks로 MS 프로젝트 개요 값 마스터하기

## 소개
이 튜토리얼에서는 .NET용 Aspose.Tasks 라이브러리를 사용하여 Microsoft Project 개요 값을 관리하는 방법을 살펴보겠습니다. Aspose.Tasks를 사용하면 개요 코드를 쉽게 조작하고, 새로운 개요 값을 생성하고, 요구 사항에 따라 프로젝트 개요를 사용자 지정할 수 있습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  .NET용 Aspose.Tasks 설치: 다음에서 .NET용 Aspose.Tasks 라이브러리를 다운로드하여 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
2. 개발 환경: Visual Studio와 같이 .NET 프레임워크와 호환되는 개발 환경이 설정되어 있는지 확인하세요.
3. C# 프로그래밍의 기본 이해: Aspose.Tasks 라이브러리 작업에 C#을 사용하므로 C# 프로그래밍 언어 기본 사항에 익숙해지세요.

## 네임스페이스 가져오기
필요한 네임스페이스를 C# 코드로 가져오는 것부터 시작하세요.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 1단계: 프로젝트 파일 로드
```csharp
// 문서 디렉터리의 경로입니다.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
이 단계에서는 새 Project 개체를 초기화하고 지정된 디렉터리에서 Microsoft Project 파일을 로드합니다.
## 2단계: 개요 코드 정의 정의
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
여기서는 두 개의 OutlineCodeDefinition 개체를 정의하고 이를 프로젝트의 OutlineCodes 컬렉션에 추가합니다.
## 3단계: 윤곽선 마스크 정의
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
이 단계에서는 개요 코드 정의를 위한 OutlineMask를 설정합니다.
## 4단계: 개요 값 생성
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
이 단계에서는 두 개의 OutlineValue 개체를 만들고 값, 값 ID, 유형, 설명, 축소 상태 등의 속성을 설정합니다.

## 결론
.NET용 Aspose.Tasks를 사용하여 MS 프로젝트 개요 값을 관리하는 것은 제공된 기능을 통해 간단합니다. 이 튜토리얼에 설명된 단계를 따르면 개요 코드와 값을 효율적으로 조작하여 필요에 따라 프로젝트 개요를 사용자 정의할 수 있습니다.
## FAQ
### Q: Aspose.Tasks를 다른 .NET 프레임워크와 함께 사용할 수 있나요?
A: 예, Aspose.Tasks는 다양한 .NET 프레임워크와 호환되므로 개발 환경의 유연성을 보장합니다.
### Q: Aspose.Tasks에 사용할 수 있는 평가판이 있나요?
 A: 예, Aspose.Tasks의 무료 평가판 버전에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?
 A: 지원 및 지원을 받으려면 Aspose.Tasks 포럼을 방문하세요.[여기](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks의 임시 라이선스를 구매할 수 있나요?
A: 예, Aspose.Tasks에 대한 임시 라이선스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks에 대한 자세한 문서는 어디서 찾을 수 있나요?
 A: 사용 가능한 종합 문서를 참조할 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
