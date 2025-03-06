---
title: Aspose.Tasks에 CSS 저장 인수
linktitle: Aspose.Tasks에 CSS 저장 인수
second_title: Aspose.태스크 .NET API
description: HTML 출력을 사용자 정의하기 위해 .NET용 Aspose.Tasks에 CSS 인수를 저장하는 방법을 알아보세요. 맞춤형 CSS 설정으로 프레젠테이션을 향상하세요.
weight: 20
url: /ko/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에 CSS 저장 인수

## 소개

이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 CSS 인수를 저장하는 과정을 자세히 살펴보겠습니다. CSS(Cascading Style Sheets)는 HTML 요소의 표현을 정의하는 데 중요합니다. Aspose.Tasks를 사용하면 이러한 CSS 속성을 효율적으로 조작하고 저장할 수 있습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  설치: .NET용 Aspose.Tasks를 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/tasks/net/).

2. 기본 지식: C# 및 .NET 개발 환경에 대해 잘 아는 것이 좋습니다.

## 네임스페이스 가져오기

시작하려면 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## 1단계: CSS 저장 콜백 정의

먼저 CSS 파일 저장을 처리하기 위해 CSS 저장 콜백 메소드를 정의합니다.

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // 여기에 CSS 저장 논리를 구현하세요.
    }
}
```

## 2단계: 글꼴 및 이미지 저장 콜백 구현

다음으로 글꼴 및 이미지 저장 콜백 메서드를 유사하게 구현합니다.

```csharp
public void FontSaving(FontSavingArgs args)
{
    // 여기에 글꼴 저장 논리를 구현하세요.
}

public void ImageSaving(ImageSavingArgs args)
{
    // 여기에 이미지 저장 논리를 구현하세요.
}
```

## 3단계: 저장 옵션 구성

이제 구현된 콜백을 활용하도록 HTML 저장 옵션을 구성합니다.

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //HTML 저장 옵션 구성
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 4단계: 사용자 정의된 CSS로 프로젝트 저장

마지막으로 사용자 정의된 CSS 설정으로 프로젝트를 저장합니다.

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 CSS 인수를 저장하는 방법을 살펴보았습니다. CSS 저장 콜백을 정의하고 HTML 저장 옵션을 구성함으로써 요구 사항에 따라 CSS 속성을 효율적으로 조작할 수 있습니다.

## 자주 묻는 질문

### Q1: .NET용 Aspose.Tasks란 무엇입니까?

A1: Aspose.Tasks for .NET은 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있게 해주는 강력한 .NET API입니다.

### Q2: Aspose.Tasks로 HTML 파일을 저장할 때 CSS 속성을 사용자 정의할 수 있나요?

A2: 예, CSS 저장 콜백을 정의하여 필요에 따라 CSS 속성을 사용자 정의할 수 있습니다.

### Q3: Aspose.Tasks for .NET은 모든 버전의 Microsoft Project 파일과 호환됩니까?

A3: Aspose.Tasks for .NET은 다양한 버전의 Microsoft Project 파일을 지원하여 다양한 환경에서의 호환성을 보장합니다.

### Q4: .NET용 Aspose.Tasks에 대한 포괄적인 문서는 어디에서 찾을 수 있습니까?

A4: 다음을 참조할 수 있습니다.[선적 서류 비치](https://reference.aspose.com/tasks/net/) 자세한 정보와 예시를 확인하세요.

### Q5: Aspose.Tasks for .NET은 개발자를 지원합니까?

 A5: 예, Aspose.Tasks 커뮤니티에서 지원을 받을 수 있습니다.[법정](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
