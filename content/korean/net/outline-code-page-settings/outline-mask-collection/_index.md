---
title: Aspose.Tasks를 사용하여 MS 프로젝트 개요 마스크 마스터하기
linktitle: Aspose.Tasks의 윤곽선 마스크 컬렉션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 컬렉션 개요 마스크를 조작하는 방법을 알아보세요. 이 포괄적인 튜토리얼을 통해 생산성을 향상하세요.
type: docs
weight: 15
url: /ko/net/outline-code-page-settings/outline-mask-collection/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 Microsoft Project의 아웃라인 마스크 기능을 활용하고 싶으십니까? 당신은 올바른 장소에 왔습니다! 이 포괄적인 튜토리얼에서는 프로세스를 단계별로 안내하여 프로젝트에서 윤곽선 마스크를 효과적으로 조작하는 방법을 확실하게 이해할 수 있도록 도와드립니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 가이드는 워크플로를 최적화하는 데 필요한 지식과 기술을 제공합니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 Aspose.Tasks 설치
개발 환경에 Aspose.Tasks for .NET이 설치되어 있는지 확인하세요. Aspose 웹사이트에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
### 2. C# 및 .NET Framework에 대한 기본 지식
이 튜토리얼에서는 C# 프로그래밍 언어와 .NET Framework를 모두 활용하므로 숙지하세요.
### 3. 마이크로소프트 프로젝트 파일
테스트용으로 Microsoft Project 파일(MPP)을 준비하세요. 기존 파일을 사용하거나 실험을 위해 새 파일을 만들 수 있습니다.
## 네임스페이스 가져오기
필요한 네임스페이스를 C# 프로젝트로 가져오는 것부터 시작해 보겠습니다. 이 단계에서는 Aspose.Tasks for .NET에서 제공하는 필수 클래스와 기능에 액세스할 수 있는지 확인합니다.

코드 파일 시작 부분에 다음 네임스페이스를 추가합니다.
```csharp
    using Aspose.Tasks;
    using System;
    
```
이제 제공된 예제를 여러 단계로 나누고 각 단계를 자세히 설명하겠습니다.
## 1단계: 프로젝트 개체 초기화
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 여기서는 새로운 인스턴스를 생성합니다.`Project` 클래스를 선택하고 "OutlineValues2010.mpp"라는 기존 Microsoft Project 파일을 로드합니다.
## 2단계: 개요 코드에 액세스
```csharp
var outline = project.OutlineCodes[0];
```
프로젝트에서 개요 코드에 액세스합니다. 개요 코드는 작업을 분류하고 구성할 수 있는 Microsoft Project의 사용자 정의 필드입니다.
## 3단계: 윤곽선 마스크 지우기
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
이 단계를 수행하면 계속 진행하기 전에 기존 윤곽선 마스크가 모두 지워집니다.
## 4단계: 윤곽선 마스크 만들기
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
새로운 윤곽선 마스크를 생성하고 해당 유형을 지정합니다. 이 예에서는 유효한 윤곽선 마스크와 잘못된 윤곽선 마스크를 만듭니다.
## 5단계: 마스크 삽입 및 편집
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
여기서는 컬렉션에 잘못된 마스크를 삽입하고 해당 인덱스를 사용하여 마스크 길이를 편집합니다.
## 6단계: 마스크 제거
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
인덱스를 기반으로 컬렉션에서 잘못된 마스크를 제거합니다.
## 7단계: 마스크 반복
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
이 루프는 컬렉션의 각 윤곽선 마스크를 반복하고 길이, 수준, 구분 기호 및 유형과 같은 속성을 인쇄합니다.
## 8단계: 다른 프로젝트에 마스크 복사
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
마지막으로 한 프로젝트에서 다른 프로젝트로 아웃라인 마스크를 복사하여 여러 프로젝트 간의 일관성을 보장합니다.
## 결론
축하해요! .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 컬렉션 개요 마스크를 조작하는 방법을 성공적으로 배웠습니다. 이 튜토리얼을 따르면 이제 프로젝트에서 윤곽선 마스크를 효율적으로 관리하여 궁극적으로 생산성과 작업 흐름을 향상시킬 수 있는 기술을 갖추게 됩니다.
## FAQ
### Q1: 다양한 버전의 Microsoft Project 파일과 함께 Aspose.Tasks for .NET을 사용할 수 있습니까?
A: 예, Aspose.Tasks for .NET은 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Q2: .NET용 Aspose.Tasks는 .NET Core와 호환됩니까?
A: 예, .NET용 Aspose.Tasks는 .NET Core와 호환되므로 크로스 플랫폼 애플리케이션에서 사용할 수 있습니다.
### Q3: 내 프로젝트 요구 사항에 따라 윤곽선 마스크의 속성을 사용자 정의할 수 있습니까?
답: 물론이죠! 특정 프로젝트 요구 사항에 맞게 길이, 레벨, 구분 기호 및 유형을 조정하여 윤곽선 마스크를 사용자 정의할 수 있습니다.
### Q4: .NET용 Aspose.Tasks는 문서와 지원을 제공합니까?
A: 예, Aspose.Tasks for .NET은 웹사이트와 웹사이트를 통해 포괄적인 문서와 전담 지원을 제공합니다.[포럼](https://forum.aspose.com/c/tasks/15).
### Q5: Aspose.Tasks for .NET에 사용할 수 있는 무료 평가판이 있습니까?
 A: 예, Aspose.Tasks for .NET의 무료 평가판에 액세스할 수 있습니다.[웹사이트](https://releases.aspose.com/tasks/net/). 구매하기 전에 특징과 기능을 살펴보세요.