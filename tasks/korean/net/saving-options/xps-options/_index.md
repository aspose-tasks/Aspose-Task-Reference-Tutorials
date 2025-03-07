---
title: Aspose.Tasks를 사용하여 MSP를 XPS 옵션으로 변환
linktitle: Aspose.Tasks에 대한 XPS 옵션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일을 XPS 형식으로 변환하는 방법을 알아보세요. 간편한 통합, 강력한 기능.
weight: 21
url: /ko/net/saving-options/xps-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MSP를 XPS 옵션으로 변환

## 소개
MSP(Microsoft Project)는 프로젝트 관리에 널리 사용되는 도구로, 프로젝트 활동의 계획, 추적 및 보고를 용이하게 합니다. Aspose.Tasks for .NET은 MSP 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 기능을 제공하여 개발자가 프로젝트 관리와 관련된 다양한 작업을 자동화할 수 있도록 해줍니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 활용하여 MSP 문서에서 XPS 파일을 생성하는 방법을 살펴보고 필요한 단계와 고려 사항을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 Aspose.Tasks 설치: 다음에서 .NET용 Aspose.Tasks를 다운로드하여 설치하세요.[웹사이트](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 문서: XPS 형식으로 변환하려는 Microsoft Project 문서(.mpp)를 준비합니다.

## 네임스페이스 가져오기
프로세스를 시작하려면 .NET 프로젝트에서 필수 네임스페이스를 가져옵니다.
```csharp

using Aspose.Tasks.Saving;
```

## 1단계: 문서 디렉터리 경로 설정
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` MSP 문서가 있는 경로를 사용하세요.
## 2단계: MSP 문서 로드
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
 여기서는 새로운 것을 초기화합니다.`Project` MSP 문서의 경로를 전달하여 개체를 만듭니다.
## 3단계: XPS 저장 옵션 만들기
```csharp
// XPS 저장 옵션 생성 및 매개변수 조정
var options = new XpsOptions
{
    RenderMetafileAsBitmap = true
};
```
 이 단계에서는 인스턴스화합니다.`XpsOptions`매개변수를 구성합니다. 환경`RenderMetafileAsBitmap` 에게`true` 메타파일의 적절한 렌더링을 보장합니다.
## 4단계: 문서를 XPS로 저장
```csharp
project.Save(DataDir + "UseSvgOptions_out.xps", options);
```
 마지막으로 우리는`Save` 에 대한 방법`Project` 객체, 출력 파일 경로 및 이전에 구성한 경로 지정`XpsOptions`.

## 결론
결론적으로 Aspose.Tasks for .NET은 프로그래밍 방식으로 Microsoft Project 문서를 XPS 형식으로 변환하는 프로세스를 단순화합니다. 이 튜토리얼에 설명된 단계를 따르면 개발자는 이 기능을 .NET 애플리케이션에 원활하게 통합하여 프로젝트 관리 워크플로를 쉽게 향상시킬 수 있습니다.
## FAQ
### Q: .NET용 Aspose.Tasks가 복잡한 MSP 파일을 처리할 수 있습니까?
A: 예, .NET용 Aspose.Tasks는 복잡한 Microsoft Project 파일을 효율적으로 처리하여 다양한 형식으로 정확하게 변환할 수 있습니다.
### Q: Aspose.Tasks for .NET에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음 사이트에서 무료 평가판을 구할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: .NET용 Aspose.Tasks는 XPS 외에 다른 출력 형식을 지원합니까?
A: 예, Aspose.Tasks for .NET은 PDF, HTML, PNG, JPEG 등 다양한 출력 형식을 지원합니다.
### Q: 출력 파일의 렌더링 옵션을 사용자 정의할 수 있습니까?
A: 물론입니다. Aspose.Tasks for .NET은 요구 사항에 따라 렌더링 매개변수를 사용자 정의할 수 있는 광범위한 옵션을 제공합니다.
### Q: Aspose.Tasks for .NET에 대한 추가 지원은 어디서 찾을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) .NET용 Aspose.Tasks에 관한 질문이나 지원이 필요합니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
