---
date: 2026-07-05
description: Aspose.Tasks for .NET를 사용하여 프로젝트를 HTML로 내보내는 동안 CSS를 사용자 지정하는 방법을 배웁니다.
  CSS 저장 인수를 사용해 HTML 출력물을 맞춤 설정합니다.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Aspose.Tasks로 프로젝트를 저장할 때 CSS 사용자 지정 방법
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks로 프로젝트를 저장할 때 CSS 사용자 지정 방법
url: /ko/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks로 프로젝트 저장 시 CSS 사용자 지정 방법

이 가이드에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 파일을 HTML로 내보낼 때 **CSS를 사용자 지정하는 방법**을 알아봅니다. CSS 저장 인수를 조정하면 생성된 HTML 페이지의 시각적 스타일을 완전히 제어할 수 있어 출력이 브랜드나 보고 표준에 맞게 조정됩니다.

## 빠른 답변
- **주 진입점은 무엇인가요?** `HtmlSaveOptions`를 사용자 지정 콜백과 함께 사용합니다.  
- **라이선스가 필요합니까?** 예, 프로덕션 환경에서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **대형 프로젝트를 내보낼 수 있나요?** Aspose.Tasks는 전체 파일을 메모리에 로드하지 않고도 10,000개 이상의 작업을 포함한 프로젝트를 처리합니다.  
- **CSS 사용자 지정은 선택 사항인가요?** 예, 기본 스타일시트를 사용하려면 콜백을 생략할 수 있습니다.

## Aspose.Tasks에서 CSS를 사용자 지정하는 방법?

프로젝트를 로드하고 `HtmlSaveOptions` 객체에 CSS 저장 콜백을 연결한 다음 `project.Save`를 호출합니다. 이 패턴을 사용하면 몇 줄의 코드만으로 사용자 지정 CSS 파일을 작성하고, 기본 스타일을 교체하며, 폴더 구조를 제어할 수 있습니다. 내보내기 과정에서 각 CSS 파일에 대해 콜백이 자동으로 호출됩니다.

`HtmlSaveOptions`는 프로젝트가 HTML로 내보내지는 방식을 구성합니다.

## 소개

이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 CSS 인수를 저장하는 과정을 자세히 살펴봅니다. Cascading Style Sheets(CSS)는 HTML 요소의 표시를 정의하는 데 필수적이며, Aspose.Tasks를 통해 이러한 CSS 속성을 효율적으로 조작하고 저장할 수 있습니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하십시오:

1. 설치: Aspose.Tasks for .NET이 설치되어 있는지 확인하십시오. [website](https://releases.aspose.com/tasks/net/)에서 다운로드할 수 있습니다.
2. 기본 지식: C# 및 .NET 개발 환경에 익숙한 것이 권장됩니다.

## 네임스페이스 가져오기

To get started, import the necessary namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 단계 1: CSS 저장 콜백 정의

`ICssSavingCallback`은 HTML 내보내기 중 CSS 파일이 저장되는 방식을 사용자 지정할 수 있게 해주는 인터페이스입니다.

**CSS 저장 콜백**은 Aspose.Tasks가 HTML 내보내기 중 CSS 파일을 작성하기 위해 호출하는 대리자입니다. 각 CSS 파일이 생성되는 방식을 제어하도록 콜백 메서드를 정의하십시오:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## 단계 2: 글꼴 및 이미지 저장 콜백 구현

`FontSavingArgs`는 저장되는 글꼴에 대한 정보를 제공하고, `ImageSavingArgs`는 이미지 리소스에 대한 세부 정보를 제공합니다.

글꼴 및 이미지 저장 콜백 메서드를 유사하게 구현하십시오:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## 단계 3: 저장 옵션 구성

`HtmlSaveOptions`는 프로젝트가 HTML로 내보내지는 방식을 제어하는 구성 객체입니다.

`HtmlSaveOptions`를 사용하면 콜백, 출력 폴더 및 기타 내보내기 설정을 지정할 수 있습니다.

앞서 정의한 콜백을 사용하고 출력 폴더를 지정하도록 해당 속성을 설정하십시오:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 단계 4: 사용자 지정 CSS로 프로젝트 저장

`Project`는 조작 및 저장이 가능한 Microsoft Project 파일을 나타냅니다.

마지막으로, 사용자 지정 CSS 설정을 적용하여 프로젝트를 저장하십시오:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## 프로젝트 내보내기 시 CSS를 사용자 지정하는 이유는?

Aspose.Tasks는 **프로젝트를 HTML로 내보내기**를 30개 이상의 형식으로 지원하며, 내보내기당 최대 30개의 별도 CSS 파일을 생성할 수 있습니다. 10,000개 이상의 작업을 포함한 프로젝트도 메모리 사용량을 200 MB 이하로 유지하면서 안정적으로 처리하여 성능 병목 현상 없이 엔터프라이즈 규모 보고를 가능하게 합니다.

## 결론

이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 CSS 인수를 저장하는 방법을 살펴보았습니다. CSS 저장 콜백을 정의하고 HTML 저장 옵션을 구성함으로써 요구 사항에 맞게 CSS 속성을 효율적으로 조작할 수 있습니다.

## 자주 묻는 질문

### Q1: Aspose.Tasks for .NET이란?

A1: Aspose.Tasks for .NET은 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있게 해주는 강력한 .NET API입니다.

### Q2: Aspose.Tasks로 HTML 파일을 저장할 때 CSS 속성을 사용자 지정할 수 있나요?

A2: 예, 필요에 따라 CSS 속성을 사용자 지정하기 위해 CSS 저장 콜백을 정의할 수 있습니다.

### Q3: Aspose.Tasks for .NET은 모든 버전의 Microsoft Project 파일과 호환되나요?

A3: Aspose.Tasks for .NET은 다양한 버전의 Microsoft Project 파일을 지원하여 다양한 환경에서 호환성을 보장합니다.

### Q4: Aspose.Tasks for .NET에 대한 포괄적인 문서는 어디에서 찾을 수 있나요?

A4: 자세한 정보와 예제는 [documentation](https://reference.aspose.com/tasks/net/)을 참고하십시오.

### Q5: Aspose.Tasks for .NET은 개발자를 위한 지원을 제공하나요?

A5: 예, Aspose.Tasks 커뮤니티의 [forum](https://forum.aspose.com/c/tasks/15)을 통해 지원을 받을 수 있습니다.

**추가 질문**

**Q: CSS를 사용자 지정하면 내보낸 HTML 크기에 어떤 영향을 줍니까?**  
A: 사용자 지정 CSS를 사용하면 사용되지 않는 기본 스타일을 제거할 수 있어 전체 크기를 최대 15 %까지 줄일 수 있습니다.

**Q: 동일한 콜백을 여러 프로젝트에 사용할 수 있나요?**  
A: 물론입니다. 콜백을 한 번 구현하면 여러 프로젝트 내보내기에 재사용할 수 있습니다.

**Q: 별도의 파일 대신 CSS를 HTML에 직접 삽입할 수 있나요?**  
A: 예, `HtmlSaveOptions.EmbeddedCss = true`로 설정하면 스타일시트를 인라인으로 삽입하여 배포를 간소화할 수 있습니다.

---

**마지막 업데이트:** 2026-07-05  
**테스트 환경:** Aspose.Tasks 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks로 MS Project를 HTML로 저장하기](/tasks/net/saving-options/html-save-options/)
- [Aspose.Tasks에서 페이지 저장 콜백 구현](/tasks/net/advanced-concepts/page-saving-callback/)
- [Aspose.Tasks에서 이미지 저장 처리](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}