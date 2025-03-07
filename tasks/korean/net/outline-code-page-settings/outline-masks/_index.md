---
title: Aspose.Tasks에서 Microsoft 프로젝트 개요 마스크 마스터하기
linktitle: Aspose.Tasks에서 윤곽선 마스크 작업
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 프로그래밍 방식으로 Microsoft Project 파일을 작업하는 방법을 알아보세요. 아웃라인 마스크를 효율적으로 마스터하세요.
weight: 14
url: /ko/net/outline-code-page-settings/outline-masks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 Microsoft 프로젝트 개요 마스크 마스터하기

## 소개
프로젝트 관리 및 작업 추적 영역에서 Microsoft Project는 초석 도구입니다. 그러나 프로젝트 파일을 프로그래밍 방식으로 조작하고 관리하는 경우 Aspose.Tasks for .NET이 강력한 솔루션으로 등장합니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일 작업의 특정 측면인 윤곽선 마스크 처리에 대해 자세히 살펴보겠습니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
- C# 프로그래밍 언어에 대한 기본 이해.
- .NET 프레임워크와 함께 Visual Studio를 설치했습니다.
- Microsoft Project 파일 형식에 익숙합니다.
-  .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치했습니다. 그렇지 않다면 얻을 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
- 프로젝트 관리 개념에 대한 기본적인 이해.
## 네임스페이스 가져오기
자습서를 진행하기 전에 C# 파일에 필요한 네임스페이스를 가져옵니다.
```csharp
    
```
## 1단계: 프로젝트 파일 로드
첫 번째 단계는 Aspose.Tasks 라이브러리를 사용하여 Microsoft Project 파일을 로드하는 것입니다.
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## 2단계: 개요 코드 정의
다음으로 프로젝트의 개요 코드 정의를 정의합니다.
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
project.OutlineCodes.Add(outline);
```
## 3단계: 윤곽선 마스크 정의
이제 개요 코드에 대한 개요 마스크를 만듭니다.
```csharp
var mask = new OutlineMask();
// 마스크 종류 설정
mask.Type = MaskType.Characters;
// 코드 값의 구분 기호 설정
mask.Separator = "/";
// 마스크 레벨 설정
mask.Level = 1;
// 개요 코드 값의 최대 길이(문자)를 설정합니다. 길이가 정의되지 않은 경우 0입니다.
mask.Length = 2;
// 정의에 마스크 추가
outline.Masks.Add(mask);
```
## 4단계: 개요 값 정의
개요 코드의 개요 값을 정의합니다.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
이 단계별 가이드에서는 Aspose.Tasks for .NET에서 윤곽선 마스크로 작업하는 과정을 다룹니다. 다음 단계를 수행하면 프로그래밍 방식으로 Microsoft Project 파일의 윤곽선 마스크를 효과적으로 관리할 수 있습니다.

## 결론
프로그래밍 방식으로 Microsoft Project 파일 조작을 마스터하면 프로젝트 관리 자동화의 가능성이 넓어집니다. .NET용 Aspose.Tasks를 사용하면 윤곽선 마스크 처리가 간소화되고 효율적이 되어 개발자가 프로젝트 추적 및 관리를 위한 맞춤형 솔루션을 만들 수 있습니다.
## FAQ
### Q: Aspose.Tasks for .NET을 다른 프로젝트 관리 도구와 함께 사용할 수 있나요?
답: 물론이죠! Aspose.Tasks는 주로 Microsoft Project 파일에 중점을 두지만 다양한 프로젝트 관리 형식과의 상호 운용성을 제공합니다.
### Q: Aspose.Tasks는 Microsoft Project 파일 읽기 및 쓰기를 모두 지원합니까?
A: 예, Aspose.Tasks를 사용하면 개발자는 Microsoft Project 파일을 읽고 쓸 수 있어 포괄적인 조작이 가능합니다.
### Q: 도움을 구할 수 있는 Aspose.Tasks 커뮤니티 포럼이 있나요?
A: 실제로, 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 질문하고, 아이디어를 공유하고, 다른 사용자와 상호 작용합니다.
### Q: 구매하기 전에 .NET용 Aspose.Tasks를 사용해 볼 수 있나요?
 답: 물론이죠! Aspose.Tasks의 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 임시 라이선스는 어디서 얻을 수 있나요?
 A: 평가 또는 테스트 목적으로 임시 라이선스가 필요한 경우 임시 라이선스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
