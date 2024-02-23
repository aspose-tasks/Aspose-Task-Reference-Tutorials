---
title: Aspose.Tasks에서 이미지 저장 처리
linktitle: Aspose.Tasks에서 이미지 저장 처리
second_title: Aspose.태스크 .NET API
description: 단계별 지침을 사용하여 .NET용 Aspose.Tasks에서 이미지 저장을 처리하는 방법을 알아보세요. 이미지 저장 기능을 .NET 애플리케이션에 원활하게 통합합니다.
type: docs
weight: 10
url: /ko/net/advanced-concepts/image-saving/
---
## 소개

이 튜토리얼에서는 Aspose.Tasks for .NET에서 이미지 저장을 처리하는 과정을 자세히 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 API입니다. 프로젝트 파일 작업 시 일반적인 작업 중 하나는 차트, 그래프 또는 기타 시각적 요소가 포함될 수 있는 이미지를 저장해야 한다는 것입니다. 우리는 프로세스를 단계별로 분석하여 전체적으로 명확성과 이해를 보장합니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Visual Studio: 시스템에 Visual Studio가 설치되어 있는지 확인하세요.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C#의 기본 이해: C# 프로그래밍 언어 기본 사항에 익숙해집니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 프로젝트로 가져오겠습니다.

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1단계: 프로젝트 객체 생성

Microsoft Project 파일에서 Project 객체를 생성하는 것부터 시작하세요.

```csharp
var project = new Project("Project1.mpp");
```

## 2단계: 저장 옵션 정의

페이지 및 기타 설정을 지정하여 프로젝트의 저장 옵션을 정의합니다.

```csharp
var options = GetSaveOptions(1);
```

## 3단계: 프로젝트를 HTML로 저장

지정된 옵션을 사용하여 프로젝트를 HTML로 저장합니다.

```csharp
project.Save("document_out.html", options);
```

## 4단계: 이미지 저장 콜백 구현

이미지 저장을 처리하려면 ImageSavingCallback 인터페이스를 구현하십시오.

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // 이미지 저장 논리가 여기에 표시됩니다.
    }
}
```

## 5단계: 지정된 디렉터리에 이미지 저장

ImageSaving 메서드 내에서 이미지를 원하는 디렉터리에 저장하는 논리를 지정합니다.

```csharp
if (args.FileName.EndsWith("png"))
{
    // 중첩된 리소스 저장
}
else
{
    // 일반 자원 절약
}
```

## 6단계: 저장 옵션 지정

CSS, 글꼴, 이미지에 대한 콜백을 포함한 저장 옵션을 지정합니다.

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // 여기서 저장 옵션을 지정하세요.
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 결론

결론적으로 Aspose.Tasks for .NET에서 이미지 저장을 처리하려면 저장 옵션을 정의하고 콜백을 구현하여 저장 프로세스를 효과적으로 관리해야 합니다. 이 자습서에 설명된 단계를 따르면 이미지 저장 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks를 사용하여 HTML 이외의 다른 형식의 프로젝트 파일을 조작할 수 있습니까?

A1: 예, Aspose.Tasks는 PDF, XLSX 및 MPP와 같은 다양한 형식을 지원합니다.

### Q2: Aspose.Tasks는 클라우드 스토리지 통합을 지원합니까?

A2: 예, Aspose.Tasks는 Amazon S3 및 Google Drive와 같은 널리 사용되는 클라우드 스토리지 서비스와 작업하기 위한 API를 제공합니다.

### Q3: Aspose.Tasks는 .NET Core와 호환됩니까?

A3: 예, Aspose.Tasks는 .NET Core와 호환되므로 크로스 플랫폼 애플리케이션을 개발할 수 있습니다.

### Q4: 저장된 이미지의 모양을 사용자 정의할 수 있나요?

A4: 예, 콜백 메서드 내에서 이미지 저장 논리를 수정하여 저장된 이미지의 모양을 사용자 지정할 수 있습니다.

### Q5: Aspose.Tasks는 평가 목적으로 평가판을 제공합니까?

 A5: 예, Aspose.Tasks의 무료 평가판을 얻을 수 있습니다.[여기](https://releases.aspose.com/).